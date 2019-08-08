---
title: Configurazione della messaggistica unificata di Exchange Server 2013 per la segreteria telefonica di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Riepilogo: configurare la messaggistica unificata di Exchange Server per Skype for Business Server Voice mail.'
ms.openlocfilehash: 514b2159c3836aee4bd6bcfad2b85311280277c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238007"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurazione della messaggistica unificata di Exchange Server 2013 per la segreteria telefonica di Skype for Business Server 2015
 
**Riepilogo:** Configurare la messaggistica unificata di Exchange Server per Skype for Business Server Voice mail.
  
Skype for Business Server consente di archiviare i messaggi della segreteria telefonica in Exchange Server 2016 o Exchange Server 2013; i messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti. 

> [!NOTE]
> La messaggistica unificata di Exchange, come precedentemente nota, non è più disponibile in Exchange 2019, ma è comunque possibile usare il sistema telefonico per registrare i messaggi della segreteria telefonica e quindi abbandonare la registrazione nella cassetta postale di Exchange dell'utente. Per altre informazioni, vedere [pianificare il servizio di segreteria cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Se si è già configurata l'autenticazione da server a server tra Skype for Business Server e Exchange Server 2016 o Exchange Server 2013, si è pronti per configurare la messaggistica unificata. A tale scopo, è necessario prima di tutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange. Ad esempio, questi due comandi (eseguiti da Exchange Management Shell) configurano un nuovo dial plan a 3 cifre per Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnalazione viene crittografato con Transport Layer Security (TLS). URIType "SipName" indica che i messaggi verranno inviati e ricevuti usando il protocollo SIP e il CountryOrRegionCode di 1 indica che il dial plan si applica agli Stati Uniti.
  
Nel secondo comando, il valore del parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica i gruppi in-Country che possono essere usati con questo dial plan. Il valore del parametro "Anywhere\*,\*,\*," imposta le operazioni seguenti:
  
- Nome gruppo ("ovunque")
    
- AllowedNumberString (\*, un carattere jolly che indica che è consentita una stringa di numero qualsiasi)
    
- DialNumberString (\*, un carattere jolly che indica che è consentito qualsiasi numero composto)
    
- TextComment (\*, un carattere jolly che indica che è consentito qualsiasi comando di testo)
    
> [!NOTE]
> La creazione di un nuovo dial plan creerà anche un criterio predefinito per le cassette postali. 
  
Dopo aver creato e configurato il nuovo piano di chiamata, è necessario aggiungere il nuovo dial plan al server Messaggistica unificata e quindi modificare la modalità di avvio del server. in particolare, devi impostare la modalità di avvio su "Dual". È possibile eseguire entrambe le attività dall'interno di Exchange Management Shell:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Dopo aver configurato il server Messaggistica unificata, è consigliabile eseguire il cmdlet Enable-ExchangeCertificate per verificare che il certificato di Exchange venga applicato al servizio di messaggistica unificata:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Dopo che il certificato è stato assegnato correttamente, è necessario arrestare e riavviare il servizio MsExchangeum nel server Messaggistica unificata. Questo servizio deve essere interrotto e riavviato ogni volta che si modifica la modalità di avvio.
  
Dopo aver terminato la configurazione del server Messaggistica unificata, è possibile configurare il router di chiamata di messaggistica unificata:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Poiché la modalità di avvio è cambiata, è necessario interrompere e riavviare il servizio MsExchangeUMCR nel computer che ospita il router di chiamata di messaggistica unificata.
  
Per completare la configurazione della messaggistica unificata, è necessario creare un criterio cassetta postale di messaggistica unificata e quindi usare questo criterio per consentire agli utenti la messaggistica unificata. È possibile creare un criterio cassetta postale usando un comando simile al seguente:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Puoi abilitare un utente per la messaggistica unificata usando un comando simile al seguente:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Nel comando precedente il parametro Extensions rappresenta il numero di interno telefonico per l'utente. In questo esempio l'utente ha il numero di interno 100.
  
