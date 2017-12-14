---
title: "Risoluzione degli errori di accesso a Skype for Business online per gli amministratori"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Risoluzione degli errori di accesso a Skype for Business online per gli amministratori

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1). 
  
Per risolvere i problemi di accesso Skype for Business online, iniziare eliminando le cause più comuni di difficoltà di accesso. Se necessario, è possibile seguire risoluzione specifica passaggi in base al tipo di errore. Se l'utente non ancora non è possibile accedere, raccogliere ulteriori informazioni e quindi richiedere assistenza.
  
## Per saperne di più
<a name="__top"> </a>

> [Cercare le cause comuni dei problemi di accesso Skype for Business online](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [Eseguire le procedure di risoluzione per un errore specifico (solo Enterprise)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [Aggiungere una voce del firewall per msoidsvc.exe al server proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [Aggiornare le impostazioni DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [Installare un certificato SSL di terze parti nel server ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [Aggiornare le credenziali di sicurezza](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [Modificare le chiavi TrustModelData del Registro di sistema](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Aggiornare le impostazioni utente in Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Usare la guida alla risoluzione dei problemi del supporto tecnico Microsoft](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [Raccogliere ulteriori informazioni e richiedere assistenza](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Cercare le cause comuni dei problemi di accesso Skype for Business online
<a name="__toc323194094"> </a>

Possono tenerne traccia la maggior parte dei problemi di accesso a un numero limitato di cause e molte di queste sono facili da correggere. La tabella seguente elenca alcune cause comuni degli errori di accesso e alcuni passaggi che o da utenti possono eseguire per risolverli.
  
|**Causa possibile**|**Soluzione**|
|:-----|:-----|
|Durante l'accesso, viene visualizzata una finestra di dialogo che contiene la frase seguente: **non riesce a verificare che il server sia attendibile per l'indirizzo di accesso. Connettersi comunque?** <br/> |Verificare che il nome di dominio nella finestra di dialogo sia un server attendibile dell'organizzazione, ad esempio **nomeDominio.contoso.com**. Chiedere all'utente di selezionare la casella di controllo **Considera il server sempre attendibile** e quindi fare clic su **Connetti**. <br/> I clienti aziendali possono disattivare la visualizzazione di questo messaggio quando l'utente accede per la prima volta modificando il Registro di sistema di Windows nel computer di ogni utente. Per informazioni dettagliate, vedere [Modificare le chiavi TrustModelData del Registro di sistema](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry).  <br/> |
|Indirizzo, nome utente o password di accesso digitati in modo non corretto  <br/> | Confermare che nome utente e password di accesso dell'utente siano corretti. <br/>  Verificare che il nome di accesso dell'utente sia formattato nel modo seguente: **utente@contoso.com**. Questo formato potrebbe essere diverso da quello usato per accedere alla rete dell'organizzazione.  <br/>  Chiedere all'utente di provare ad accedere di nuovo. <br/> |
|Password dimenticata  <br/> |Reimpostare la password dell'utente e comunicare la nuova password temporanea.  <br/> |
|Non ha una licenza per l'utilizzo di Skype for Business online  <br/> |Verificare che l'utente è registrato come utente Skype for Business online. In caso contrario, registrare l'utente e quindi chiedere all'utente di accedere di nuovo.  <br/> |
|Versione non corretta di Skype for Business online installato  <br/> |Questo problema è generalmente associato a un messaggio di errore che contiene la frase seguente: **il servizio di autenticazione non è compatibile con questa versione del programma**.  <br/> Chiedere all'utente di disinstallare e reinstallare Skype for Business online dal portale di Office 365.  <br/> |
|Problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso  <br/> |Se l'indirizzo di accesso dell'utente cambiato di recente, potrebbe essere eliminare i dati di accesso memorizzate nella cache. Chiedere agli utenti di eseguire la disconnessione, fare clic su Elimina le informazioni di accesso collegamento nella schermata di accesso e quindi riprovare.  <br/> |
|È stato configurato un nome di dominio personalizzato ed è possibile che le modifiche non siano ancora state propagate in tutto il sistema.  <br/> |Prima di tutto, assicurarsi che siano modificati i record di servizio DNS (Domain Name) per riflettere la modifica.  <br/> Se sono già state apportate le modifiche DNS necessarie, avvisare l'utente di ripetere il tentativo di accesso più tardi. La distribuzione delle modifiche DNS in tutto il sistema può richiedere fino a 72 ore.  <br/> |
|L'orologio di sistema non è sincronizzato con l'orologio del server  <br/> |Verificare che il controller di dominio di rete sia sincronizzato con un'origine di ora esterna affidabile. Per informazioni dettagliate, vedere l'articolo 816042 della Microsoft Knowledge Base [Configurazione di un server di riferimento ora autorevole in Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
[Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità. Per visualizzare la versione inglese dell'articolo, fare clic quihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Per risolvere i problemi di accesso Skype for Business online, iniziare eliminando le cause più comuni di difficoltà di accesso. Se necessario, è possibile seguire risoluzione specifica passaggi in base al tipo di errore. Se l'utente non ancora non è possibile accedere, raccogliere ulteriori informazioni e quindi richiedere assistenza.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Eseguire le procedure di risoluzione per un errore specifico (solo Enterprise)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> Queste istruzioni sono destinate principalmente ai clienti del Piano E di Microsoft Office 365. Se è stato acquistato un Piano P di Office 365, passare alla sezione seguente [Raccogliere ulteriori informazioni e richiedere assistenza](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1). 
  
Se l'utente non riesce ancora ad accedere dopo aver tentato le soluzioni suggerite nella sezione precedente, è possibile eseguire ulteriori interventi di risoluzione dei problemi in base al tipo di errore. Nella tabella seguente sono elencati i messaggi di errore più comuni e le cause possibili. Dopo la tabella sono disponibili procedure dettagliate per ogni problema.
  
|**Messaggio di errore**|**Causa possibile**|**Risoluzione**|
|:-----|:-----|:-----|
|Indirizzo di accesso non trovato  <br/> |Le richieste di accesso dall'Assistente per l'accesso a Microsoft Online Services (msoidsvc.exe) non attraversano il firewall esterno o il server proxy.  <br/> |[Aggiungere una voce del firewall per msoidsvc.exe al server proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|Server temporaneamente non disponibile  <br/> |Se l'organizzazione dispone di un dominio personalizzato, è possibile che le impostazioni DNS (Domain Name System) necessarie non siano disponibili o siano errate.  <br/> |[Aggiornare le impostazioni DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|Server temporaneamente non disponibile  <br/> |Se l'organizzazione usa l'accesso Single Sign-On con Active Directory Federation Services, è possibile che sia stato usato un certificato SSL (Secure Sockets Layer) autofirmato anziché un certificato emesso da un'Autorità di certificazione di terze parti.  <br/> |[Installare un certificato SSL di terze parti nel server ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|Problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso  <br/> |Se già stata rimossa i dati memorizzati nella cache server utilizzati per accedere e l'errore continua a visualizzare le credenziali di sicurezza dell'utente è danneggiate o una cartella RSA nel computer dell'utente non sia bloccato l'autenticazione.  <br/> |[Aggiornare le credenziali di sicurezza](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|Viene visualizzata una finestra di dialogo relativa all'attendibilità del certificato quando un utente accede per la prima volta.  <br/> |Questa finestra di dialogo viene visualizzata se il server Skype for Business non è ancora elencato nella chiave del Registro di sistema **TrustModelData**.  <br/> |[Modificare le chiavi TrustModelData del Registro di sistema](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|Utente non abilitato per SIP  <br/> |Se per l'organizzazione è disponibile un'installazione precedente di Office Communications Server o Microsoft Lync Server 2010, è possibile che gli utenti non siano stati eliminati dal server prima di rimuoverne le autorizzazioni, di conseguenza l'attributo **msRTCSIP-UserEnabled** è ancora impostato su **FALSE** in Servizi di dominio Active Directory. <br/> |[Aggiornare le impostazioni utente in Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### Aggiungere una voce del firewall per msoidsvc.exe al server proxy
<a name="__add_a_firewall"> </a>

Questa procedura è una possibile soluzione per il messaggio di errore seguente: **Indirizzo di accesso non trovato**.
  
 **NOTA**: nei passaggi seguenti si presuppone l'utilizzo di Microsoft Forefront Threat Management Gateway (TMG) 2010. Se si dispone di una diversa soluzione di gateway Web, usare le impostazioni descritte nel passaggio 4 di seguito.
  
Per creare una voce per l'applicazione Msoidsvc.exe in Forefront TMG 2010, eseguire le operazioni seguenti:
  
1. Nel riquadro sinistro di Forefront fare clic su **Networking**.
    
2. Fare clic sulla scheda **Network**. Nella scheda **Tasks** del riquadro destro fare clic su **Configure Forefront TMG Client Settings**.
    
3. Nella finestra di dialogo **Forefront TMG Client Settings** fare clic su **New**.
    
4. Nella finestra di dialogo **Application Entry Setting** configurare le regole seguenti:
    
|****Applicazione****|****Chiave****|****Valore****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Per informazioni dettagliate, vedere l'articolo della Microsoft Knowledge Base 2409256, [che è possibile connettersi a Skype for Business Online perché un firewall locale blocca la connessione](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### Aggiornare le impostazioni DNS
<a name="__update_dns_service"> </a>

Se l'organizzazione dispone di un dominio personalizzato, questa procedura è una possibile soluzione per il messaggio di errore seguente: **Server temporaneamente non disponibile**.
  
- Contattare il registrar per informazioni su come aggiungere il record CNAME seguente al dominio:
    
  - **Tipo di record DNS**: CNAME
    
  - **Nome**: sip
    
  - **Valore/Destinazione**: sipdir.online.microsoft.com
    
Per informazioni dettagliate, vedere l'articolo 2566790 della Microsoft Knowledge Base, [Risoluzione dei problemi di Skype per Business Online DNS i problemi di configurazione di Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)e l'articolo di Office 365 Wiki, [verifica della compatibilità della rete con Skype per le aziende (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
### Installare un certificato SSL di terze parti nel server ADFS
<a name="__verify_upn_and"> </a>

Per installare un certificato SSL di terze parti nel server Active Domain Federation Services (ADFS), eseguire le operazioni seguenti:
  
1. Ottenere un certificato SSL da un'Autorità di certificazione di terze parti come VeriSign o Thawte.
    
2. Installare il certificato nel server ADFS tramite la console di gestione di ADFS.
    
### Aggiornare le credenziali di sicurezza
<a name="__update_security_credentials_1"> </a>

Questa procedura è una possibile soluzione per il messaggio di errore **Si è verificato un problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso**.
  
Per eliminare possibili problemi di certificato o credenziali, rinnovare prima di tutto il certificato dell'utente in Gestione certificati Windows. A tale scopo, eseguire le operazioni seguenti:
  
1. Aprire Gestione certificati Windows. Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **certmgr.msc** e quindi fare clic su **OK**.
    
2. Fare doppio clic su **Personali** e quindi fare doppio clic su **Certificati**.
    
3. Ordinare le informazioni in base alla colonna **Emesso da** e quindi cercare un certificato emesso da Communications Server.
    
4. Fare clic con il pulsante destro del mouse sul certificato e quindi scegliere **Elimina**.
    
Se l'utente esegue Windows 7, rimuovere quindi le credenziali archiviate in Gestione credenziali Windows. A tale scopo, eseguire le operazioni seguenti:
  
1. Fare clic sul pulsante **Start**, scegliere **Pannello di controllo** e quindi fare clic su **Gestione credenziali**.
    
2. Individuare il set di credenziali utilizzato per connettersi a Skype for Business Online.
    
3. Espandere il set di credenziali e quindi fare clic su **Rimuovi dall'insieme di credenziali**.
    
4. Accedere di nuovo e reimmettere le credenziali dell'utente.
    
Infine, se l'utente non riesce ancora ad accedere dopo l'aggiornamento delle credenziali, provare a eliminare la cartella RSA nel computer dell'utente, perché potrebbe impedire il completamento del processo di autenticazione dell'utente:
  
1. Accedere al computer dell'utente con un account di amministratore.
    
2. Se necessario, attivare l'opzione di visualizzazione cartella **Mostra file nascosti**.
    
3. Digitare il percorso seguente nella barra degli indirizzi di Esplora file: **C:\\Documents and Settings\\NomeUtente\\Application Data\\Microsoft\\Crypto\\RSA**, **dove** ** *NomeUtente* ** **è il nome di accesso di Windows**.
    
4. Eliminare le eventuali cartelle con un nome che inizia con **S-1-5-21-** seguito da una stringa di numeri.
    
### Modificare le chiavi TrustModelData del Registro di sistema
<a name="__modify_trustmodeldata_registry"> </a>

Quando un utente accede per la prima volta, potrebbe ricevono una finestra di dialogo che contiene il seguente: **non riesce a verificare che il server sia attendibile per l'indirizzo di accesso. Connettersi comunque?** Questa è una funzionalità di protezione e non un errore. Tuttavia, è possibile impedire la finestra di dialogo utilizzando un oggetto Criteri (gruppo) per aggiornare i computer degli utenti con il nome di dominio prima eseguire l'accesso per la prima volta. A tale scopo, eseguire le operazioni seguenti:
  
- Creare e distribuire un oggetto Criteri di gruppo che aggiunga il nome di dominio Skype for Business, ad esempio nomedominio.contoso.com il valore corrente di hkey_local_machine\\software\\policies\\microsoft\\communicator\\trustmodeldata..
    
> [!IMPORTANT]
> È necessario  *aggiungere*  il nome di dominio al valore esistente e non sostituirlo semplicemente.
  
Per informazioni dettagliate, vedere l'articolo 2531068 della Microsoft Knowledge Base [Skype for Business (Lync) non riesce a verificare che il server sia attendibile per l'indirizzo di accesso](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### Aggiornare le impostazioni utente in Active Directory
<a name="__update_user_settings_1"> </a>

Se per l'organizzazione è disponibile un'installazione precedente di Office Communications Server o Microsoft Lync Server 2010, è possibile che gli utenti non siano stati eliminati dal server prima di rimuoverne le autorizzazioni, di conseguenza l'attributo **msRTCSIP-UserEnabled** è ancora impostato su **FALSE** in Servizi di dominio Active Directory.
  
Per risolvere il problema, eseguire le operazioni seguenti:
  
1. Aggiornare l'attributo **msRTCSIP-UserEnabled** per tutti gli utenti interessati, impostandolo su **TRUE**.
    
2. Eseguire di nuovo lo strumento di sincronizzazione Directory di Microsoft Online Services (DirSync). Per informazioni dettagliate, vedere [Directory AIntegrate propri locali con Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).
    
[Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità. Per visualizzare la versione inglese dell'articolo, fare clic quihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Per risolvere i problemi di accesso Skype for Business online, iniziare eliminando le cause più comuni di difficoltà di accesso. Se necessario, è possibile seguire risoluzione specifica passaggi in base al tipo di errore. Se l'utente non ancora non è possibile accedere, raccogliere ulteriori informazioni e quindi richiedere assistenza.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Usare la guida alla risoluzione dei problemi del supporto tecnico Microsoft
<a name="__toc325626447"> </a>

Se non si riesce ancora a risolvere i problemi di accesso dell'utente, esaminare i suggerimenti descritti nell'articolo della Microsoft Knowledge Base 2541980, [come risolvere i problemi di accesso in Skype for Business Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## Raccogliere ulteriori informazioni e richiedere assistenza
<a name="__collect_more_information_1"> </a>

Se si aver seguito le istruzioni precedenti e ancora non riesce a risolvere i problemi di accesso, è necessario raccogliere informazioni aggiuntive e contattare il supporto tecnico. A tale scopo, procedere come segue:
  
1. Ottenere il file di log e Dettagli registro eventi di Windows dal computer dell'utente. Per istruzioni dettagliate, vedere l'argomento della Guida per gli utenti finali [Informazioni sulla registrazione in Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Inviare al supporto tecnico Microsoft i file di log e le informazioni dettagliate sull'errore:
    
Potrebbero essere richieste ulteriori informazioni diagnostiche installando il Toolkit di supporto Microsoft Online Services Diagnostics and Logging (MOSDAL) nel computer dell'utente interessato. Per ulteriori informazioni, vedere [Uso del Toolkit di supporto MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
[Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità. Per visualizzare la versione inglese dell'articolo, fare clic quihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Per risolvere i problemi di accesso Skype for Business online, iniziare eliminando le cause più comuni di difficoltà di accesso. Se necessario, è possibile seguire risoluzione specifica passaggi in base al tipo di errore. Se l'utente non ancora non è possibile accedere, raccogliere ulteriori informazioni e quindi richiedere assistenza.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

