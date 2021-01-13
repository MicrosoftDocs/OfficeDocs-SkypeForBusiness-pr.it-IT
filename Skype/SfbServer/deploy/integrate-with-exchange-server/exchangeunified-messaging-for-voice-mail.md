---
title: Configurare la messaggistica unificata di Exchange Server per la segreteria telefonica di Skype for Business Server
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
description: 'Riepilogo: configurare la messaggistica unificata di Exchange Server per la segreteria telefonica di Skype for Business Server.'
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834036"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurare la messaggistica unificata di Exchange Server per la segreteria telefonica di Skype for Business Server
 
**Riepilogo:** Configurare la messaggistica unificata di Exchange Server per la segreteria telefonica di Skype for Business Server.
  
Skype for Business Server consente di archiviare i messaggi in segreteria telefonica in Exchange Server 2016 o Exchange Server 2013; i messaggi vocali verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti. 

> [!NOTE]
> La messaggistica unificata di Exchange come precedentemente nota non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare il sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente. Per ulteriori informazioni, vedere [Plan cloud Voicemail Service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Se è già stata configurata l'autenticazione da server a server tra Skype for Business Server e Exchange Server 2016 o Exchange Server 2013, si è pronti per l'installazione della messaggistica unificata. A tale scopo, è necessario innanzitutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange. Ad esempio, questi due comandi (eseguiti dall'interno di Exchange Management Shell) configurano un nuovo dial plan a tre cifre per Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnalazione è crittografato tramite TLS (Transport Layer Security). Il parametro URIType "SipName" indica che i messaggi verranno inviati e ricevuti tramite il protocollo SIP e il valore 1 per CountryOrRegionCode indica che il dial plan si applica agli Stati Uniti.
  
Nel secondo comando il valore di parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica quali gruppi nazionali è possibile utilizzare con questo dial plan. Il valore del parametro "Anywhere \* , \* , \* " consente di impostare gli elementi seguenti:
  
- Nome gruppo
    
- AllowedNumberString ( \* un carattere jolly che indica che è consentita una stringa di numero qualsiasi)
    
- DialNumberString ( \* un carattere jolly che indica che è consentito qualsiasi numero composto)
    
- TextComment ( \* un carattere jolly che indica che è consentito qualsiasi comando di testo)
    
> [!NOTE]
> Se si crea un nuovo dial plan, verrà creato anche un criterio cassetta postale predefinito. 
  
Dopo aver creato e configurato il nuovo dial plan, è necessario aggiungerlo al server di messaggistica unificata, quindi impostare la modalità di avvio su "Doppio". È possibile eseguire entrambe queste attività dall'interno di Exchange Management Shell:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Dopo aver configurato il server Messaggistica unificata, è necessario eseguire il cmdlet Enable-ExchangeCertificate per assicurarsi che il certificato di Exchange venga applicato al servizio di messaggistica unificata:
  
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
  
Dopo averne abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di utilizzare la messaggistica unificata di Exchange. È possibile verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) da Skype for Business Server Management Shell:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se è presente un secondo utente per cui è stata abilitata la messaggistica unificata, è possibile utilizzare il cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) per verificare che possa lasciare un messaggio della segreteria telefonica per il primo utente.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurazione della messaggistica unificata in Microsoft Exchange Server 
> [!IMPORTANT]
> Se si desidera utilizzare la messaggistica unificata di Exchange per fornire i servizi di risponditore automatico, Outlook Voice Access o operatori automatici per gli utenti di VoIP aziendale, leggere [piano per l'integrazione della messaggistica unificata di Exchange in Skype for business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)e quindi seguire le istruzioni riportate in questa sezione. 

Per configurare la messaggistica unificata di Exchange in modo che funzioni con VoIP aziendale, è necessario eseguire le attività seguenti:

- Configurare i certificati nel server che esegue i servizi di messaggistica unificata di Exchange
  > [!NOTE]
  > Aggiungere tutti i server Accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata. In caso contrario, il routing delle chiamate in uscita non funzionerà come previsto. 
- Creare uno o più dial plan URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare i dial plan di L corrispondenti.

- Utilizzare lo script exchucutil.ps1 per:
    - Creare gateway IP di messaggistica unificata.
    - Creare gruppi di risposta di messaggistica unificata.
    - Concedere l'autorizzazione Skype for Business Server per leggere gli oggetti di servizi di dominio Active Directory di messaggistica unificata.
- Creare un oggetto operatore automatico di messaggistica unificata.
- Creare un oggetto di accesso sottoscrittore.
- Creare un URI SIP per ogni utente e associare gli utenti a un dial plan URI SIP di messaggistica unificata.

### <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange seguenti: accesso client e cassetta postale. In Microsoft Exchange Server, la messaggistica unificata di Exchange viene eseguita come servizio su questi server.

Tenere inoltre presente quanto segue:
- Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire i passaggi di integrazione di Exchange Server per ogni foresta di messaggistica unificata. Inoltre, ogni foresta di messaggistica unificata deve essere configurata per considerare attendibile la foresta in cui è distribuito Skype for Business Server e la foresta in whichSkype for Business Server è distribuita affinché consideri attendibile ogni foresta di messaggistica unificata.
- I passaggi di integrazione vengono eseguiti sui ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e sul server che esegue Skype for Business Server. È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.
  > [!NOTE]
  > Per sapere quali passaggi di integrazione vengono eseguiti su quali server e quali ruoli di amministratore, vedere  [Deployment Process Overview per l'integrazione della messaggistica unificata locale e Skype for business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Gli strumenti seguenti devono essere disponibili in ogni server che esegue la messaggistica unificata di Exchange:
- Exchange Management Shell
- Script exchucutil.ps1, che consente di eseguire le attività seguenti:
    - Crea un gateway IP di messaggistica unificata per ogni server Skype for business.
    - Creazione di un gruppo di risposta per ogni gateway. L'identificatore pilota di ogni gruppo di risposta specifica il dial plan URI SIP di messaggistica unificata utilizzato dal pool Front end o dal server Standard Edition associato al gateway.
    - Concede l'autorizzazione di Skype for Business Server alla lettura degli oggetti di messaggistica unificata di Exchange in servizi di dominio Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurare la messaggistica unificata in Microsoft Exchange con ExchUCUtil.ps1 

Quando si sta integrando Microsoft Skype for Business Server con la messaggistica unificata di Exchange, è necessario eseguire lo script ExchUcUtil.ps1 in Shell. Lo script ExchUcUtil.ps1 esegue quanto indicato di seguito:

- Crea un gateway IP di messaggistica unificata per ogni pool di Skype for Business Server.

> [!IMPORTANT]
> Lo script ExchUcUtil.ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita su tutti i gateway IP di messaggistica unificata, ad eccezione di quello creato dallo script. Questo comprende la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. 

- Crea un gruppo di risposta di messaggistica unificata per ciascun gateway IP di messaggistica unificata. L'identificatore pilota di ogni gruppo di risposta specifica il dial plan di messaggistica unificata URI SIP utilizzato dal pool Front End di Skype for Business Server o dal server Standard Edition associato al gateway IP di messaggistica unificata.
- Concede l'autorizzazione di Skype for Business Server alla lettura di oggetti contenitore di messaggistica unificata di Active Directory, ad esempio dial plan, operatori automatici, gateway IP di messaggistica unificata e gruppi di risposta di messaggistica unificata.
  > [!IMPORTANT]
  > Ogni foresta di messaggistica unificata deve essere configurata per considerare attendibile la foresta in cui è distribuito Skype for Business Server e la foresta in cui è distribuito Skype for Business Server 2013 deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata. Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire la procedura di integrazione di Exchange Server per ogni foresta di messaggistica unificata oppure è necessario specificare il dominio Skype for Business Server. Ad esempio, ExchUcUtil.ps1-Forest: <Lync-domain-controller-FQDN>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Utilizzo di Shell per l'esecuzione dello script ExchUcUtil.ps1

Eseguire lo script ExchUcUtil.ps1 su qualsiasi server Exchange dell'organizzazione che si trova nella stessa topologia di Skype for Business Server. È possibile eseguire lo script da un server Cassette postali utilizzando Shell oppure utilizzando Windows PowerShell remoto su un server Accesso client. Se si esegue lo script su un server Accesso client dell'organizzazione, tale server inoltrerà la sessione di Windows PowerShell remoto a un server Cassette postali dell'organizzazione.
> [!IMPORTANT]
> Lo script ExchUcUtil.ps1 crea uno o più gateway IP di messaggistica unificata. È necessario disabilitare le chiamate in uscita su tutti i gateway IP di messaggistica unificata, ad eccezione di quello creato dallo script. Questo comprende la disabilitazione delle chiamate in uscita sui gateway IP di messaggistica unificata creati prima dell'esecuzione dello script. Per disabilitare le chiamate in uscita su un gateway IP di messaggistica unificata, vedere Disabilitare le chiamate in uscita sui gateway IP di messaggistica unificata. 
> [!IMPORTANT]
> Per eseguire lo script, è necessario disporre delle autorizzazioni del ruolo Exchange Organization Management o essere membri del gruppo di sicurezza Exchange Organization Administrators. 

1. Aprire Exchange Management Shell.
2. Al prompt di C:\Windows\System32 digitare **CD \<drive letter> : \Program c:\Programmi\Microsoft\Exchange Server\V15\Scripts # C0.ExchUcUtil.ps1** e quindi premere INVIO.

#### <a name="how-do-you-know-this-worked"></a>Verifica dell'esito positivo dell'operazione

Per verificare che lo script ExchUcUtul.ps1 sia stato eseguito correttamente, procedere come segue:
- Utilizzare il cmdlet Get-UMIPGateway o l'interfaccia di amministrazione di Exchange per visualizzare il nuovo gateway IP di messaggistica unificata o i gateway che sono stati creati.
- Utilizzare il cmdlet Get-UMHuntGroup o l'interfaccia di amministrazione di Exchange per visualizzare il nuovo gruppo di risposta di messaggistica unificata o i gruppi che sono stati creati.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurare i certificati nel server che esegue la messaggistica unificata di Exchange Server
 
Se la messaggistica unificata di Exchange è stata distribuita, come descritto in pianificazione dell'integrazione della messaggistica unificata di Exchange in Skype for Business Server nella documentazione relativa alla pianificazione e si desidera fornire le funzionalità di messaggistica unificata di Exchange agli utenti di VoIP aziendale nell'organizzazione, è possibile utilizzare le procedure seguenti per configurare il certificato sul server che esegue la messaggistica unificata di Exchange.

> [!IMPORTANT]
> Per i certificati interni, entrambi i server che eseguono Skype for Business Server e i server che eseguono Microsoft Exchange devono disporre di certificati attendibili per l'autorità radice che sono mutuamente attendibili. L'autorità di certificazione (CA) può essere la stessa o un'autorità di certificazione diversa, purché i server dispongano del certificato radice dell'autorità di certificazione registrata nell'archivio certificati dell'autorità radice attendibile. 

Il server di Exchange deve essere configurato con un certificato del server per connettersi a Skype for Business Server:
1. Scaricare il certificato CA per Exchange Server.
2. Installare il certificato CA per Exchange Server.
3. Verificare che la CA sia inclusa nell'elenco delle CA radice attendibili di Exchange Server.
4. Creare una richiesta di certificato per Exchange Server e installare il certificato. 
5. Assegnare il certificato per Exchange Server.


**Per scaricare il certificato CA:**

1. Nel server che esegue la messaggistica unificata di Exchange, fare clic sul pulsante **Start**, scegliere **esegui**, digitare **http:// \<name of your Issuing CA Server> /certsrv** e quindi fare clic su **OK**.
2. In selezionare un'attività fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.
3. In **Scarica un certificato CA, una catena di certificati o un CRL selezionare il** **metodo di codifica su base 64** e quindi fare clic su **Scarica certificato CA**.
   > [!NOTE]
   > È inoltre possibile specificare la codifica DER (Distinguished Encoding Rules) in questo passaggio. Se si seleziona la codifica DER, il tipo di file nel prossimo passaggio e nel passaggio 10 di **Per installare il certificato CA** è .p7b anziché .cer. 
4. Nella finestra di dialogo **Download file** fare clic su **Salva** e quindi salvare il file nel disco rigido del server. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio precedente.

**Per installare il certificato CA:**

1. Nel server che esegue la messaggistica unificata di Exchange, aprire Microsoft Management Console (MMC) facendo clic sul pulsante **Start**, scegliendo **Esegui**, digitando **MMC** nella casella Apri e quindi facendo clic su **OK**.
2. Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File** e quindi fare clic su **Aggiungi**.
3. Nella casella **Aggiungi snap-in autonomo** fare clic su **Certificati** e quindi su **Aggiungi**.
4. Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.
5. Nella finestra di dialogo **Seleziona computer** verificare che sia selezionata la casella di controllo computer **locale (il computer su cui è in esecuzione questa console)** e quindi fare clic su **fine**.
6. Fare clic su **Chiudi** e quindi su **OK**. 
7. Nell'albero della console espandere **Certificati (computer locale)**, espandere **Autorità di certificazione radice attendibili** e quindi fare clic su **Certificati**.
8. Fare clic con il pulsante destro del mouse su **Certificati**, scegliere **Tutte le attività** e quindi **Importa**.
9. Fare clic su **Avanti**. 
10. Fare clic su **Sfoglia** per individuare il file e quindi fare clic su **Avanti**. Il file avrà estensione cer o p7b, a seconda della codifica selezionata nel passaggio 3 di **Per scaricare il certificato CA**.
11. Fare clic su **colloca tutti i certificati** nel seguente archivio.
12. Fare clic su **Sfoglia** e quindi selezionare **Autorità di certificazione radice attendibili**. 
13. Fare clic su **Avanti** per verificare le impostazioni e quindi fare clic su **Fine**. 


**Per verificare che l'autorità di certificazione sia presente nell'elenco delle autorità di certificazione radice attendibili:**

1. Nel server che esegue la messaggistica unificata di Exchange, in MMC espandere certificati (computer locale), espandere Autorità di certificazione radice attendibili e quindi fare clic su certificati.
2. Nel riquadro dei dettagli verificare che la CA sia inclusa nell'elenco delle CA attendibili.


