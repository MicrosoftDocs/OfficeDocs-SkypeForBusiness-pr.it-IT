---
title: Configurare Instradamento diretto
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
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: beeecb1ece84980337c7fe385c6a0e1190bc5e3c
ms.sourcegitcommit: cb394272050d049ebceedb7df835b86362dfd8d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2019
ms.locfileid: "40741380"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

> [!Tip]
> Vedere la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificare la procedura e su come distribuirla: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)

Se non è già stato fatto, leggere [pianificare il routing diretto](direct-routing-plan.md) per i prerequisiti e rivedere altri passaggi che è necessario eseguire prima di configurare la rete del sistema telefonico Microsoft. 

Questo articolo descrive come configurare il routing diretto di Microsoft Phone System. Descrive come associare un SBC (Session Border Controller) supportato a routing diretto e come configurare gli utenti di Microsoft teams per usare il routing diretto per la connessione alla rete PSTN (Public Switched Telephone Network). Per completare la procedura descritta in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

È consigliabile verificare che SBC sia già stato configurato come consigliato dal fornitore SBC: 

- [Documentazione di distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione di distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione delle comunicazioni della barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

È possibile configurare il sistema telefonico Microsoft e consentire agli utenti di usare il routing diretto, quindi configurare Microsoft teams come client chiamante preferito completando le procedure seguenti: 

- [Associare il SBC a un sistema telefonico Microsoft e convalidare l'associazione](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Abilitare gli utenti per il servizio di routing diretto](#enable-users-for-direct-routing-service)
- Verificare che Microsoft teams sia il client chiamante preferito per gli utenti

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Associare il SBC al servizio di routing diretto del sistema telefonico 

Di seguito sono riportati i tre passaggi di alto livello per consentire di connettersi o associare l'SBC all'interfaccia di routing diretto: 

- Connettersi all'interfaccia di amministrazione di **Skype for business online** con PowerShell 
- Associare il SBC 
- Convalidare l'associazione 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connettersi a Skype for business online tramite PowerShell 

Puoi usare una sessione di PowerShell connessa al tenant per associare il SBC all'interfaccia di routing diretta. Per aprire una sessione di PowerShell, seguire i passaggi descritti in [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Dopo aver stabilito una sessione remota di PowerShell, verificare che sia possibile visualizzare i comandi per la gestione di SBC. Per convalidare i comandi, digitare o copiare/incollare il comando seguente nella sessione di PowerShell e premere INVIO: 

```
Get-Command *onlinePSTNGateway*
```

Il comando restituirà le quattro funzioni visualizzate in questa sezione che consente di gestire il SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Associare il SBC al tenant 

Per associare il SBC al tenant, nella sessione di PowerShell digitare il testo seguente e premere INVIO: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Ti consigliamo vivamente di impostare un limite massimo per le chiamate in SBC, usando le informazioni che puoi trovare nella documentazione SBC. Il limite attiverà una notifica se SBC è a livello di capacità.
  > 2. Puoi associare l'SBC solo se la parte del dominio del relativo nome FQDN corrisponde a uno dei domini registrati nel tenant, eccetto \*. onmicrosoft.com. L' \*uso dei nomi di dominio con estensione onmicrosoft.com non è supportato per il nome FQDN di SBC. Se ad esempio sono presenti due nomi di dominio:<br/><br/>
  > **Contoso**. com<br/>**Contoso**. onmicrosoft.com<br/><br/>
  > Per il nome SBC, è possibile usare il nome sbc.contoso.com. Se si tenta di associare l'SBC con un nome SBC. contoso. ABC, il sistema non lo consente, poiché il dominio non è di proprietà del tenant.<br/>
  > Oltre al dominio registrato nel tenant, è importante che ci sia un utente con tale dominio e una licenza E3 o E5 assegnata. In caso contrario, verrà visualizzato il seguente messaggio di errore:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Restituisce
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Sono disponibili altre opzioni che possono essere impostate durante il processo di associazione. Nell'esempio precedente vengono tuttavia visualizzati solo i parametri minimi obbligatori. 
 
Nella tabella seguente sono elencati i parametri aggiuntivi che è possibile usare per ```New-CsOnlinePstnGateway```l'impostazione dei parametri.

|Obbligatorio?|Nome|Descrizione|Predefinita|Valori possibili|Tipo e restrizioni|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sì|FQDN|Nome FQDN di SBC |Nessuno|Nome NoneFQDN, limite di 63 caratteri|Stringa, elenco dei caratteri consentiti e non consentiti nelle [convenzioni di denominazione in Active Directory per computer, domini, siti e unità organizzative](https://support.microsoft.com/help/909264)|
|No|MediaBypass |Il parametro indicato da SBC supporta il bypass multimediale e l'amministratore vuole usarlo.|Nessuno|True<br/>False|Boolean|
|Sì|SipSignallingPort |Porta di ascolto usata per comunicare con i servizi di routing diretto usando il protocollo Transport Layer Security (TLS).|Nessuno|Qualsiasi porta|da 0 a 65535 |
|No|FailoverTimeSeconds |Se impostato su 10 (valore predefinito), le chiamate in uscita non risposte dal gateway entro 10 secondi vengono instradate al successivo trunk disponibile. Se non sono presenti trunk aggiuntivi, la chiamata viene automaticamente eliminata. In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente. Il valore predefinito è 10.|10|Numero|Int|
|No|ForwardCallHistory |Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk. Se abilitata, il proxy PSTN di Office 365 invia due intestazioni: History-info e riferimento. Il valore predefinito è **false** ($false). |False|True<br/>False|Boolean|
|No|ForwardPAI|Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante. Se è abilitata anche l'intestazione privacy: ID verrà inviata. Il valore predefinito è **false** ($false).|False|True<br/>False|Boolean|
|No|SendSIPOptions |Definisce se un SBC riceverà o non invierà le opzioni SIP. Se disabilitato, SBC verrà escluso dal sistema di monitoraggio e avviso. Ti consigliamo vivamente di abilitare le opzioni SIP. Il valore predefinito è **true**. |True|True<br/>False|Boolean|
|No|MaxConcurrentSessions |Usato da Alerting System. Quando viene impostato un valore qualsiasi, il sistema di avviso genera un avviso per l'amministratore del tenant quando il numero di sessione simultanea è pari a 90% o superiore a questo valore. Se il parametro non è impostato, gli avvisi non vengono generati. Tuttavia, il sistema di monitoraggio riporterà il numero di sessioni simultanee ogni 24 ore. |Null|Null<br/>1-100.000 ||
|No|MediaRelayRoutingLocationOverride |Consente di selezionare manualmente il percorso per elementi multimediali. Il routing diretto assegna un Data Center per il percorso multimediale basato sull'IP pubblico di SBC. Selezionare sempre più vicino al Data Center SBC. Tuttavia, in alcuni casi un IP pubblico da ad esempio un intervallo degli Stati Uniti può essere assegnato a un SBC situato in Europa. In questo caso useremo un percorso di supporto non ottimale. Questo parametro consente di impostare manualmente l'area preferita per il traffico multimediale. È consigliabile impostare questo parametro solo se i registri delle chiamate indicano chiaramente che l'assegnazione automatica del Data Center per il percorso multimediale non assegna il più vicino al Data Center SBC. |Nessuno|Codici paese in formato ISO||
|No|Abilitata|Usato per abilitare questo SBC per le chiamate in uscita. Può essere usato per rimuovere temporaneamente il SBC, mentre viene aggiornato o durante la manutenzione. |False|True<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Verificare l'associazione di SBC 

Verificare la connessione: 
- Verificare se il controllo SBC è nell'elenco di SBCs associati. 
- Convalidare le opzioni SIP. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificare se SBC è nell'elenco di SBCs associati 

Dopo avere associato il controllo SBC, verificare che l'SBC sia presente nell'elenco di SBCs associati eseguendo il comando seguente in una sessione remota di PowerShell:`Get-CSOnlinePSTNGateway`

Il gateway associato deve essere visualizzato nell'elenco come illustrato nell'esempio seguente e verificare che il parametro **Enabled** visualizzi il valore **true**. Immettere

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Che restituisce:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Convalidare il flusso delle opzioni SIP 

Per convalidare l'associazione con le opzioni SIP in uscita, usare l'interfaccia di gestione SBC e verificare che SBC riceva le risposte OK di 200 ai messaggi delle opzioni in uscita.

Quando il routing diretto Visualizza le opzioni in arrivo, inizierà a inviare messaggi di opzioni SIP in uscita all'FQDN SBC configurato nel campo dell'intestazione del contatto nel messaggio delle opzioni in arrivo. 

Per convalidare l'associazione con le opzioni SIP in arrivo, usare l'interfaccia di gestione SBC e verificare che il SBC invii una risposta ai messaggi delle opzioni provenienti da routing diretto e che il codice di risposta inviato sia 200 OK.

## <a name="enable-users-for-direct-routing-service"></a>Abilitare gli utenti per il servizio di routing diretto 

Quando si è pronti per abilitare gli utenti per il servizio di routing diretto, eseguire le operazioni seguenti: 

1. Creare un utente in Office 365 e assegnare una licenza per il sistema telefonico. 
2. Verificare che l'utente sia ospitato in Skype for business online. 
3. Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica. 
4. Configurare il routing vocale. La route viene convalidata automaticamente.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Creare un utente in Office 365 e assegnare la licenza 

Esistono due opzioni per la creazione di un nuovo utente in Office 365. Tuttavia, è consigliabile che l'organizzazione selezioni e usi un'opzione per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud. Vedere [integrare le directory locali con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Creare l'utente direttamente nel portale di amministrazione di Office 365. Vedere [aggiungere utenti singolarmente o in blocco a Office 365-Guida per gli amministratori](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se la distribuzione di Skype for business online è condivisa con Skype for business 2015 o Lync 2010/2013 in locale, l'unica opzione supportata consiste nel creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1). 

Licenze obbligatorie: 

- Office 365 Enterprise E3 (inclusi SfB Plan2, Exchange Plan2 e teams) + sistema telefonico
- Office 365 Enterprise E5 (inclusi SfB Plan2, Exchange Plan2, teams e Phone System) 

Licenze facoltative: 

- Piano per le chiamate 
- Audioconferenza 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Verificare che l'utente sia ospitato in Skype for business online 

Il routing diretto richiede che l'utente sia ospitato in Skype for business online. Puoi controllare questo aspetto esaminando il parametro RegistrarPool. Deve avere un valore nel dominio infra.lync.com.

1. Connettersi a PowerShell remoto.
2. Emettere il comando: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica 

Dopo aver creato l'utente e assegnato una licenza, il passaggio successivo consiste nel configurare il proprio numero di telefono e la segreteria telefonica. Questa operazione può essere eseguita in un solo passaggio. 

Per aggiungere il numero di telefono e abilitare per la segreteria telefonica:
 
1. Connettersi a una sessione remota di PowerShell. 
2. Immettere il comando: 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer low", è necessario immettere quanto segue: 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Il numero di telefono usato deve essere configurato come numero di telefono E. 164 completo con prefisso nazionale. 

  > [!NOTE]
  > Se il numero di telefono dell'utente viene gestito in locale, USA Skype for Business Management Shell locale o pannello di controllo per configurare il numero di telefono dell'utente. 

### <a name="configure-voice-routing"></a>Configurare il routing vocale 

Microsoft Phone System include un meccanismo di routing che consente di inviare una chiamata a un SBC specifico in base a: 

- Modello di numero definito 
- Nome modello numero + utente specifico che effettua la chiamata
 
SBCs può essere designato come attivo e backup. Questo significa che quando l'SBC configurato come attivo per il modello di numero o il modello numerico + un utente specifico non è disponibile, le chiamate verranno instradate a un SBC di backup.
 
Il routing delle chiamate è costituito dagli elementi seguenti: 
- Criteri di routing vocale: contenitore per gli usi PSTN; può essere assegnato a un utente o a più utenti 
- Usi PSTN: contenitore per le route vocali ed usi PSTN; possono essere condivisi in criteri di routing vocale diversi 
- Route vocali: modello numerico e set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde al modello 
- Il gateway PSTN online-puntatore a un SBC, memorizza anche la configurazione applicata quando la chiamata viene inserita tramite SBC, ad esempio forward P-Asserted-Identity (PAI) o codec preferiti; può essere aggiunto alle route vocali 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Creazione di un criterio di routing vocale con un solo utilizzo PSTN 

Il diagramma seguente mostra due esempi di criteri di routing vocale nel flusso delle chiamate.

**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non sono disponibili né sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene eliminata. 

**Chiamata flusso 2 (a destra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene prima indirizzata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non è disponibile alcun SBC, verrà provata la route con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz). Se nessuna delle SBCs è disponibile, la chiamata viene eliminata. 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In entrambi gli esempi, mentre la route vocale è assegnata alle priorità, il SBCs nelle route viene provato in ordine casuale.

  > [!NOTE]
  > A meno che l'utente non disponga anche di una licenza per il piano di chiamata Microsoft, le chiamate a qualsiasi numero eccetto i numeri corrispondenti ai pattern + 1 425 XXX XX XX o + 1 206 XXX XX XX nella configurazione di esempio vengono eliminati. Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del piano di chiamata Microsoft. 

Il piano di chiamate Microsoft si applica automaticamente come ultima route a tutti gli utenti con la licenza per il piano di chiamata Microsoft e non richiede ulteriori configurazioni di routing delle chiamate.

Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri americani e canadesi (chiamate che vanno alla sequenza numerica chiamata + 1 XXX XXX XX XX).

![Mostra i criteri di routing vocale con una terza Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica. Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, passare tramite il piano di chiamata Microsoft.

Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.

  > [!NOTE]
  > Il valore di priorità per la route "altro + 1" non ha importanza in questo caso, in quanto esiste una sola route che corrisponde al modello + 1 XXX XXX XX XX. Se un utente effettua una chiamata a + 1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene eliminata.

La tabella seguente riepiloga la configurazione usando tre route vocali. In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN "Stati Uniti e Canada".

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Solo Stati Uniti|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo Stati Uniti|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo Stati Uniti|"Altro + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|||||||

Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo PSTN è associato ai criteri di routing vocale "solo Stati Uniti". In questo esempio, il criterio di routing vocale viene assegnato all'utente Spencer low.

#### <a name="examples-of-call-routes"></a>Esempi di route di chiamata

Nell'esempio seguente viene illustrato come configurare le route, gli utilizzi PSTN e i criteri di routing e assegnare i criteri all'utente.

**Passaggio 1:** Creare l'utilizzo PSTN "Stati Uniti e Canada".

In una sessione remota di PowerShell per Skype for business digitare:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Verificare che l'utilizzo sia stato creato immettendo: 
```
Get-CSOnlinePSTNUsage
``` 
Che restituisce un elenco di nomi che possono essere troncati:
```
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
Nell'esempio seguente puoi vedere il risultato del comando `(Get-CSOnlinePSTNUsage).usage` Esegui PowerShell per visualizzare i nomi completi (non troncati).

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Passaggio 2:** In una sessione di PowerShell in Skype for business online, creare tre Route: Redmond 1, Redmond 2 e altre + 1, come descritto nella tabella precedente. 

Per creare la route "Redmond 1", immettere:

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Che restituisce:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Per creare la route Redmond 2, immettere:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Per creare l'altra route + 1, immettere:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Verificare che l'espressione regolare nell'attributo NumberPattern sia valida. Puoi testarlo usando questo sito Web:[https://www.regexpal.com](https://www.regexpal.com)

In alcuni casi è necessario instradare tutte le chiamate allo stesso SBC; usare-NumberPattern ". *"

Instradare tutte le chiamate allo stesso SBC.

```
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Verificare di aver configurato correttamente la route eseguendo il comando di `Get-CSOnlineVoiceRoute` PowerShell usando le opzioni come illustrato:

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Che dovrebbe restituire:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

Nell'esempio, la route "altro + 1" è stata assegnata automaticamente la priorità 4. 

**Passaggio 3:** Creare un criterio di routing vocale "solo Stati Uniti" e aggiungere al criterio l'utilizzo PSTN "Stati Uniti e Canada".

In una sessione di PowerShell in Skype for business online digitare:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Il risultato è illustrato in questo esempio:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Passaggio 4:** Concedere a user Spencer un criterio di routing vocale basso usando PowerShell.

In una sessione di PowerShell in Skype for business online digitare:

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Convalidare l'assegnazione dei criteri immettendo questo comando:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Che restituisce:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Creazione di un criterio di routing vocale con diversi usi PSTN

Il criterio di routing vocale creato in precedenza consente solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che l'utente non venga assegnato anche alla licenza per il piano di chiamata Microsoft.

Nell'esempio seguente puoi creare il criterio di routing vocale "nessuna restrizione". Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creati nell'esempio precedente, nonché il nuovo utilizzo PSTN "internazionale". 

Questo instrada tutte le altre chiamate a SBCs sbc2.contoso.biz e sbc5.contoso.biz. Gli esempi illustrati assegnano il criterio US only all'utente "Spencer low" e nessuna restrizione per l'utente "John Woods".

Spencer Low: le chiamate sono consentite solo ai numeri US e canadesi. Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBC. I numeri non Stati Uniti non verranno instradati, a meno che non venga assegnata all'utente la licenza per il piano chiamante.

John Woods-chiamate consentite a qualsiasi numero. Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBC. I numeri non US verranno instradati tramite sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra il criterio di routing vocale assegnato all'utente Spencer low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica. Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, passare tramite il piano di chiamata Microsoft.

Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.

![Mostra il criterio di routing vocale assegnato all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Nella tabella seguente vengono riepilogati i criteri di routing "nessuna restrizione" denominazioni di utilizzo e route vocali. 

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Solo Stati Uniti|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Route attiva per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo Stati Uniti|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Solo Stati Uniti|"Altro + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Route per i numeri dei chiamanti + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|Internazionale|Internazionale|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route per qualsiasi modello di numero |


  > [!NOTE]
  > - L'ordine degli usi PSTN nei criteri di routing vocale è fondamentale. Gli usi vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati. L'utilizzo PSTN "internazionale" deve essere posizionato dopo l'uso PSTN "solo USA". Per modificare l'ordine degli usi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" prima e "internazionale" in secondo luogo, eseguire l'ordine inverso:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorità per le route vocali "altro + 1" e "internazionale" viene assegnata automaticamente. Gli utenti non hanno importanza se hanno priorità più basse rispetto a "Redmond 1" e "Redmond 2".

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Esempio di criteri di routing vocale per l'utente John Woods

La procedura per creare l'utilizzo PSTN "internazionale", la route vocale "internazionale", "criteri di routing vocale" senza restrizioni "e quindi l'assegnazione all'utente" John Woods "è la seguente.


**Passaggio 1**: creare l'utilizzo PSTN "internazionale". 

In una sessione remota di PowerShell in Skype for business online, immettere:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Passaggio 2**: creare la nuova route vocale "internazionale".

```
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Che restituisce:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Passaggio 3**: creare un criterio di routing vocale "nessuna restrizione". 

L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

Prendere nota dell'ordine degli usi PSTN:

un. Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale. La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

b. Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing. Immettere il comando:

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

Che restituisce

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**Passaggio 4**: assegnare il criterio di routing vocale all'utente "John Woods" usando il comando seguente.

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Verificare quindi l'assegnazione usando il comando: 

```
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Che restituisce:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare la modalità solo team agli utenti per garantire la destinazione delle chiamate in Microsoft Teams

Il routing diretto richiede che gli utenti siano in modalità solo teams per garantire la terra delle chiamate in arrivo nel client teams. Per inserire gli utenti solo in modalità teams, assegna loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Se l'organizzazione usa Skype for Business Server o Skype for business online, vedere l'articolo seguente per l'interoperabilità delle informazioni tra Skype e teams: [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurazione dell'invio di chiamate direttamente alla segreteria telefonica

Il routing diretto consente di terminare la chiamata a un utente e di inviarla direttamente alla segreteria telefonica degli utenti. Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque = app: voicemail all'intestazione dell'URI della richiesta. Ad esempio, "SIP: user@yourdomain. com; opaque = app: voicemail".
In questo caso, l'utente del team non riceverà la notifica chiamante, la chiamata verrà connessa direttamente alla segreteria telefonica dell'utente.

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>Tradurre i numeri chiamante e chiamato per le chiamate in uscita e in ingresso in un formato alternativo

Talvolta gli amministratori del tenant potrebbero voler cambiare il chiamante o il numero di telefono per le chiamate in uscita e/o in entrata in base agli schemi creati per garantire l'interoperabilità con SBCs. È possibile impostare un criterio per la conversione dei numeri per tradurre il chiamante o i numerati dei chiamanti in un formato alternativo. È possibile usare i criteri per tradurre i numeri per i seguenti:

- Chiamate in ingresso: chiamate da un endpoint PSTN (chiamante) a un client di Teams (chiamato).
- Chiamate in uscita: chiamate da un client di Teams (chiamante) a un endpoint PSTN (chiamato).

Il criterio viene applicato a livello SBC. È possibile assegnare più regole di traduzione a un SBC, che vengono applicate nell'ordine in cui vengono visualizzate durante l'elenco in PowerShell. È anche possibile modificare l'ordine delle regole nel criterio.

Per creare, modificare, visualizzare ed eliminare le regole di manipolazione dei numeri, usare i cmdlet New-CsTeamsTranslationRule, set-CsTeamsTranslationRule, Get-CsTeamsTranslationRule e Remove-CsTeamsTranslationRule.

Per assegnare, configurare e modificare le regole di manipolazione dei numeri in SBCS, usare i cmdlet [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) insieme ai ```InboundTeamsNumberTranslationRules```parametri ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```,,, e ```OutboundPSTNNumberTranslationRulesList``` .

### <a name="examples"></a>Esempi

#### <a name="example-sbc-configuration"></a>Configurazione SBC di esempio

Per gli scenari di esempio, eseguiamo ```New-CsOnlinePSTNGateway``` il cmdlet per creare la configurazione SBC seguente.

```
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Nella tabella seguente vengono riepilogate le regole di traduzione assegnate a SBC.

|Nome  |Modello |Conversione  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+ 1 $1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

In questi scenari di esempio ci sono due utenti, Alice e Roberto. Alice è un utente di teams e il suo numero è + 1 206 555 0100. Roberto è un utente PSTN e il suo numero è + 1 425 555 0100.

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Esempio 1: chiamata in ingresso a un numero a dieci cifre

Roberto chiama Alice usando un numero di dieci cifre diverso da E. 164. Bob compone 2065550100 per raggiungere Alice.
SBC USA 2065550100 in RequestURI e in Headers e 4255550100 nell'intestazione from.

|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:2065550100@sbc.contoso.com|INVITARE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|A    |A: \<SIP:2065550100@sbc.contoso.com>|A: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|Da   |DA: \<SIP:4255550100@sbc.contoso.com>|DA: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>Esempio 2: chiamata in ingresso a un numero a quattro cifre

Roberto chiama Alice usando un numero a quattro cifre. Bob compone 0100 per raggiungere Alice.
SBC USA 0100 in RequestURI e in Headers e 4255550100 nell'intestazione from.

|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:0100@sbc.contoso.com          |INVITARE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|A    |A: \<SIP:0100@sbc.contoso.com>|A: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|Da   |DA: \<SIP:4255550100@sbc.contoso.com>|DA: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Esempio 3: chiamata in uscita con un numero non E. 164 a dieci cifre

Alice chiama Roberto usando un numero a dieci cifre. Alice compone 425 555 0100 per raggiungere Bob.
SBC è configurato per l'uso di numeri di dieci cifre diversi da E. 164 sia per i team che per gli utenti PSTN.

In questo scenario, un dial plan converte il numero prima di inviarlo all'interfaccia Direct routing. Quando Alice immette 425 555 0100 nel client teams, il numero viene convertito in + 14255550100 tramite il dial plan paese. I numeri risultanti sono una normalizzazione cumulativa delle regole del dial plan e della traduzione di teams. Le regole di traduzione di teams eliminano il "+ 1" aggiunto dal dial plan.

|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:+14255550100@sbc.contoso.com          |INVITARE sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|A    |A: \<SIP:+14255550100@sbc.contoso.com>|A: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|Da   |DA: \<SIP:+12065550100@sbc.contoso.com>|DA: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Esempio 4: chiamata in uscita con un numero non E. 164 a quattro cifre

Alice chiama Roberto usando un numero a quattro cifre. Alice USA 0100 per raggiungere Roberto da chiamate o tramite un contatto.
SBC è configurato per l'uso di numeri a quattro cifre non E. 164 per gli utenti di team e per i numeri a dieci cifre per gli utenti PSTN. Il dial plan non viene applicato in questo scenario.

|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:0100@sbc.contoso.com           |INVITARE sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|A    |A: \<SIP:0100@sbc.contoso.com>|A: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Da   |DA: \<SIP:+12065550100@sbc.contoso.com>|DA: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)
