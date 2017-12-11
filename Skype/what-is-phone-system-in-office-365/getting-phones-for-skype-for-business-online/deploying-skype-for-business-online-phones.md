---
title: "Distribuzione dei telefoni per Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
description: "Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones"
---

# Distribuzione dei telefoni per Skype for Business Online

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](faa17eb3-7483-4984-87f2-815d981b68ae.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/faa17eb3-7483-4984-87f2-815d981b68ae). 
  
Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.
  
In tutti i tipi di azienda, con un numero di telefono consente agli utenti di apportare e ottenere chiamate vocali ed è un requisito importante per intrattengono rapporti commerciali. Gli utenti che dispongono di numeri di telefono sarà possibile effettuare chiamate vocali da tutti i dispositivi Skype for Business inclusi telefoni IP, il PC e dispositivi mobili. È possibile ottenere ulteriori informazioni Skype per i telefoni IP Business leggendo [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
## Fasi della distribuzione di telefoni IP

### Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore

Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.
  
- Per i telefoni Polycom, consulta la [Guida alla distribuzione di Polycom](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl).
    
- Per i telefoni Yealink, vedere [Yealink Skype per Business HD SIP telefoni soluzione](http://www.yealink.com/solution_7.mdl).
    
- Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/products/ems).
    
### Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business.

Skype for Business Online supportati telefono e firmware disponibile compatibile per Skype for Business Server, ma l'operazione non è sempre true. Per assicurarsi che acquistare o il provisioning di un telefono supportato e firmware, vedere [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
### Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario

Controllare la versione del firmware in telefoni. Per:
  
- i **telefoni Polycom VVX**, accedi a **Settings** (Impostazioni) > **Status** (Stato) > **Platform** (Piattaforma) > **Application** (Applicazione) > **Main** (Principale).
    
- i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.
    
- i **telefoni AudioCodes**, accedi a **Menu** > **Device Status** (Stato dispositivo) > **Firmware version** (Versione firmware) dalla schermata iniziale.
    
    > [!NOTE]
    > Per accedere alla Dettagli numero di telefono, fare riferimento alle guide amministrazione produttore. Vedere i collegamenti sopra per l'utente guide e manuali del telefono. 
  
- I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.
    
### Fase 4 - Considerazioni sull'aggiornamento del dispositivo

> [!NOTE]
> Firmware Polycom prima 5.5.1.X aveva un meccanismo di blocco del dispositivo specifiche del produttore che viene sostituito con Skype per l'implementazione di Business "Telefono blocco" L'aggiornamento di un telefono da 5.4.X.X è stato protetto in modo esclusivo "Blocco dispositivo" a 5.5.1.X con "Blocco telefono" non eredita il codice PIN da "Dispositivo blocco" possibile lasciare il telefono non protetto. Gli utenti che sono attivato "Blocco dispositivo" è necessario attivare il parametro Polycom dispositivo profilo seguente offrire agli utenti di controllo del tempo dell'aggiornamento (lync.deviceUpdate.popUpSK.enabled=1). 
  
Aggiornamenti del firmware sono gestiti da di Skype per Business servizio. Ogni Skype per le aziende certified firmware del telefono caricamento di Skype per Business aggiornare server e aggiornamento di dispositivo è stato attivato tutti i telefoni per impostazione predefinita. A seconda il tempo di inattività sul telefono e intervalli di polling telefoni verranno automaticamente scaricare e installare l'ultima versione build certificata. È possibile disattivare le impostazioni di aggiornamento utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e impostando il parametro _EnableDeviceUpdate_ su `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando un nuovo firmware è disponibile e pronto per scaricare e installare, il telefono notifica all'utente. Telefoni Polycom verranno notificare all'utente e fornire un'opzione di **aggiornamento** o **Posticipa**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.
  
> [!CAUTION]
> Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento. 
  
### Passaggio 5 - configurazione e impostazioni del telefono infrastruttura

Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) per i dettagli di questi parametri e impostazioni.
  
Per la pianificazione dell'infrastruttura di rete, vedere [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### Passaggio 6 - preparazione per gli utenti di effettuare l'accesso

