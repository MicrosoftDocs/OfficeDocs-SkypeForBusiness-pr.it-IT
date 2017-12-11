---
title: "Trasferire i numeri di telefono a Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PortingNumbersOverview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e

description: "Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them."
---

# Trasferire i numeri di telefono a Office 365

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](47b3af8e-4171-4dec-8333-c956f108664e.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/47b3af8e-4171-4dec-8333-c956f108664e). 
  
È facile trasferire numeri di telefono dal provider di servizi telefonici attuale a Skype for Business. Dopo il trasferimento dei numeri in Skype for Business, Microsoft diventa il tuo provider di servizi e ti addebita l'uso di tali numeri. 
  
Prima di iniziare il trasferimento numeri di telefono, è consigliabile esaminare le informazioni nelle [Trasferimento di domande comuni i numeri di telefono](transferring-phone-numbers-common-questions.md).Se si dispone di numeri di servizio per le conferenze telefoniche ponti, operatori automatici o altri numeri di servizio, verde numeri o non sono più di 999 numeri di telefono utente (sottoscrittore) che è necessario trasferire Skype for Business, vedere [Inviare manualmente una richiesta di servizio](manually-submit-a-custom-service-request.md) per scaricare le forme corrette e inviarli a Microsoft.
> [!NOTE]
> Siamo elaborare gli ordini di porta per il trasferimento numeri di telefono solo nei giorni lavorativi degli Stati Uniti e non su festività o i fine settimana. 
  
## Come creare un ordine di trasferimento e trasferire i numeri di telefono in Skype for Business
<a name="bk_LNPcountries_1"> </a>

> [!NOTE]
> Se si dispone di numeri di servizio per le conferenze telefoniche ponti, operatori automatici o altri numeri di servizio, verde numeri o non sono più di 999 numeri di telefono utente (sottoscrittore) che è necessario trasferire Skype for Business, vedere [Inviare manualmente una richiesta di servizio](manually-submit-a-custom-service-request.md) per scaricare le forme corrette e inviarli a Microsoft.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella barra di spostamento sinistra, passa a **Voce** > **Ordini di trasferimento** e fai clic su **Aggiungi**.
    
4. Nella pagina **Nuovo ordine di trasferimento di un numero locale**, leggi le informazioni e fai clic su **Inizia**.
    
5. Nella pagina **Informazioni account**, immetti le informazioni seguenti e quindi fai clic su **Avanti**:
    
  - **Numero account** Numero dell'account per il provider di servizi o il gestore.
    
  - **Numero di telefono di fatturazione** deve essere in formato e. 164 (richiede un segno + per anteporre il numero). Ad esempio, per un numero Nord America, utilizzare il formato + 1XXXYYYZZZZ.
    
  - **PIN per sbloccare i numeri** PIN eventualmente richiesto dal provider di servizi o dal gestore corrente.
    
  - **Nome azienda** Nome dell'azienda o dell'organizzazione.
    
    > [!NOTE]
    > Nella casella **Nome azienda** è possibile inserire solo 25 caratteri spazi inclusi. Se il nome dell'azienda è composto da più di 25 caratteri, i primi 25 caratteri del nome verranno inviati e l'ordine di trasferimento verrà comunque elaborato.
  
  - **Utente incaricato dell'autorizzazione** Nome dell'utente autorizzato.
    
    > [!NOTE]
    > Nella casella **Utente incaricato dell'autorizzazione** è possibile inserire solo 15 caratteri spazi inclusi. Se il nome dell'utente incaricato dell'autorizzazione è composto da più di 15 caratteri, i primi 15 caratteri del nome verranno inviati e l'ordine di trasferimento verrà comunque elaborato.
  
  - **Indirizzo del servizio** L'indirizzo del servizio per l'account. È riportato nella fattura del gestore o del provider di servizi.
    
  - **Città**, **Stato**, **CAP** dell'indirizzo del servizio.
    
