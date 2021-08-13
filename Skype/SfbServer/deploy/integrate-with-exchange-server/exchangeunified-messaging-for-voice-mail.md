---
title: Configurare Exchange Server messaggistica unificata per Skype for Business Server segreteria telefonica
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Riepilogo: configurare Exchange Server messaggistica unificata per Skype for Business Server segreteria telefonica.'
ms.openlocfilehash: 7a963fc7220e5865976c2f4159f84c2dba31ffb0f58b642c011f97cdeacf976f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319479"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurare Exchange Server messaggistica unificata per Skype for Business Server segreteria telefonica
 
**Riepilogo:** Configurare Exchange Server messaggistica unificata per la Skype for Business Server vocale.
  
Skype for Business Server consente di avere messaggi di segreteria telefonica archiviati in Exchange Server 2016 o Exchange Server 2013; tali messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cartelle Posta in arrivo degli utenti. 

> [!NOTE]
> Exchange La messaggistica unificata come nota in precedenza non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare Sistema telefonico per registrare i messaggi di segreteria telefonica e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
  
Se è già stata configurata l'autenticazione da server a server tra Skype for Business Server e Exchange Server 2016 o Exchange Server 2013, è possibile configurare la messaggistica unificata. A tale scopo, è necessario innanzitutto creare e assegnare un nuovo dial plan di messaggistica unificata nel Exchange Server. Ad esempio, questi due comandi (eseguiti da Exchange Management Shell) configurano un nuovo dial plan a 3 cifre per Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnalazione è crittografato utilizzando TRANSPORT Layer Security (TLS). Il parametro URIType "SipName" indica che i messaggi verranno inviati e ricevuti tramite il protocollo SIP e il valore 1 per CountryOrRegionCode indica che il dial plan si applica agli Stati Uniti.
  
Nel secondo comando il valore di parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica quali gruppi nazionali è possibile utilizzare con questo dial plan. Il valore del parametro "Anywhere, \* , , " imposta quanto \* \* segue:
  
- Nome gruppo
    
- AllowedNumberString ( \* , un carattere jolly che indica che qualsiasi stringa numerica è consentita)
    
- DialNumberString ( \* , un carattere jolly che indica che qualsiasi numero composto è consentito)
    
- TextComment ( \* , un carattere jolly che indica che qualsiasi comando di testo è consentito)
    
> [!NOTE]
> La creazione di un nuovo dial plan creerà anche un criterio cassetta postale predefinito. 
  
Dopo aver creato e configurato il nuovo dial plan, è necessario aggiungerlo al server di messaggistica unificata, quindi impostare la modalità di avvio su "Doppio". È possibile eseguire entrambe queste attività da Exchange Management Shell:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Dopo aver configurato il server messaggistica unificata, è necessario eseguire il cmdlet Enable-ExchangeCertificate per assicurarsi che il certificato Exchange sia applicato al servizio di messaggistica unificata:
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Dopo avere assegnato correttamente il certificato, è quindi necessario arrestare e riavviare il servizio MsExchangeUM sul server di messaggistica unificata. È necessario arrestare e riavviare il servizio ogni volta che si modifica la modalità di avvio.
  
Al termine della configurazione del server di messaggistica unificata, è quindi possibile configurare il Router chiamate di messaggistica unificata:
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Dato che la modalità di avvio è stata modificata, è necessario arrestare e riavviare il servizio MsExchangeUMCR nel computer che ospita il router chiamate di messaggistica unificata.
  
Per completare l'impostazione della messaggistica unificata, è quindi necessario creare criteri di cassetta postale di messaggistica unificata e utilizzare tali criteri per abilitare la messaggistica unificata per gli utenti. È possibile creare criteri di cassetta postale tramite un comando simile al seguente:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

È possibile abilitare la messaggistica unificata per un utente tramite un comando simile al seguente:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Nel comando precedente, il parametro Extensions rappresenta il numero di interno telefonico dell'utente. In questo esempio l'utente ha l'interno 100.
  
Dopo averne abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di utilizzare la messaggistica unificata di Exchange. È possibile verificare che l'utente possa connettersi Exchange messaggistica unificata eseguendo il cmdlet [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) da Skype for Business Server Management Shell:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se è presente un secondo utente per cui è stata abilitata la messaggistica unificata, è possibile utilizzare il cmdlet [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) per verificare che possa lasciare un messaggio della segreteria telefonica per il primo utente.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurazione della messaggistica unificata in Microsoft Exchange Server 
> [!IMPORTANT]
> Se si desidera utilizzare la messaggistica unificata di Exchange per fornire servizi di risposta alle chiamate, Outlook Voice Access o operatore automatico per gli utenti di VoIP aziendale, vedere [Plan for Exchange Unified Messaging integration in Skype for Business e quindi](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)seguire le istruzioni in questa sezione. 

Per configurare Exchange messaggistica unificata per l'utilizzo VoIP aziendale messaggistica unificata, è necessario eseguire le attività seguenti:

