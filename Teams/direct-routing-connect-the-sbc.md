---
title: Connettere il controller dei confini della sessione (SBC) al routing diretto
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare e connettere SBC a Teams Phone System Direct Routing.
ms.openlocfilehash: 0423c374e903aab2e283ee45bcabf9ceb31ef869
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682665"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connettere il controller dei confini della sessione (SBC) al routing diretto

Questo articolo descrive come configurare un session border controller (SBC) e connetterlo al routing diretto.  Questo è il passaggio 1 della procedura seguente per configurare il routing diretto:

- **Passaggio 1. Connettere la scheda SBC con sistema telefonico e convalidare la connessione** (questo articolo)
- Passaggio 2. [Abilitare gli utenti per il routing diretto](direct-routing-enable-users.md)
- Passaggio 3. [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre numeri in un formato alternativo](direct-routing-translate-numbers.md)

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

È possibile usare [l'interfaccia di amministrazione di Microsoft Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) per configurare e connettere una scheda SBC al routing diretto.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro vai a **Routing diretto** **vocale** >  e quindi fai clic sulla scheda **SBCs**.

2. Fare clic su **Aggiungi**.

3. Immettere un FQDN per SBC. <br><br>Verificare che la parte relativa al nome di dominio completo corrisponda a un dominio registrato nel tenant e tenere presente che il `*.onmicrosoft.com` nome di dominio non è supportato per il nome di dominio FQDN SBC. Ad esempio, se si hanno due nomi di `contoso.com` dominio e `contoso.onmicrosoft.com`, usare `sbc.contoso.com` come nome SBC. Se si usa un sottodominio, assicurarsi che anche questo sottodominio sia registrato nel tenant. Ad esempio, se si vuole usare `sbc.service.contoso.com`, `service.contoso.com` è necessario registrarlo.

4. Configurare le impostazioni seguenti per SBC, in base alle esigenze dell'organizzazione. Per informazioni dettagliate su ognuna di queste impostazioni, vedere [Impostazioni SBC](#sbc-settings).

    ![Screenshot della pagina aggiungi SBC nell'interfaccia di amministrazione di Microsoft Teams.](media/direct-routing-add-sbc.png)

5. Al termine fare clic su **Salva**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Per connettere SBC a Direct Routing, è necessario:

1. [Connettersi a Skype for Business Online usando PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Connettere la scheda SBC al tenant](#connect-the-sbc-to-the-tenant).

3. [Verificare la connessione SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for Business Online tramite PowerShell

Per associare SBC all'interfaccia di routing diretto, usare una sessione di PowerShell connessa al tenant. Per aprire una sessione di PowerShell, seguire i passaggi descritti in [Configurare il computer per Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per gestire SBC. Per verificare i comandi, digitare oppure copiare e incollare il comando seguente nella sessione di PowerShell e quindi premere INVIO: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Il comando restituisce le quattro funzioni qui visualizzate che consentono di gestire la funzione SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Connettere la scheda SBC al tenant

Per connettere SBC al tenant, usa il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . In una sessione di PowerShell digitare quanto segue e quindi premere INVIO:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. È consigliabile impostare un limite massimo per le chiamate in SBC usando le informazioni disponibili nella documentazione di SBC. Il limite attiverà una notifica se il segnale SBC è a livello di capacità.
  > 2. È possibile connettere la scheda SBC solo se la parte di dominio del relativo FQDN corrisponde a uno dei domini registrati nel tenant, ad eccezione \*di .onmicrosoft.com. L'uso di \*nomi di dominio .onmicrosoft.com non è supportato per il nome FQDN SBC. Ad esempio, se si hanno due nomi di dominio, **contoso.com** e **contoso.onmicrosoft.com**, è possibile usare sbc.contoso.com per il nome SBC. Se si prova a connettere SBC con un nome come sbc.contoso.abc, il sistema non lo consente, in quanto il dominio non è di proprietà di questo tenant.<br/>
  > Oltre al dominio registrato nel tenant, è importante che ci sia un utente con quel dominio e una licenza E3 o E5 assegnata. In caso contrario, verrà visualizzato l'errore seguente:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. Più IP mappati con lo stesso FQDN sul lato SBC non sono supportati.
  > 4. Per fornire la crittografia migliore della categoria ai clienti, Microsoft forza l'uso di TLS1.2 per l'interfaccia SIP routing diretto.
  > Per evitare qualsiasi impatto sul servizio, assicurarsi che gli SBC siano configurati per supportare TLS1.2 e possano connettersi usando uno dei pacchetti di crittografia seguenti: TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ad esempio. ECDHE-RSA-AES256-GCM-SHA384 TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 vale a dire ECDHE-RSA-AES128-GCM-SHA256 TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ad esempio ECDHE-RSA-AES256-SHA384 TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 vale a dire ECDHE-RSA-AES128-SHA256

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
> Questo esempio mostra solo i parametri minimi obbligatori. Sono disponibili altri parametri che è possibile impostare con il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) durante il processo di connessione. Per altre informazioni, vedere [Impostazioni SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Verificare la connessione SBC

Per verificare la connessione:

- [Controlla se SBC è presente nell'elenco dei controller di dominio condivisi associati](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Convalidare le opzioni SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se SBC è presente nell'elenco dei controller di dominio condivisi associati

Dopo aver connesso SBC, usa il cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) per verificare che la scheda SBC sia presente nell'elenco degli SBC associati. Digitare quanto segue in una sessione remota di PowerShell e quindi premere INVIO:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Il gateway associato dovrebbe essere visualizzato nell'elenco, come illustrato nell'esempio seguente, e il parametro **Enabled** dovrebbe visualizzare il valore **True**.

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

Per convalidare l'associazione utilizzando le opzioni SIP in uscita, usare l'interfaccia di gestione di SBC e verificare che SBC riceva 200 risposte OK ai messaggi OPZIONI in uscita.

Quando il routing diretto visualizza OPZIONI posta in arrivo, inizierà a inviare i messaggi delle opzioni SIP in uscita all'FQDN SBC configurato nel campo dell'intestazione Contatto del messaggio OPZIONI posta in arrivo. 

Per convalidare l'associazione utilizzando le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che SBC invii una risposta ai messaggi OPTIONS provenienti da Direct Routing e che il codice di risposta inviato sia 200 OK.

## <a name="sbc-settings"></a>Impostazioni SBC

Questa tabella elenca le opzioni che è possibile impostare per SBC nell'interfaccia di amministrazione di Microsoft Teams e usando il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) .

|Obbligatorio?|Impostazione dell'interfaccia di amministrazione di Teams|Parametro di PowerShell|Descrizione|Predefinito|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|**Aggiungere un FQDN per SBC**|FQDN |Nessuno|Nome FQDN, limite di 63 caratteri|Stringa. Vedere l'elenco dei caratteri consentiti e non consentiti [nelle convenzioni di denominazione in Active Directory per computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|**Abilitato**|Abilitata|Da usare per attivare SBC per le chiamate in uscita. È possibile usare questa opzione per rimuovere temporaneamente SBC dal servizio durante l'aggiornamento o durante la manutenzione. |Falso|Vero<br/>Falso|Boolean|
|Sì|**Porta di segnalazione SIP**|SipSignalingPort |Questa è la porta di ascolto usata per comunicare con l'instradamento diretto tramite il protocollo Transport Layer (TLS).|Nessuno|Qualsiasi porta|Da 0 a 65535 |
|No|**Opzioni Invia SIP**|SendSIPOptions |Definisce se la scheda SBC invierà messaggi di opzioni SIP. Ti consigliamo vivamente di attivare questa impostazione. Quando questa impostazione è disattivata, SBC viene escluso dal sistema di monitoraggio e avviso.|Vero|Vero<br/>Falso|Boolean|
|No|**Inoltrare la cronologia delle chiamate**|ForwardCallHistory |Indica se le informazioni del registro chiamate vengono inoltrate attraverso il trunk. Quando si attiva questa opzione, il proxy di Microsoft 365 invia un'intestazione Cronologia-info e Referred-by. |Falso|Vero<br/>Falso|Boolean|
|No|**Inoltrare l'intestazione P-Asserted-identity (PAI)**|ForwardPAI|Indica se l'intestazione PAI viene inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se questa impostazione è attivata, viene inviata anche l'intestazione Privacy:ID.|Falso|Vero<br/>Falso|Boolean|
|No|**Capacità di chiamata simultanea**|MaxConcurrentSessions |Quando si imposta un valore, il sistema di avviso ti avviserà quando il numero di sessioni simultanee è 90% o superiore a questo valore. Se non si imposta un valore, gli avvisi non vengono generati. Tuttavia, il sistema di monitoraggio segnala il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>Da 1 a 100.000 ||
|No|**Codici di risposta di failover**|FailoverResponseCodes<br>|Se il routing diretto riceve un codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita indica una chiamata da un client di Teams alla rete PSTN con flusso del traffico: client teams -> Routing diretto -> SBC -rete di telefonia >). Quando si specifica un codice di risposta di failover, questo forza direct routing a provare un altro SBC (se esiste un altro SBC nel criterio di routing vocale dell'utente) quando riceve i codici specificati se sBC non può effettuare una chiamata a causa di rete o altri problemi. Per ulteriori informazioni, vedere [Failover di specifici codici SIP ricevuti da Session Border Controller (SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|No|**Tempi di failover (secondi)**|FailoverTimeSeconds |Quando si imposta un valore, le chiamate in uscita a cui il gateway non risponde entro il tempo impostato vengono instradate al trunk disponibile successivo. Se non sono presenti trunk aggiuntivi, la chiamata viene interrotta automaticamente. Il valore predefinito è 10 secondi. In un'organizzazione con reti lente e risposte al gateway, questo potrebbe comportare l'inutilmente calo delle chiamate.|10|Numero|Int|
|No|**Paese o area geografica preferiti per il traffico multimediale**|MediaRelayRoutingLocationOverride | Non applicabile al routing diretto. Questo parametro è riservato per l'uso con i gestori gestiti nei Piani per chiamate |Nessuno|||
|No|**SBC supporta PIDF/LO per le chiamate di emergenza**|PidfloSupported|Specificare se SBC supporta il formato informazioni sulla presenza Formato posizione oggetto (PIDF/LO) per le chiamate di emergenza.||||
|No| - |MediaBypass|Questa impostazione indica se SBC supporta il bypass multimediale e se si vuole usarlo per questo SBC. |Nessuno|Vero<br/>Falso|Boolean|

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)
