---
title: "Reimpostare un ID conferenza per un utente"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# Reimpostare un ID conferenza per un utente

Quando le proprie organizzazioni non sono state abilitate per gli ID conferenza dinamici, viene creato automaticamente un ID conferenza statico per le conferenze con accesso esterno, con Microsoft come provider. L'ID conferenza viene inserito in fondo alle convocazioni di riunione Skype for Business online insieme ai numeri di telefono per l'accesso esterno che i chiamanti possono utilizzare per accedere alla riunione. Quando l'utente compone il numero di telefono, l'operatore automatico della riunione richiede di inserire l'ID conferenza per poter partecipare alla riunione.
  
Gli ID statici vengono utilizzati nei casi in cui si preferisce non dover ricordare un numero casuale ogni volta, quando si preferisce selezionare un numero specifico o semplicemente se si preferisce avere un numero facile da ricordare. Quando si utilizzano ID dinamici per le conferenze, l'utente riceverà un ID conferenza univoco per ogni riunione pianificata. Se si desidera assegnare ID conferenza dinamici, piuttosto che statici, [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Gli ID conferenza vengono impostati automaticamente da Skype for Business solo per gli utenti abilitati per i servizi di conferenza telefonica con accesso esterno con Microsoft come provider. Per reimpostare l'ID conferenza di un utente che utilizza un provider di servizi di audioconferenza di terze parti, devi immettere manualmente un ID conferenza nella pagina delle proprietà dell'utente.
  
## Reimpostazione dell'ID conferenza di una riunione per un utente

### Per reimpostare l'ID conferenza di una riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**> **Servizi di conferenza telefonica con accesso esterno**, nella pagina Azioni, sezione **ID conferenza**, fai clic su **Reimposta**.
    
4. Nella finestra **Reimpostare l'ID conferenza?** fai clic su **Sì**. L'ID conferenza viene creato automaticamente e comunicato all'utente tramite e-mail. I messaggi e-mail vengono inviati agli utenti per impostazione predefinita, ma tale opzione più essere disattivata. 
    
    > [!NOTE]
    > Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti. 
  
## Quali altre informazioni sono necessarie?

- Facendo clic su **Invia informazioni conferenza tramite posta elettronica**, puoi inviare all'utente tutte le informazioni relative alla conferenza in un messaggio e-mail che contiene l'ID conferenza e i numeri di telefono per l'accesso esterno. Il PIN non è incluso.
    
- Un ID conferenza conterrà 7 cifre e tale lunghezza non può essere modificata nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- Per visualizzare l'ID conferenza di un utente per un'audioconferenza, osserva la parte inferiore del riquadro Azioni **Servizi di conferenza telefonica con accesso esterno** dopo aver selezionato l'utente nella pagina **Utenti**.
    
- Dopo aver creato un nuovo ID conferenza, quello precedente non può più essere usato dai chiamanti. È consigliabile invitare gli utenti a riconfigurare le convocazioni di riunione attuali, in modo da aggiungervi il nuovo ID conferenza. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per scoprire come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, vedi:
    
  - [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](http://go.microsoft.com/fwlink/?LinkID=626046)
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    