6. Nella pagina **numeri**, immettere i numeri di telefono che si desidera trasferire in formato e. 164. Ad esempio, per un numero Nord America, utilizzare il formato + 1XXXYYYZZZZ. Separare più numeri di telefono utilizzando un punto e virgola.
    
    > [!NOTE]
    > Se stai eseguendo una portabilità completa, devi includere nell'elenco il numero di telefono di fatturazione. Se stai eseguendo una portabilità parziale, non devi includere nell'elenco il numero di telefono di fatturazione. 
  
    Se stai eseguendo una portabilità completa, seleziona **Intendo trasferire tutti i miei numeri dal mio gestore corrente**. Se stai eseguendo una portabilità parziale, seleziona **Intendo trasferire solo alcuni numeri**. Dopo aver scelto l'opzione corretta, fai clic su **Verifica la portabilità del numero**.
    
7. Fare clic su **procedere**.
    
8. Nella pagina **Data di trasferimento** il **giorno** elenco a discesa, selezionare la data in **ora di inizio** a discesa, selezionare l'ora (EST) e quindi fare clic su **Avanti**.
    
9. Nella pagina **lettera di autorizzazione** selezionare ognuna delle caselle seguenti. Sotto la casella **della firma**, quindi digitare la persona che è autorizzata ad apportare modifiche all'account. Questo è lo stesso nome utilizzato nella pagina **Informazioni sull'Account** > **Authorizing persona**. Fare clic su **Avanti**.
    
10. Nella pagina **Invia** in **altre persone per ricevere una notifica** immettere qualsiasi altro indirizzo di posta elettronica delle persone a cui si vuole e fare clic su **Invia porta ordine**. L'ordine di porta sarà ora elencato nella pagina **porta ordini**. È possibile visualizzare lo stato dell'ordine nella colonna **stato**. È possibile visualizzare i dettagli dell'ordine di porta, ad esempio **ID ordine**, **inviata**, **Data di trasferimento** e **stato**. È possibile visualizzare ulteriori dettagli per l'ordine di porta nel riquadro azioni, tra cui il nome del vettore.
    
## E ora?
<a name="bk_LNPcountries_1"> </a>

Dopo che l'ordine di trasferimento viene inviato e ricevuto, riceverai un'e-mail di verifica dell'ordine. 
  
La richiesta di ordine porta verrà selezionata e aggiornata quotidianamente e si riceverà una notifica del proprio stato e lo stato nel messaggio di posta elettronica. In caso di rifiuto della richiesta, verrà chiesto di aprire un ticket di supporto e in che supporta i ticket che vi chiediamo di fornire **ID ordine porta**. L'ordine di porta ID sono disponibili in Skype for di amministrazione di Business in **segreteria** > **ordini porta** > colonna **ID ordine**.
  
## Cosa fare in caso di problemi?
<a name="bk_LNPcountries_1"> </a>

 **L'indirizzo del servizio non è uguale all'indirizzo di fatturazione. Le informazioni sull'indirizzo inviata sull'ordine corrisponde copia distinta il cliente, perché non ancora accetta?** La maggior parte dei vettori identifica le informazioni portabilità in base alle informazioni di indirizzo del servizio, non l'indirizzo di fatturazione. Poiché una copia distinta è un record di fatturazione, potrebbero non fornire le stesse informazioni come l'indirizzo del servizio per i numeri di telefono vengono trasferiti.
  
 **Cosa deve fare se il mio ordine sta impiegando troppo tempo per elaborare?** Vogliamo portabilità numero per diventare un processo molto semplice e rapido. Se ordine è richiede più tempo del interazione utente è necessario che lo stato ancora non mostra come completato nell'interfaccia di amministrazione di Skype for Business, aprire ticket di supporto e includono l'ordine di porta ID.
  
## 
<a name="bk_LNPcountries_1"> </a>

||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## Argomenti correlati
<a name="bk_LNPcountries_1"> </a>

[Configurare la chiamata plan di messaggistica unificata](set-up-calling-plans.md)
  
[Trasferimento di domande comuni i numeri di telefono](transferring-phone-numbers-common-questions.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

