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
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157976"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connettere il session border controller (SBC) al routing diretto 

Questo articolo descrive come connettere il session border controller (SBC) al routing diretto del sistema telefonico.  Questo è il passaggio 1 dei passaggi seguenti per la configurazione del routing diretto:

- **Passaggio 1. Connettere il SBC con il sistema telefonico e convalidare la connessione** (questo articolo)
- Passaggio 2. [Abilitare gli utenti per il routing diretto](direct-routing-enable-users.md)
- Passaggio 3. [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

Per connettere il SBC al routing diretto, è necessario: 

1. Connettersi all'interfaccia di amministrazione di **Skype for business online** con PowerShell.            
2. Connettere il SBC al tenant.
3. Convalidare la connessione. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for business online tramite PowerShell 

Puoi usare una sessione di PowerShell connessa al tenant per associare il SBC all'interfaccia di routing diretta. Per aprire una sessione di PowerShell, seguire i passaggi descritti in [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Dopo aver stabilito una sessione remota di PowerShell, convalidare la possibilità di visualizzare i comandi per la gestione di SBC. Per convalidare i comandi, digitare oppure copiare e incollare il comando seguente nella sessione di PowerShell e premere INVIO: 

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


## <a name="connect-the-sbc-to-the-tenant"></a>Connettere il SBC al tenant 

Per connettere il SBC al tenant, nella sessione di PowerShell digitare il testo seguente e premere INVIO: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft consiglia di impostare un limite massimo per le chiamate in SBC, usando le informazioni che si trovano nella documentazione SBC. Il limite attiverà una notifica se SBC è a livello di capacità.
  > 2. Puoi associare l'SBC solo se la parte del dominio del relativo nome FQDN corrisponde a uno dei domini registrati nel tenant, eccetto \*. onmicrosoft.com. L' \*uso dei nomi di dominio con estensione onmicrosoft.com non è supportato per il nome FQDN di SBC. Se ad esempio sono presenti due nomi di dominio:<br/><br/>
  > **Contoso**. com<br/>**Contoso**. onmicrosoft.com<br/><br/>
  > Per il nome SBC, è possibile usare il nome sbc.contoso.com. Se si tenta di associare l'SBC con un nome SBC. contoso. ABC, il sistema non lo consente, poiché il dominio non è di proprietà del tenant.<br/>
  > Oltre al dominio registrato nel tenant, è importante che ci sia un utente con tale dominio e una licenza E3 o E5 assegnata. In caso contrario, verrà visualizzato il seguente messaggio di errore:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
Restituisce
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
Sono disponibili altre opzioni che possono essere impostate durante il processo di connessione. Nell'esempio precedente vengono tuttavia visualizzati solo i parametri minimi obbligatori. 
 
Nella tabella seguente sono elencati i parametri aggiuntivi che è possibile usare per ```New-CsOnlinePstnGateway```l'impostazione dei parametri.

|Obbligatorio?|Nome|Descrizione|Predefinita|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|FQDN|Nome FQDN di SBC |Nessuno|Nome NoneFQDN, limite di 63 caratteri|Stringa, elenco dei caratteri consentiti e non consentiti nelle [convenzioni di denominazione in Active Directory per computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|MediaBypass |Il parametro indicato da SBC supporta il bypass multimediale e l'amministratore vuole usarlo.|Nessuno|True<br/>False|Boolean|
|Sì|SipSignalingPort |Porta di ascolto usata per comunicare con i servizi di routing diretto usando il protocollo Transport Layer Security (TLS).|Nessuno|Qualsiasi porta|da 0 a 65535 |
|No|FailoverTimeSeconds |Se impostato su 10 (valore predefinito), le chiamate in uscita non risposte dal gateway entro 10 secondi vengono instradate al successivo trunk disponibile. Se non sono presenti trunk aggiuntivi, la chiamata viene automaticamente eliminata. In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente. Il valore predefinito è 10.|10|Numero|Int|
|No|ForwardCallHistory |Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk. Se abilitata, il proxy PSTN di Office 365 invia due intestazioni: History-info e riferimento. Il valore predefinito è **false** ($false). |False|True<br/>False|Boolean|
|No|ForwardPAI|Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se è abilitata anche l'intestazione privacy: ID verrà inviata. Il valore predefinito è **false** ($false).|False|True<br/>False|Boolean|
|No|SendSIPOptions |Definisce se un SBC riceverà o non invierà le opzioni SIP. Se disabilitato, SBC verrà escluso dal sistema di monitoraggio e avviso. Ti consigliamo vivamente di abilitare le opzioni SIP. Il valore predefinito è **true**. |True|True<br/>False|Boolean|
|No|MaxConcurrentSessions |Usato da Alerting System. Quando viene impostato un valore qualsiasi, il sistema di avviso genera un avviso per l'amministratore del tenant quando il numero di sessioni simultanee è pari a 90% o superiore a questo valore. Se il parametro non è impostato, gli avvisi non vengono generati. Il sistema di monitoraggio riporterà tuttavia il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>1-100.000 ||
|No|MediaRelayRoutingLocationOverride |Consente di selezionare manualmente il percorso per elementi multimediali. Il routing diretto assegna un Data Center per il percorso multimediale basato sull'IP pubblico di SBC. Selezionare sempre più vicino al Data Center SBC. Tuttavia, in alcuni casi un IP pubblico da, ad esempio, un intervallo degli Stati Uniti può essere assegnato a un SBC situato in Europa. In questo caso useremo un percorso di supporto non ottimale. Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale. Microsoft consiglia solo l'impostazione di questo parametro se i registri delle chiamate indicano chiaramente che l'assegnazione automatica del Data Center per il percorso multimediale non assegna il più vicino al Data Center SBC. |Nessuno|Codici paese in formato ISO||
|No|Abilitata|Usato per abilitare questo SBC per le chiamate in uscita. Può essere usato per rimuovere temporaneamente il SBC mentre viene aggiornato o durante la manutenzione. |False|True<br/>False|Boolean|
 
## <a name="verify-the-sbc-connection"></a>Verificare la connessione SBC 

Per verificare la connessione: 
- Verificare se il controllo SBC è nell'elenco di SBCs associati. 
- Convalidare le opzioni SIP. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se il controllo SBC è nell'elenco delle coppie di SBCs 

Dopo aver connesso il controllo SBC, verificare che l'SBC sia presente nell'elenco di SBCs associati eseguendo il comando seguente in una sessione remota di PowerShell: 

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

### <a name="validate-sip-options-flow"></a>Convalidare il flusso delle opzioni SIP 

Per convalidare l'associazione con le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva le risposte OK di 200 ai messaggi delle opzioni in uscita.

Quando il routing diretto Visualizza le opzioni in arrivo, inizierà a inviare messaggi di opzioni SIP in uscita all'FQDN SBC configurato nel campo dell'intestazione del contatto nel messaggio delle opzioni in arrivo. 

Per convalidare l'associazione con le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che il SBC invii una risposta ai messaggi delle opzioni provenienti da routing diretto e che il codice di risposta inviato sia 200 OK.


## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
