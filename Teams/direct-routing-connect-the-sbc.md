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
description: Informazioni su come configurare e connettere il proprio SBC al routing diretto del sistema telefonico.
ms.openlocfilehash: fbcc1d79a4875ba835fc77ea24f6356ded3da894
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159038"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connettere il session border controller (SBC) al routing diretto

Questo articolo descrive come configurare un session border controller (SBC) e connetterlo al routing diretto del sistema telefonico.  Questo è il passaggio 1 dei passaggi seguenti per configurare il routing diretto:

- **Passaggio 1. Connettere il SBC con il sistema telefonico e convalidare la connessione** (questo articolo)
- Passaggio 2. [Abilitare gli utenti per il routing diretto](direct-routing-enable-users.md)
- Passaggio 3. [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

Puoi usare l'interfaccia di [amministrazione di Microsoft teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) per configurare e connettere un SBC per il routing diretto.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra, passa a routing **vocale** > **diretto**e quindi fai clic sulla scheda **SBCS** .
2. Fare clic su **Aggiungi**.
3. Immettere un nome di dominio completo per SBC. <br><br>Verificare che la parte Domain Name dell'FQDN corrisponda a un dominio registrato nel tenant e ricordare che il `*.onmicrosoft.com` nome di dominio non è supportato per il nome di dominio FQDN di SBC. Se ad esempio sono presenti due nomi di dominio, `contoso.com` `contoso.on.microsoft.com`usare `sbc.contoso.com` il nome SBC.
4. Configurare le impostazioni seguenti per SBC, in base alle esigenze dell'organizzazione. Per informazioni dettagliate su ognuna di queste impostazioni, vedere [Impostazioni SBC](#sbc-settings).

    ![Screenshot della pagina Add SBC nell'interfaccia di amministrazione di Microsoft Teams](media/direct-routing-add-sbc.png)

5. Al termine fare clic su **Salva**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Per connettere il SBC al routing diretto, è necessario:

1. [Connettersi a Skype for business online con PowerShell](#connect-to-skype-for-business-online-by-using-powershell).
2. [Connettere il SBC al tenant](#connect-the-sbc-to-the-tenant).
3. [Verificare la connessione SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for business online tramite PowerShell

Puoi usare una sessione di PowerShell connessa al tenant per associare il SBC all'interfaccia di routing diretta. Per aprire una sessione di PowerShell, seguire i passaggi descritti in [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per la gestione di SBC. Per verificare i comandi, digitare oppure copiare e incollare il comando seguente nella sessione di PowerShell e quindi premere INVIO: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Il comando restituisce le quattro funzioni visualizzate in questa sezione che consentono di gestire l'SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Connettere il SBC al tenant

Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) per connettere il SBC al tenant. In una sessione di PowerShell digitare il codice seguente e quindi premere INVIO:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Ti consigliamo di impostare un limite massimo per le chiamate in SBC usando le informazioni che puoi trovare nella documentazione SBC. Il limite attiverà una notifica se SBC è a livello di capacità.
  > 2. Puoi connettere il SBC solo se la parte del dominio del relativo nome FQDN corrisponde a uno dei domini registrati nel tenant, eccetto \*. onmicrosoft.com. L' \*uso dei nomi di dominio con estensione onmicrosoft.com non è supportato per il nome FQDN di SBC. Se ad esempio sono presenti due nomi di dominio, **Contoso**. com e **Contoso**. onmicrosoft.com, è possibile usare SBC. contoso. con per il nome SBC. Se si prova a connettere l'SBC con un nome, ad esempio SBC. contoso. ABC, il sistema non lo consente, poiché il dominio non è di proprietà di questo tenant.<br/>
  > Oltre al dominio registrato nel tenant, è importante che ci sia un utente con tale dominio e una licenza E3 o E5 assegnata. In caso contrario, verrà visualizzato il seguente messaggio di errore:<br/>
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
> Questo esempio Mostra solo i parametri minimi necessari. Sono disponibili altri parametri che è possibile impostare con il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) durante il processo di connessione. Per altre informazioni, Vedi [Impostazioni SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Verificare la connessione SBC

Per verificare la connessione:

- [Verificare se il controllo SBC è nell'elenco di sbcs associati](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Convalidare le opzioni SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se il controllo SBC è nell'elenco delle coppie di SBCs

Dopo aver connesso il controllo SBC, usare il cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) per verificare che l'SBC sia presente nell'elenco delle coppie di sbcs. Digitare quanto segue in una sessione remota di PowerShell e quindi premere INVIO:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Il gateway associato deve essere visualizzato nell'elenco come illustrato nell'esempio seguente e il parametro **Enabled** deve visualizzare il valore **true**.

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

Per convalidare l'associazione con le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva le risposte OK di 200 ai messaggi delle opzioni in uscita.

Quando il routing diretto Visualizza le opzioni in arrivo, inizierà a inviare messaggi di opzioni SIP in uscita all'FQDN SBC configurato nel campo dell'intestazione del contatto nel messaggio delle opzioni in arrivo. 

Per convalidare l'associazione con le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che il SBC invii una risposta ai messaggi delle opzioni provenienti da routing diretto e che il codice di risposta inviato sia 200 OK.

## <a name="sbc-settings"></a>Impostazioni SBC

Questa tabella elenca le opzioni che è possibile impostare per SBC nell'interfaccia di amministrazione di Microsoft teams e usando il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) .

|Obbligatorio?|Impostazione dell'interfaccia di amministrazione di Microsoft Teams|Parametro di PowerShell|Descrizione|Predefinita|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|**Aggiungere un nome di dominio completo per SBC**|FQDN |Nessuno|Nome FQDN, limite di 63 caratteri|Stringa, vedere l'elenco dei caratteri consentiti e non consentiti nelle [convenzioni di denominazione in Active Directory per computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|**Abilitato**|Abilitata|USA per attivare SBC per le chiamate in uscita. Puoi usare questa funzione per rimuovere temporaneamente l'SBC dal servizio durante l'aggiornamento o durante la manutenzione. |Falso|Vero<br/>Falso|Boolean|
|Sì|**Porta di segnalazione SIP**|SipSignalingPort |Questa è la porta di ascolto usata per comunicare con il routing diretto usando il protocollo Transport Layer (TLS).|Nessuno|Qualsiasi porta|da 0 a 65535 |
|No|**Opzioni di invio SIP**|SendSIPOptions |Definisce se SBC invierà messaggi di opzioni SIP. Ti consigliamo vivamente di attivare questa impostazione. Quando questa impostazione è disattivata, il SBC viene escluso dal sistema di monitoraggio e avviso.|Vero|Vero<br/>Falso|Boolean|
|No|**Inoltra cronologia chiamate**|ForwardCallHistory |Indica se le informazioni sulla cronologia delle chiamate vengono inoltrate tramite il trunk. Quando si attiva questa operazione, il proxy di Office 365 invia una cronologia-info e un'intestazione di riferimento. |Falso|Vero<br/>Falso|Boolean|
|No|**Intestazione in avanti P-asserzione-identità (PAI)**|ForwardPAI|Indica se l'intestazione PAI viene inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se questa impostazione è attivata, viene inviata anche l'intestazione privacy: ID.|Falso|Vero<br/>Falso|Boolean|
|No|**Capacità chiamata simultanea**|MaxConcurrentSessions |Quando si imposta un valore, il sistema di avviso notificherà quando il numero di sessioni simultanee è pari a 90% o superiore a questo valore. Se non si imposta un valore, gli avvisi non vengono generati. Tuttavia, il sistema di monitoraggio riporterà il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>1-100.000 ||
|No|**Codici di risposta di failover**|FailoverResponseCodes<br>|Se il routing diretto riceve qualsiasi codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita si intende una chiamata da un client teams alla rete PSTN con flusso di traffico: client teams-> Direct routing-> SBC-> Telephony Network). Quando si specifica un codice di risposta di failover, questo impone al routing diretto di provare un altro SBC (se esiste un altro SBC nel criterio di routing vocale dell'utente) quando riceve i codici specificati se SBC non riesce a effettuare una chiamata a causa di problemi di rete o altri. Per altre informazioni, vedere [failover di codici SIP specifici ricevuti da Session Border Controller (SBC)](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Int|
|No|**Tempi di failover (secondi)**|FailoverTimeSeconds |Quando si imposta un valore, le chiamate in uscita non risposte dal gateway entro il tempo impostato vengono instradate al trunk successivo disponibile. Se non sono presenti trunk aggiuntivi, la chiamata viene rilasciata automaticamente. Il valore predefinito è di 10 secondi. In un'organizzazione con le reti lente e le risposte del gateway, questo potrebbe potenzialmente causare la perdita di chiamate inutilmente.|10|Numero|Int|
|No|**Paese o area geografica preferita per il traffico multimediale**|MediaRelayRoutingLocationOverride |Consente di impostare manualmente il paese o l'area geografica preferita per il traffico multimediale. È consigliabile impostare questa opzione solo se i registri delle chiamate indicano chiaramente che l'assegnazione predefinita del Data Center per il percorso multimediale non usa il percorso più vicino al Data Center SBC. Per impostazione predefinita, il routing diretto assegna un Data Center in base all'indirizzo IP pubblico di SBC e seleziona sempre il percorso più vicino al Data Center SBC. Tuttavia, in alcuni casi, il percorso predefinito potrebbe non essere il percorso ottimale. Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale. |Nessuno|Codici paese in formato ISO||
|No|**SBC supporta PIDF/LO per le chiamate di emergenza**|PidfloSupported|Specifica se SBC supporta l'oggetto location Data Format (PIDF/LO) per le chiamate di emergenza.||||
|No|**Squillare il telefono durante il tentativo di trovare l'utente**|GenerateRingingWhileLocatingUser|Imposta se un segnale audio viene riprodotto al chiamante per indicare che il team sta per stabilire la chiamata. Questa impostazione si applica solo al routing diretto in modalità bypass non multimediale. A volte le chiamate in ingresso dalla rete PSTN ai client teams possono richiedere più tempo del previsto per la creazione. In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e la chiamata può essere annullata da alcuni provider di telecomunicazioni. Questa impostazione consente di evitare silenzi imprevisti che possono verificarsi in questi scenari.|Vero|Vero<br/>Falso|Boolean|
|No| - |MediaBypass|Questa impostazione indica se SBC supporta il bypass multimediale e se si vuole usarlo per questo SBC. |Nessuno|Vero<br/>Falso|Boolean|

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)
