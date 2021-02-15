---
title: Connettere il controller di bordo della sessione (SBC) al routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come configurare e connettere il tuo SBC all'instradamento diretto del sistema telefonico.
ms.openlocfilehash: e20ab921e8f01d8beea15f0b1dd8a50e229f4e91
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099446"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connettere il controller di bordo della sessione (SBC) al routing diretto

Questo articolo descrive come configurare un controller dei confini della sessione (SBC) e collegarlo all'instradamento diretto del sistema telefonico.  Questo è il passaggio 1 della procedura seguente per configurare il routing diretto:

- **Passaggio 1. Collegare il servizio SBC al Sistema telefonico e convalidare la connessione** (questo articolo)
- Passaggio 2. [Abilitare gli utenti per il routing diretto](direct-routing-enable-users.md)
- Passaggio 3. [Configurare l'instradamento delle chiamate](direct-routing-voice-routing.md)
- Passaggio 4. [Convertire i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)

È possibile usare [l'interfaccia di amministrazione di Microsoft Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) per configurare e connettere un SBC al routing diretto.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra passare a **Voice** Direct Routing e quindi fare  >  clic sulla **scheda SBCs.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome di dominio completo per SBC. <br><br>Verificare che la parte relativa al nome di dominio completo corrisponda a un dominio registrato nel tenant e tenere presente che il nome di dominio non è supportato per il nome di dominio `*.onmicrosoft.com` COMPLETO SBC. Ad esempio, se si hanno due nomi di dominio `contoso.com` e , usare come nome `contoso.onmicrosoft.com` `sbc.contoso.com` SBC. Se si usa un sottodominio, assicurarsi che sia registrato anche nel tenant. Ad esempio, se si vuole usare `sbc.service.contoso.com` , `service.contoso.com` è necessario registrare.
4. Configurare le impostazioni seguenti per SBC in base alle esigenze dell'organizzazione. Per informazioni dettagliate su ognuna di queste impostazioni, vedere [Impostazioni SBC.](#sbc-settings)

    ![Screenshot dell'aggiunta della pagina SBC nell'interfaccia di amministrazione di Microsoft Teams](media/direct-routing-add-sbc.png)

5. Al termine fare clic su **Salva**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Per connettere il proprio SBC al routing diretto, è necessario:

1. [Connettersi a Skype for Business online tramite PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Connettere il database SBC al tenant.](#connect-the-sbc-to-the-tenant)
3. [Verificare la connessione SBC.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for Business online tramite PowerShell

È possibile usare una sessione di PowerShell connessa al tenant per associare il servizio SBC all'interfaccia di routing diretto. Per aprire una sessione di PowerShell, seguire i passaggi descritti in Configurare [il computer per Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per gestire il database SBC. Per verificare i comandi, digitare oppure copiare e incollare il comando seguente nella sessione di PowerShell e quindi premere INVIO: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Il comando restituisce le quattro funzioni qui mostrate che consentono di gestire il valore SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Connettere l'SBC al tenant

Usare il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) per connettere il servizio SBC al tenant. In una sessione di PowerShell digitare quanto segue e quindi premere INVIO:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. È consigliabile impostare un limite massimo per le chiamate nel servizio SBC usando le informazioni disponibili nella documentazione SBC. Il limite attiverà una notifica se il valore SBC si trova al livello di capacità.
  > 2. È possibile connettere il servizio SBC solo se la parte del dominio del relativo FQDN corrisponde a uno dei domini registrati nel tenant, ad eccezione di \* onmicrosoft.com. L'uso onmicrosoft.com di dominio completo SBC non è \* supportato. Ad esempio, se si hanno due nomi di dominio, **contoso.com** e **contoso.onmicrosoft.com,** è possibile usare sbc.contoso.con come nome SBC. Se si prova a connettere il dominio SBC con un nome come sbc.contoso.abc, il sistema non lo consente, perché il dominio non è di proprietà del tenant.<br/>
  > Oltre al dominio registrato nel tenant, è importante che ci sia un utente con quel dominio e una licenza E3 o E5 assegnata. In caso contrario, verrà visualizzato l'errore seguente:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Ecco un esempio:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Che restituisce:

<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>

> [!NOTE]
> Questo esempio mostra solo i parametri minimi obbligatori. Sono disponibili altri parametri che è possibile impostare con il cmdlet [New-CsOnlinePSTNGateway durante](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) il processo di connessione. Per altre informazioni, vedere Impostazioni [SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Verificare la connessione SBC

Per verificare la connessione:

- [Verificare se SBC è in elenco di SBC associati.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Convalidare le opzioni SIP.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se SBC è in elenco di SBC associati

Dopo aver connesso SBC, usa il cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) per verificare che sBC sia presente nell'elenco di SBC associati. Digitare quanto segue in una sessione remota di PowerShell e quindi premere INVIO:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Il gateway associato dovrebbe comparire nell'elenco come illustrato nell'esempio seguente, mentre il parametro **Enabled** dovrebbe visualizzare il valore **True.**

Che restituisce:

<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA
ExcludedCodecs        :  
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
</pre>

#### <a name="validate-sip-options"></a>Verificare le opzioni SIP

Per convalidare l'associazione usando le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva 200 risposte OK ai messaggi OPTIONS in uscita.

Quando in Routing diretto sono presenti le opzioni in arrivo, inizierà a inviare i messaggi delle opzioni SIP in uscita all'FQDN SBC configurato nel campo di intestazione Contatto del messaggio OPZIONI in arrivo. 

Per convalidare l'associazione usando le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che SBC invii una risposta ai messaggi OPTIONS provenienti da Direct Routing e che il codice di risposta inviato sia 200 OK.

## <a name="sbc-settings"></a>Impostazioni SBC

Questa tabella elenca le opzioni che è possibile impostare per SBC nell'interfaccia di amministrazione di Microsoft Teams e utilizzando il cmdlet [New-CsOnlinePSTNGateway.](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

|Obbligatorio?|Impostazione dell'interfaccia di amministrazione di Microsoft Teams|Parametro di PowerShell|Descrizione|Impostazione predefinita|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|**Aggiungere un FQDN per il campo SBC**|FQDN |Nessuno|Nome FQDN, limite di 63 caratteri|String, vedere l'elenco dei caratteri consentiti e non consentiti nelle convenzioni di denominazione in Active Directory per [computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|**Abilitato**|Abilitata|Da usare per attivare il controller SBC per le chiamate in uscita. È possibile usarla per rimuovere temporaneamente il servizio SBC dal servizio durante l'aggiornamento o durante la manutenzione. |Falso|Vero<br/>Falso|Boolean|
|Sì|**Porta di segnalazione SIP**|SipSignalingPort |Questa è la porta in ascolto usata per comunicare con il routing diretto usando il protocollo TLS (Transport Layer).|Nessuno|Qualsiasi porta|Da 0 a 65535 |
|No|**Opzioni di invio SIP**|SendSIPOptions |Definisce se L'SBC invierà messaggi di opzioni SIP. È consigliabile attivare questa impostazione. Quando questa impostazione è disattivata, il servizio SBC viene escluso dal sistema di monitoraggio e avviso.|Vero|Vero<br/>Falso|Boolean|
|No|**Inoltrare il cronologia delle chiamate**|ForwardCallHistory |Indica se le informazioni del cronologia chiamate vengono inoltrate attraverso il trunk. Quando si attiva questa opzione, il proxy di Microsoft 365 o Office 365 invia un'intestazione Cronologia e Riferimento. |Falso|Vero<br/>Falso|Boolean|
|No|**Forward P-Asserted-identity (PAI) header**|ForwardPAI|Indica se l'intestazione PAI viene inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se questa impostazione è attivata, viene inviata anche l'intestazione Privacy:ID.|Falso|Vero<br/>Falso|Boolean|
|No|**Capacità di chiamata simultanea**|MaxConcurrentSessions |Quando si imposta un valore, il sistema di avviso invierà una notifica quando il numero di sessioni simultanee è 90% o superiore a questo valore. Se non si imposta un valore, gli avvisi non vengono generati. Tuttavia, il sistema di monitoraggio riporta il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>Da 1 a 100.000 ||
|No|**Codici di risposta di failover**|FailoverResponseCodes<br>|Se l'instradamento diretto riceve un codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita si intende una chiamata da un client di Teams alla rete PSTN con flusso di traffico: client Teams -> Direct Routing -> SBC -> rete telefonica). Quando si specifica un codice di risposta di failover, questo forza l'instradamento diretto a provare un altro SBC (se esiste un altro SBC nei criteri di routing vocale dell'utente) quando riceve i codici specificati se SBC non può effettuare una chiamata a causa di problemi di rete o di altro tipo. Per altre informazioni, vedere Failover di codici SIP specifici ricevuti dal controller dei confini della sessione [(SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|No|**Tempi di failover (secondi)**|FailoverTimeSeconds |Quando si imposta un valore, le chiamate in uscita a cui non si risponde dal gateway entro il tempo impostato vengono indirizzate al trunk disponibile successivo. Se non ci sono altri trunk, la chiamata viene interrotta automaticamente. Il valore predefinito è 10 secondi. In un'organizzazione con reti lente e risposte del gateway, questo potrebbe comportare un numero inutilmente interrotta delle chiamate.|10|Numero|Int|
|No|**Paese o area geografica preferita per il traffico multimediale**|MediaRelayRoutingLocationOverride |Da usare per impostare manualmente il paese o l'area geografica preferita per il traffico multimediale. È consigliabile impostare questa impostazione solo se i registri delle chiamate indicano chiaramente che l'assegnazione predefinita del data center per il percorso del supporto non usa il percorso più vicino al data center SBC. Per impostazione predefinita, il routing diretto assegna un data center in base all'indirizzo IP pubblico del centro dati SBC e seleziona sempre il percorso più vicino al data center SBC. Tuttavia, in alcuni casi, il percorso predefinito potrebbe non essere quello ottimale. Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale. |Nessuno|Codici paese in formato ISO||
|No|**SBC supporta il PIDF/LO per le chiamate di emergenza**|PidfloSupported|Specificare se SBC supporta il formato PIDF/LO (Presence Information Data Format Location Object) per le chiamate di emergenza.||||
|No|**Squilla mentre cerchi l'utente**|GenerateRingingWhileLocatingUser|Impostare se al chiamante viene riprodotto un segnale audio per indicare che Teams è in corso per stabilire la chiamata. Questa impostazione si applica solo al routing diretto in modalità di bypass non multimediale. A volte le chiamate in ingresso dalla rete PSTN ai client di Teams possono richiedere più tempo del previsto per essere stabilite. In questo caso, il chiamante potrebbe non sentire nulla, il client di Teams non squilla e la chiamata potrebbe essere annullata da alcuni provider di telecomunicazioni. Questa impostazione consente di evitare silenzi imprevisti che possono verificarsi in questi scenari.|Vero|Vero<br/>Falso|Boolean|
|No| - |MediaBypass|Questa impostazione indica se il controller SBC supporta il bypass multimediale e se lo si vuole usare per questo SBC. |Nessuno|Vero<br/>Falso|Boolean|

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)
