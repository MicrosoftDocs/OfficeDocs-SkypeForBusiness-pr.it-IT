---
title: Connettere il session border controller (SBC) al routing diretto
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
description: Scopri come configurare e connettere il tuo SBC a Phone System Direct Routing.
ms.openlocfilehash: 697f426b9c9dc3215d653520658282fab1787001
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122250"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connettere il session border controller (SBC) al routing diretto

Questo articolo descrive come configurare un session border controller (SBC) e collegarlo a Phone System Direct Routing.  Questo è il passaggio 1 della procedura seguente per configurare il routing diretto:

- **Passaggio 1. Connettere SBC con Sistema telefonico e convalidare la connessione** (questo articolo)
- Passaggio 2. [Abilitare gli utenti per il routing diretto](direct-routing-enable-users.md)
- Passaggio 3. [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md)

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

È possibile usare [l'interfaccia di amministrazione di Microsoft Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) per configurare e connettere un SBC al routing diretto.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Routing**  >  **diretto vocale** e quindi fare clic sulla scheda **SBC.**
2. Fare clic su **Aggiungi**.
3. Immettere un NOME DI DOMINIO completo per SBC. <br><br>Verificare che la parte relativa al nome di dominio dell'FQDN corrisponda a un dominio registrato nel tenant e tenere presente che il nome di dominio non è supportato per il nome di dominio `*.onmicrosoft.com` FQDN SBC. Ad esempio, se si hanno due nomi di dominio e `contoso.com` , usare come nome `contoso.onmicrosoft.com` `sbc.contoso.com` SBC. Se si usa un sottodominio, assicurarsi che questo sottodominio sia registrato anche nel tenant. Ad esempio, se si vuole usare `sbc.service.contoso.com` , `service.contoso.com` è necessario registrare.
4. Configurare le impostazioni seguenti per SBC, in base alle esigenze dell'organizzazione. Per informazioni dettagliate su ognuna di queste impostazioni, vedere [Impostazioni SBC.](#sbc-settings)

    ![Screenshot dell'aggiunta della pagina SBC nell'interfaccia di amministrazione di Microsoft Teams](media/direct-routing-add-sbc.png)

5. Al termine fare clic su **Salva**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Per connettere il servizio SBC al routing diretto, è necessario:

1. [Connettersi a Skype for Business online tramite PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Connettere il database SBC al tenant](#connect-the-sbc-to-the-tenant).
3. [Verificare la connessione SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for Business online tramite PowerShell

È possibile usare una sessione di PowerShell connessa al tenant per associare SBC all'interfaccia di routing diretto. Per aprire una sessione di PowerShell, seguire i passaggi descritti in [Configurare il computer per Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per gestire il database SBC. Per verificare i comandi, digitare oppure copiare e incollare il comando seguente nella sessione di PowerShell e quindi premere INVIO: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Il comando restituisce le quattro funzioni mostrate qui che consentono di gestire il valore SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Connettere il database SBC al tenant

Usare il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) per connettere il database SBC al tenant. In una sessione di PowerShell digitare quanto segue e quindi premere INVIO:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. È consigliabile impostare un limite massimo per le chiamate in SBC usando le informazioni disponibili nella documentazione di SBC. Il limite attiverà una notifica se il valore SBC è a livello di capacità.
  > 2. È possibile connettere il servizio SBC solo se la parte del dominio del relativo FQDN corrisponde a uno dei domini registrati nel tenant, ad eccezione di \* onmicrosoft.com. \*L'uso di onmicrosoft.com di dominio non è supportato per il nome FQDN SBC. Ad esempio, se si hanno due nomi di dominio, **contoso**.com e **contoso**.onmicrosoft.com, è possibile usare sbc.contoso.com per il nome SBC. Se si prova a connettere SBC con un nome come sbc.contoso.abc, il sistema non lo consente, perché il dominio non è di proprietà di questo tenant.<br/>
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
> Questo esempio mostra solo i parametri minimi obbligatori. Sono disponibili altri parametri che è possibile impostare con il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) durante il processo di connessione. Per altre informazioni, vedere [Impostazioni SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Verificare la connessione SBC

Per verificare la connessione:

- [Verificare se SBC è in elenco di SBC associati.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Convalidare le opzioni SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se SBC è in elenco di SBC associati

Dopo aver connesso SBC, usare il cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) per verificare che SBC sia presente nell'elenco di SBC associati. Digitare quanto segue in una sessione remota di PowerShell e quindi premere INVIO:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Il gateway associato dovrebbe essere visualizzato nell'elenco come illustrato nell'esempio seguente, mentre il parametro **Enabled** dovrebbe visualizzare il valore **True**.

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

#### <a name="validate-sip-options"></a>Convalidare le opzioni SIP

Per convalidare l'associazione usando le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva 200 risposte OK ai messaggi OPTIONS in uscita.

Quando Instradamento diretto visualizza opzioni in arrivo, inizierà a inviare messaggi opzioni SIP in uscita all'FQDN SBC configurato nel campo di intestazione Contatto nel messaggio OPZIONI in arrivo. 

Per convalidare l'associazione usando le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che SBC invii una risposta ai messaggi OPTIONS provenienti da Direct Routing e che il codice di risposta inviato sia 200 OK.

## <a name="sbc-settings"></a>Impostazioni SBC

Questa tabella elenca le opzioni che è possibile impostare per SBC nell'interfaccia di amministrazione di Microsoft Teams e usando il cmdlet [New-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway)

|Obbligatorio?|Impostazione dell'interfaccia di amministrazione di Microsoft Teams|Parametro di PowerShell|Descrizione|Impostazione predefinita|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|**Aggiungere un nome di dominio completo per SBC**|FQDN |Nessuno|Nome FQDN, limite di 63 caratteri|Stringa, vedere l'elenco dei caratteri consentiti e non consentiti nelle convenzioni di denominazione in Active Directory per [computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|**Abilitato**|Abilitata|Da usare per attivare SBC per le chiamate in uscita. È possibile usarlo per rimuovere temporaneamente SBC dal servizio durante l'aggiornamento o durante la manutenzione. |Falso|Vero<br/>Falso|Boolean|
|Sì|**Porta di segnalazione SIP**|SipSignalingPort |Questa è la porta di attesa usata per comunicare con il routing diretto usando il protocollo TLS (Transport Layer).|Nessuno|Qualsiasi porta|Da 0 a 65535 |
|No|**Opzioni di invio SIP**|SendSIPOptions |Definisce se SBC invierà messaggi di opzioni SIP. È consigliabile attivare questa impostazione. Quando questa impostazione è disattivata, SBC viene escluso dal sistema di monitoraggio e avviso.|Vero|Vero<br/>Falso|Boolean|
|No|**Cronologia chiamate inoltrate**|ForwardCallHistory |Indica se le informazioni della cronologia chiamate vengono inoltrate tramite il trunk. Quando si attiva questa opzione, il proxy di Microsoft 365 o Office 365 invia un'intestazione History-info e Referred-by. |Falso|Vero<br/>Falso|Boolean|
|No|**Intestazione Forward P-Asserted-identity (PAI)**|ForwardPAI|Indica se l'intestazione PAI viene inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se questa impostazione è attivata, viene inviata anche l'intestazione Privacy:ID.|Falso|Vero<br/>Falso|Boolean|
|No|**Capacità delle chiamate simultanee**|MaxConcurrentSessions |Quando si imposta un valore, il sistema di avvisi avvisa l'utente quando il numero di sessioni simultanee è del 90% o superiore a questo valore. Se non si imposta un valore, gli avvisi non vengono generati. Tuttavia, il sistema di monitoraggio segnala il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>Da 1 a 100.000 ||
|No|**Codici di risposta di failover**|FailoverResponseCodes<br>|Se Routing diretto riceve un codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita si intende una chiamata da un client di Teams alla rete PSTN con flusso di traffico: client teams -> Direct Routing -> SBC -> rete di telefonia). Quando si specifica un codice di risposta di failover, il routing diretto forza il routing diretto a provare un altro SBC (se esiste un altro SBC nei criteri di routing vocale dell'utente) quando riceve i codici specificati se SBC non è in grado di effettuare una chiamata a causa di problemi di rete o di altro tipo. Per altre informazioni, vedere Failover di codici SIP specifici [ricevuti da Session Border Controller (SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|No|**Tempi di failover (secondi)**|FailoverTimeSeconds |Quando si imposta un valore, le chiamate in uscita a cui il gateway non risponde entro il tempo impostato vengono instradati al successivo trunk disponibile. Se non sono presenti altri trunk, la chiamata viene automaticamente interrotta. Il valore predefinito è 10 secondi. In un'organizzazione con reti lente e risposte gateway, questo potrebbe comportare l'inutilmente dell'annullamento delle chiamate.|10|Numero|Int|
|No|**Paese o area geografica preferita per il traffico multimediale**|MediaRelayRoutingLocationOverride |Da usare per impostare manualmente il paese o l'area geografica preferita per il traffico multimediale. È consigliabile impostare questa opzione solo se i registri delle chiamate indicano chiaramente che l'assegnazione predefinita del data center per il percorso multimediale non usa il percorso più vicino al data center SBC. Per impostazione predefinita, Routing diretto assegna un data center in base all'indirizzo IP pubblico del SBC e seleziona sempre il percorso più vicino al data center SBC. Tuttavia, in alcuni casi, il percorso predefinito potrebbe non essere il percorso ottimale. Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale. |Nessuno|Codici paese in formato ISO||
|No|**SBC supporta PIDF/LO per le chiamate di emergenza**|PidfloSupported|Specificare se SBC supporta l'oggetto Posizione formato dati informazioni presenza (PIDF/LO) per le chiamate di emergenza.||||
|No| - |MediaBypass|Questa impostazione indica se SBC supporta il bypass multimediale e se si vuole usarlo per questo SBC. |Nessuno|Vero<br/>Falso|Boolean|

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)