- Configurare i certificati nel server che esegue Exchange di messaggistica unificata
  > [!NOTE]
  > Aggiungere tutti i server Accesso client e Cassette postali a tutti i dial plan URI SIP di messaggistica unificata. In caso contrario, il routing delle chiamate in uscita non funzionerà come previsto. 
- Creare uno o più dial plan URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del sottoscrittore, in base alle esigenze, e quindi creare i dial plan L corrispondenti.

- Utilizzare lo script exchucutil.ps1 per:
    - Creare gateway IP di messaggistica unificata.
    - Creare gruppi di risposta di messaggistica unificata.
    - Concedere Skype for Business Server autorizzazioni per la lettura degli oggetti servizi di dominio Active Directory di messaggistica unificata.
- Creare un oggetto operatore automatico di messaggistica unificata.
- Creare un oggetto di accesso sottoscrittore.
- Creare un URI SIP per ogni utente e associare gli utenti a un dial plan URI SIP di messaggistica unificata.

### <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

Prima di iniziare, nella documentazione di questa sezione si presuppone che siano stati distribuiti i ruoli Exchange seguenti: Accesso client e Cassetta postale. In Microsoft Exchange Server, Exchange messaggistica unificata viene eseguita come servizio in questi server.

Tenere inoltre presente quanto segue:
- Se Exchange la messaggistica unificata è installata in più foreste, è necessario eseguire i Exchange Server di integrazione per ogni foresta di messaggistica unificata. Inoltre, ogni foresta di messaggistica unificata deve essere configurata per considerare attendibile la foresta in cui viene distribuito Skype for Business Server e la foresta in cui viene distribuitoSkype for Business Server deve essere configurata per considerare attendibile ogni foresta di messaggistica unificata.
- I passaggi di integrazione vengono eseguiti sia sui ruoli Exchange Server in cui sono in esecuzione i servizi di messaggistica unificata che sul server che esegue Skype for Business Server. È consigliabile eseguire i Exchange Server di integrazione della messaggistica unificata prima di eseguire la procedura di integrazione di Lync Server 2013.
  > [!NOTE]
  > Per vedere quali passaggi di integrazione vengono eseguiti sui server e con quali ruoli di amministratore, vedere [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Gli strumenti seguenti devono essere disponibili in ogni server che esegue Exchange messaggistica unificata:
- Exchange Management Shell
- Script exchucutil.ps1, che consente di eseguire le attività seguenti:
    - Crea un gateway IP di messaggistica unificata per ogni Skype for Business Server.
    - Creazione di un gruppo di risposta per ogni gateway. L'identificatore pilota di ogni gruppo di risposta specifica il dial plan URI SIP di messaggistica unificata utilizzato dal pool Front End o dal server edizione Standard associato al gateway.
    - Concede Skype for Business Server autorizzazioni di lettura Exchange oggetti di messaggistica unificata in Servizi di dominio Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurare la messaggistica unificata in Microsoft Exchange con ExchUCUtil.ps1 

Durante l'integrazione di Microsoft Skype for Business Server con Exchange messaggistica unificata, è necessario eseguire lo script di ExchUcUtil.ps1 in Shell. Lo script ExchUcUtil.ps1 esegue quanto indicato di seguito:

- Crea un gateway IP di messaggistica unificata per ogni pool Skype for Business Server di messaggistica unificata.

> [!IMPORTANT]
> Lo script ExchUcUtil.ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita su tutti i gateway IP di messaggistica unificata, ad eccezione di quello creato dallo script. Questo comprende la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. 

- Crea un gruppo di risposta di messaggistica unificata per ciascun gateway IP di messaggistica unificata. L'identificatore pilota di ogni gruppo di risposta specifica il dial plan URI SIP di messaggistica unificata utilizzato dal pool Front End di Skype for Business Server o dal server edizione Standard associato al gateway IP di messaggistica unificata.
- Concede Skype for Business Server autorizzazioni per leggere gli oggetti contenitore di messaggistica unificata di Active Directory, ad esempio dial plan di messaggistica unificata, operatori automatici, gateway IP di messaggistica unificata e gruppi di risposta di messaggistica unificata.
  > [!IMPORTANT]
  > Ogni foresta di messaggistica unificata deve essere configurata per considerare attendibile la foresta in cui viene distribuito Skype for Business Server e la foresta in cui viene distribuito Skype for Business Server 2013 deve essere configurata per considerare attendibile ogni foresta di messaggistica unificata. Se Exchange messaggistica unificata è installata in più foreste, è necessario eseguire i passaggi di integrazione Exchange Server per ogni foresta di messaggistica unificata oppure è necessario specificare il Skype for Business Server dominio. Ad esempio, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Utilizzo di Shell per l'esecuzione dello script ExchUcUtil.ps1

Eseguire lo script ExchUcUtil.ps1 in qualsiasi server Exchange dell'organizzazione nella stessa topologia di Skype for Business Server. È possibile eseguire lo script da un server Cassette postali utilizzando Shell oppure utilizzando Windows PowerShell remoto su un server Accesso client. Se si esegue lo script su un server Accesso client dell'organizzazione, tale server inoltrerà la sessione di Windows PowerShell remoto a un server Cassette postali dell'organizzazione.
> [!IMPORTANT]
> Lo script ExchUcUtil.ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita su tutti i gateway IP di messaggistica unificata, ad eccezione di quello creato dallo script. Questo comprende la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. Per disabilitare le chiamate in uscita su un gateway IP di messaggistica unificata, vedere Disabilitare le chiamate in uscita sui gateway IP di messaggistica unificata.[!IMPORTANT]
> Per eseguire lo script, è necessario disporre delle autorizzazioni del ruolo Exchange Organization Management o essere membri del gruppo di sicurezza Exchange Organization Administrators. 

1. Aprire Exchange Management Shell.
2. Al prompt C:\Windows\System32 digitare **cd \<drive letter> :\Programmi\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** e quindi premere INVIO.

#### <a name="how-do-you-know-this-worked"></a>Verifica dell'esito positivo dell'operazione

Per verificare che lo script ExchUcUtul.ps1 sia stato eseguito correttamente, procedere come segue:
- Utilizzare il cmdlet Get-UMIPGateway o l'interfaccia di amministrazione di Exchange per visualizzare il nuovo gateway IP di messaggistica unificata o i gateway che sono stati creati.
- Utilizzare il cmdlet Get-UMHuntGroup o l'interfaccia di amministrazione di Exchange per visualizzare il nuovo gruppo di risposta di messaggistica unificata o i gruppi che sono stati creati.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurare i certificati nel server che esegue Exchange Server messaggistica unificata
 
Se è stata distribuita la messaggistica unificata di Exchange, come descritto in Planning for Exchange Unified Messaging integration in Skype for Business Server nella documentazione relativa alla pianificazione e si desidera fornire funzionalità di messaggistica unificata Exchange agli utenti di VoIP aziendale nell'organizzazione, è possibile utilizzare le procedure seguenti per configurare il certificato nel server che esegue la messaggistica unificata di Exchange.

> [!IMPORTANT]
> Per i certificati interni, sia i server che eseguono Skype for Business Server che i server che eseguono Microsoft Exchange devono disporre di certificati di autorità radice attendibili reciprocamente attendibili. L'Autorità di certificazione (CA) può essere la stessa o un'autorità di certificazione diversa, purché i server presentino il certificato radice dell'autorità di certificazione registrato nell'archivio certificati dell'autorità radice attendibile. 

Il Exchange Server deve essere configurato con un certificato server per connettersi a Skype for Business Server:
1. Scaricare il certificato CA per Exchange Server.
2. Installare il certificato CA per Exchange Server.
3. Verificare che la CA sia inclusa nell'elenco delle CA radice attendibili di Exchange Server.
4. Creare una richiesta di certificato per Exchange Server e installare il certificato. 
5. Assegnare il certificato per Exchange Server.


**Per scaricare il certificato CA:**

1. Nel server che esegue Exchange messaggistica unificata, fare clic sul pulsante **Start** **,** scegliere Esegui , **digitare http:// \<name of your Issuing CA Server> /certsrv** e quindi fare clic su **OK**.
2. In Selezionare un'attività fare clic **su Scarica un certificato CA, una catena di certificati o un CRL.**
3. In **Download a CA Certificate, Certificate Chain o CRL** selezionare Encoding Method to Base **64** e quindi fare clic su **Download CA certificate**.
   > [!NOTE]
   > È inoltre possibile specificare Distinguished Encoding Rules (DER) in questo passaggio. Se si seleziona la codifica DER, il tipo di file nel prossimo passaggio e nel passaggio 10 di **Per installare il certificato CA** è .p7b anziché .cer. 
4. Nella finestra di dialogo **Download file** fare clic su **Salva** e quindi salvare il file nel disco rigido del server. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio precedente.

**Per installare il certificato CA:**

1. Nel server che esegue Exchange messaggistica unificata, aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui,** **digitando mmc** nella casella Apri e quindi facendo clic su **OK**.
2. Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.
3. Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.
4. Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.
5. Nella finestra **di dialogo** Seleziona computer verificare che la casella di controllo Computer **locale: (il computer** in cui è in esecuzione la console) sia selezionata e quindi fare clic su **Fine**.
6. Fare clic su **Chiudi** e quindi su **OK**. 
7. Nell'albero della console espandere **Certificati (computer locale)**, espandere **Autorità di certificazione radice attendibili** e quindi fare clic su **Certificati**.
8. Fare clic con il pulsante destro del mouse su **Certificati**, scegliere **Tutte le attività** e quindi **Importa**.
9. Fare clic su **Avanti**. 
10. Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **Per scaricare il certificato CA**.
11. Fare **clic su Inserisci tutti i** certificati nel seguente archivio.
12. Fare clic su **Sfoglia** e quindi selezionare **Autorità di certificazione radice attendibili**. 
13. Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **Fine**. 


**Per verificare che l'autorità di certificazione sia presente nell'elenco delle CA radice attendibili:**

1. Nel server che esegue Exchange messaggistica unificata, in MMC espandere Certificati (computer locale), espandere Autorità di certificazione radice attendibili e quindi fare clic su Certificati.
2. Nel riquadro dei dettagli verificare che la CA sia inclusa nell'elenco delle CA attendibili.