Per consentire agli utenti di accedere a Skype for Business Online telefono correttamente ed effettuare chiamate, è necessario assicurarsi che gli utenti vengono assegnati alle licenze corrette. Minimo, sarà necessario assegnare una licenza di sistema telefonico e un piano di chiamata. Per ulteriori informazioni, è possibile visualizzare [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
È possibile trovare ulteriori informazioni sulle chiamate plan di messaggistica unificata leggendo [Cosa sono i Piani per le chiamate in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.
    
  - Verrà visualizzato agli utenti con **Polycom VVX 5XX/6XX** telefoni:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Verrà visualizzato agli utenti con telefoni **Yealink T48G/T46G**:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Per informazioni dettagliate sulle opzioni di accesso è supportate dal produttore, vedere [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come *amosm@contoso.com*  per il nome utente.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner. 
  
- **Con un PC** Se meglio insieme del software Ethernet (BToE) è installato nel computer dell'utente è abilitato, gli utenti possono accedere a sui telefoni mediante la finestra di autenticazione nel loro Skype Windows App for Business. Per altre informazioni, vedere[Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) .
    
    > [!NOTE]
    > Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  *amosm@contoso.com*  per il nome utente.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilizzando un accesso Web**: si tratta di un nuovo metodo per gli utenti Online per l'autenticazione tramite un web browser standard. Gli utenti saranno forniti con un set di istruzioni per eseguire quando si utilizza un browser per accedere.
    
  - Verrà visualizzato agli utenti con **Polycom VVX 5XX/6XX** telefoni:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Verrà visualizzato agli utenti con telefoni **Yealink T48G/T46G**:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Il codice viene generato scadrà 15 minuti. Quando scade, sarà necessario all'utente di scegliere **Riprova** o **OK** per generare un nuovo codice, a seconda del telefono.
    
  - Verrà visualizzato agli utenti con **Polycom VVX 5XX/6XX** telefoni:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Verrà visualizzato agli utenti con telefoni **Yealink T48G/T46G**:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Immetti il codice mostrato sul telefono.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verificare che il sito viene visualizzato "[Nome produttore telefono] **Skype for Business certificata Phone** " e fare clic su **Continua**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando viene visualizzata la pagina seguente, è consigliabile chiudere il browser.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB. 
  
- **Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Metodo di accesso telefono** <br/> |**Skype per l'accesso Business** <br/> |**Accesso Exchange con autorizzazione moderna e MFA disattivate** <br/> |**Accesso Exchange con autorizzazione moderna e MFA attivate** <br/> |
|Online  <br/> |Online  <br/> |Accesso Web  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Online  <br/> |Online  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Accesso Web  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Autenticazione PIN  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
|Locale  <br/> |Online/locale  <br/> |Accesso via PC (BTOE)  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
   
- **Funzioni del telefono** Il set di funzionalità può variare leggermente a seconda del partner telefono IP. Per la caratteristica Completamento imposta e per ulteriori informazioni sulle funzionalità per ogni produttore phone, vedere[Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **Blocca telefono** è una funzionalità introdotta di recente in Skype for Business certificata telefoni che viene utilizzato per proteggere un telefono. Se è attivato, gli utenti verranno chiesto di creare un PIN volta eseguita l'autenticazione. Una volta creato, telefoni consente di bloccare quando scade il timeout inattività definite dall'utente, un utente blocca manualmente il proprio telefono o il blocco di telefono sincronizzare con loro blocco PC utilizzando l'associazione telefono. Se il PIN telefono blocco viene immessa errato più volte, nel telefono verrà Disconnetti l'utente o Richiedi codice dell'amministratore per sbloccare il telefono, ma può variare a seconda del partner telefono. Il PIN dell'utente deve essere compreso tra 6 e 15 cifre.
    
    È possibile disattivare telefono blocco per l'organizzazione (che è attivata per impostazione predefinita), modificare il timeout di inattività e scegliere se gli utenti possono effettuare chiamate telefoniche mentre si trovano le impostazioni inband bloccate o non USA. Per ulteriori informazioni su queste impostazioni, vedere [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) .
    
## Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE è un telefono paining meccanismo per Partner IP telefoni che coppie telefono di un utente con loro Windows Skype per Business App BToE consente agli utenti di:
  
- Accedere al proprio telefono IP con loro Skype per Business app desktop (con un PC)
    
- Sincronizzare telefono blocco con blocco PC
    
- Fare clic su da chiamare
    
BToE può essere configurato per funzionare in due modi:  *manuale*  e *automatico*  (impostazione predefinita). Può inoltre essere abilitata (impostazione predefinita) / disabilitata per gli utenti che utilizzano Skype per le impostazioni in banda Business. Quando si opera in modalità *manuale*  , sarà necessario eseguire un'ulteriore operazione a cui associare il proprio telefono con le app di Windows.
  
 **Per distribuire BToE agli utenti**
  
1. Collegare il PC al telefono utilizzando la porta del PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Scaricare e installare l'ultima versione del software BToE dal sito web del produttore dai link qui sotto. Per una migliore esperienza utente, è possibile distribuire e installare il software BToE utilizzando una soluzione di distribuzione di amministrazione come System Center Configuration Manager (SCCM). Per informazioni sull'utilizzo di SCCM, consulta [Pacchetti e programmi in System Center Configuration Manager](https://docs.microsoft.com/it-it/sccm/apps/deploy-use/packages-and-programs).
    
  - [Sito di Download di Polycom BToE Software](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  - [Download software BToE Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  - [Download software BToE AudioCodes](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
3. Impostazione del server per BToE è impostato su **abilitato** e **la modalità automatica** per impostazione predefinita. Per modificare queste impostazioni, vedere[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE non è attualmente supportato su piattaforme Mac e VDI. 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