Dopo aver abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di usare la messaggistica unificata di Exchange. Puoi verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) da Skype for Business Server Management Shell:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se si ha un secondo utente abilitato per la messaggistica unificata, è possibile usare il cmdlet [test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) per verificare che il secondo utente possa uscire da un messaggio della segreteria telefonica per il primo utente.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurazione della messaggistica unificata in Microsoft Exchange Server 
> [!IMPORTANT]
> Se si vuole usare la messaggistica unificata di Exchange (UM) per fornire risposte alle chiamate, Outlook Voice Access o servizi di operatore automatico per gli utenti di VoIP aziendale, leggere il [piano per l'integrazione della messaggistica unificata di Exchange in Skype for business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)e quindi seguire le istruzioni in questa sezione. 

Per configurare la messaggistica UNIFICAta di Exchange per l'utilizzo di Enterprise Voice, è necessario eseguire le attività seguenti:

- Configurare i certificati nel server che gestisce i servizi di messaggistica UNIFICAta di Exchange
  > [!NOTE]
  > Aggiungere tutti i server di accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata. In caso contrario, il routing delle chiamate in uscita non funziona come previsto. 
- Creare uno o più piani di dial URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare i dial plan di L corrispondenti.

- USA lo script exchucutil. ps1 per:
    - Creare gateway IP di messaggistica unificata.
    - Creare gruppi di risposta di messaggistica unificata.
    - Concedere l'autorizzazione Skype for Business Server per la lettura degli oggetti servizi di dominio Active Directory di messaggistica unificata.
- Creare un oggetto operatore automatico di messaggistica unificata.
- Creare un oggetto di accesso del Sottoscrittore.
- Crea un URI SIP per ogni utente e associa gli utenti a un dial plan di URI SIP di messaggistica unificata.

### <a name="requirements-and-recommendations"></a>Requisiti e suggerimenti

Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange seguenti: accesso client e cassetta postale. In Microsoft Exchange Server la messaggistica unificata di Exchange viene eseguita come servizio in questi server.

Tenere inoltre presente quanto segue:
- Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire la procedura di integrazione di Exchange Server per ogni foresta di messaggistica unificata. Ogni foresta di messaggistica unificata deve inoltre essere configurata in modo da considerare attendibile la foresta in cui è distribuito Skype for Business Server e la distribuzione della foresta in whichSkype for Business Server deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata.
- I passaggi di integrazione vengono eseguiti nei ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e nel server che esegue Skype for Business Server. È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.
  > [!NOTE]
  > Per scoprire quali passaggi di integrazione vengono eseguiti in quali server e per quali ruoli di amministratore, vedere [Panoramica del processo di distribuzione per l'integrazione della messaggistica unificata locale e Skype for business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Gli strumenti seguenti devono essere disponibili in ogni server che gestisce la messaggistica unificata di Exchange:
- Exchange Management Shell
- Lo script exchucutil. ps1, che esegue le attività seguenti:
    - Crea un gateway IP di messaggistica unificata per ogni server Skype for business.
    - Crea un gruppo di ricerca per ogni gateway. L'identificatore pilota di ogni gruppo di ricerca specifica il dial plan URI SIP di messaggistica unificata usato dal pool Front-end o dal server Standard Edition associato al gateway.
    - Concede l'autorizzazione di Skype for Business Server per la lettura degli oggetti della messaggistica unificata di Exchange in servizi di dominio Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurare la messaggistica unificata in Microsoft Exchange con ExchUCUtil. ps1 

Quando si integra Microsoft Skype for Business Server con la messaggistica UNIFICAta di Exchange, è necessario eseguire lo script ExchUcUtil. ps1 nella shell. Lo script ExchUcUtil. ps1 esegue le operazioni seguenti:

- Crea un gateway IP di messaggistica unificata per ogni pool di Skype for Business Server.

> [!IMPORTANT]
> Lo script ExchUcUtil. ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita in tutti i gateway IP di messaggistica unificata eccetto un gateway creato dallo script. Questo include la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. 

- Crea un gruppo di risposta di messaggistica unificata per ogni gateway IP di messaggistica unificata. L'identificatore pilota di ogni gruppo di ricerca specifica il dial plan di URI SIP di messaggistica unificata usato dal pool di front end di Skype for Business Server o dal server Standard Edition associato al gateway IP di messaggistica unificata.
- Concede l'autorizzazione di Skype for Business Server per leggere gli oggetti contenitore di messaggistica unificata di Active Directory, ad esempio i dial plan di messaggistica unificata, gli operatori automatici, i gateway IP di messaggistica unificata e i gruppi di
  > [!IMPORTANT]
  > Ogni foresta di messaggistica unificata deve essere configurata per considerare attendibile la foresta in cui è distribuito Skype for Business Server e la foresta in cui è installato Skype for Business Server 2013 deve essere configurata per considerare attendibile ogni foresta di messaggistica unificata. Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire la procedura di integrazione di Exchange Server per ogni foresta di messaggistica unificata oppure è necessario specificare il dominio di Skype for Business Server. Ad esempio, ExchUcUtil. ps1-Forest: <Lync-domain-controller-FQDN>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Usare la Shell per eseguire lo script ExchUcUtil. ps1

Eseguire lo script ExchUcUtil. ps1 in qualsiasi server Exchange dell'organizzazione nella stessa topologia di Skype for Business Server. Puoi eseguire lo script da un server di cassette postali usando la Shell oppure puoi eseguire lo script usando Windows PowerShell remoto su un server Accesso client. Se si esegue lo script in un server Accesso client dell'organizzazione, il server Accesso client delega la sessione remota di Windows PowerShell a un server di cassette postali dell'organizzazione.
> [!IMPORTANT]
> Lo script ExchUcUtil. ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita in tutti i gateway IP di messaggistica unificata eccetto un gateway creato dallo script. Questo include la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. Per disabilitare le chiamate in uscita in un gateway IP di messaggistica unificata, vedere disabilitare le chiamate in uscita nei gateway IP di messaggistica unificata. 
> [!IMPORTANT]
> Per eseguire lo script, è necessario disporre delle autorizzazioni del ruolo di gestione dell'organizzazione di Exchange o di essere membri del gruppo di sicurezza di Exchange Organization Administrators. 

1. Aprire Exchange Management Shell.
2. Al prompt di C:\Windows\System32 digitare la **lettera \<dell'unità CD>: c:\Programmi\Microsoft\Exchange Server\V15\Scripts>. ExchUcUtil. ps1**e quindi premere INVIO.

#### <a name="how-do-you-know-this-worked"></a>Come si fa a sapere che funziona?

Per verificare che lo script ExchUcUtul. ps1 sia stato completato correttamente, eseguire le operazioni seguenti:
- Utilizzare il cmdlet Get-UMIPGateway o l'interfaccia di Exchange per visualizzare il nuovo gateway IP di messaggistica unificata o i gateway che sono stati creati.
- Usare il cmdlet Get-UMHuntGroup o l'interfaccia di Exchange per visualizzare il nuovo gruppo di risposta di messaggistica unificata creato.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurare i certificati nel server che gestisce la messaggistica unificata di Exchange Server
 
Se è stata distribuita la messaggistica unificata di Exchange, come descritto in pianificazione dell'integrazione della messaggistica unificata di Exchange in Skype for Business Server nella documentazione relativa alla pianificazione e si desidera specificare le caratteristiche di messaggistica unificata di Exchange per gli utenti di VoIP aziendale nella propria organizzazione, è possibile usare le procedure seguenti per configurare il certificato nel server che usa la messaggistica unificata di Exchange.

> [!IMPORTANT]
> Per i certificati interni, sia i server che usano Skype for Business Server che i server che usano Microsoft Exchange devono avere certificati di autorità radice attendibili che sono mutuamente attendibili. L'autorità di certificazione (CA) può essere uguale o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrato nell'archivio certificati dell'autorità radice attendibile. 

Il server di Exchange deve essere configurato con un certificato server per connettersi a Skype for Business Server:
1. Scaricare il certificato CA per il server Exchange.
2. Installare il certificato CA per il server Exchange.
3. Verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili del server Exchange.
4. Creare una richiesta di certificato per il server Exchange e installare il certificato. 
5. Assegnare il certificato per il server Exchange.


**Per scaricare il certificato CA:**

1. Nel server che esegue la messaggistica unificata di Exchange fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http://\<nome del server della CA emittente>/certsrv**e quindi fare clic su **OK**.
2. In selezionare un'attività fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.
3. In **scaricare un certificato CA, una catena di certificati o un CRL**selezionare **metodo di codifica per base 64**e quindi fare clic su**Scarica certificato CA**.
   > [!NOTE]
   > È anche possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio. Se si seleziona la codifica DER, il tipo di file nel passaggio successivo di questa procedura e nel passaggio 10 di **per installare il certificato della CA** è. p7b anziché. cer. 
4. Nella finestra di dialogo **Download file** fare clic su **Salva**e quindi salvare il file nel disco rigido nel server. In base alla codifica selezionata nel passaggio precedente, il file includerà un file con estensione cer o. p7b.

**Per installare il certificato CA:**

1. Nel server che esegue la messaggistica unificata di Exchange aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella Apri e quindi facendo clic su **OK**.
2. Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi fare clic su **Aggiungi**.
3. Nella casella **Add standalone snap-** in fare clic su **certificati**e quindi fare clic su **Aggiungi**.
4. Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.
5. Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.
6. Fare clic su **Chiudi**e quindi su **OK**. 
7. Nell'albero della console espandere **certificati (computer locale)**, espandere **autorità di certificazione radice attendibili**e quindi fare clic su **certificati**.
8. Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**e fare clic su **Importa**.
9. Fare clic su **Avanti**. 
10. Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file includerà un'estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **per scaricare il certificato della CA**.
11. Fare clic su **Inserisci tutti i certificati** nello Store seguente.
12. Fare clic su **Sfoglia**e quindi selezionare **autorità di certificazione radice attendibili**. 
13. Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **fine**. 


**Per verificare che la CA si trovi nell'elenco delle autorità di certificazione radice attendibili:**

1. Nel server che gestisce la messaggistica unificata di Exchange, in MMC Espandi certificati (computer locale), Espandi autorità di certificazione radice attendibili e quindi fai clic su certificati.
2. Nel riquadro dei dettagli verificare che la CA sia nell'elenco delle CA attendibili.


