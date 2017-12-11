---
title: "Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente"
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
- Strat_SB_PSTN
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente

Un ID conferenza viene assegnato automaticamente ad un utente quando gli ID vengono configurati per le conferenza con accesso esterno utilizzando Microsoft come provider. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla conferenza al momento della pianificazione della conferenza stessa. 
  
Gli ID statici vengono utilizzati nei casi in cui si preferisce non dover ricordare un numero casuale ogni volta, quando si preferisce selezionare un numero specifico o semplicemente se si preferisce avere un numero facile da ricordare. Quando si utilizzano ID dinamici per le conferenze, l'utente riceverà un ID conferenza univoco per ogni riunione pianificata. Se si desidera assegnare ID conferenza dinamici, piuttosto che statici, [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Sebbene un ID conferenza statico verrà creato e assegnato ad un utente automaticamente, in alcuni casi un utente potrebbe desiderare un numero diverso oppure potrebbe non ricordare più il suo ID conferenza. Utilizzando l'interfaccia di amministrazione di Skype for Business e Windows PowerShell sarà possibile visualizzare, modificare e ripristinare l'ID conferenza.
  
All'utente verrà inviato un messaggio di posta elettronica con l'ID conferenza e i numeri di telefono predefiniti per i servizi di conferenza telefonica con accesso esterno. Se invece reimposti l'ID conferenza, verrà inviato un altro messaggio di posta elettronica che includerà l'ID conferenza ma non il PIN. 
  
## 

### Per visualizzare l'ID conferenza

È possibile visualizzare gli ID conferenza e inviarli agli utenti.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**> **Servizi di conferenza telefonica con accesso esterno**, nell'elenco degli utenti, scegli l'utente che ha bisogno dell'ID conferenza. 
    
4. Nella pagina Azione, individua **ID conferenza**.
    
    > [!TIP]
    > Facendo clic su **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **Utenti connessi con chiamata in ingresso**, puoi inviare all'utente tutte le informazioni conferenza in un messaggio di posta elettronica che contiene l'ID conferenza e i numeri di telefono per l'accesso esterno. 
  
    Per utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente, esegui:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Per ulteriori informazioni sul cmdlet, vedi [Get-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617693 ).
    
### Per assegnare o modificare l'ID conferenza

È possibile assegnare o modificare un ID conferenza per un utente nel caso in cui, ad esempio, l'utente desideri un ID facile da ricordare.
  
> [!NOTE]
> Non puoi usare l'interfaccia di amministrazione di Skype for Business per modificare un ID conferenza creato automaticamente, ma puoi utilizzare Windows PowerShell per modificare o sostituire un ID conferenza impostato manualmente. 
  
- Per modificare o sostituire l'ID conferenza per un utente, esegui:
    
    > [!TIP]
    >  Un ID conferenza deve contenere 7 cifre e non può essere modificato nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.
  
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

### Per ripristinare l'ID conferenza

È possibile ripristinare un ID conferenza per un utente nel caso in cui, ad esempio, l'utente lo abbia dimenticato.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**> **Servizi di conferenza telefonica con accesso esterno**, nella pagina Azioni, sezione **ID conferenza**, fai clic su **Reimposta**.
    
4. Nella finestra **Reimpostare l'ID conferenza?** fai clic su **Sì**. L'ID conferenza viene creato automaticamente e comunicato all'utente tramite e-mail.
    
    Puoi reimpostare l'ID conferenza per un utente usando Windows PowerShell. A tale scopo, esegui:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## Quali altre informazioni devi conoscere?

-     > [!IMPORTANT]
    >  Dopo aver creato o ripristinato un ID conferenza, il vecchio ID non potrà più essere utilizzato. È importante ricordare agli utenti di ripianificare gli inviti alla riunine esistenti, per essere sicuri che il nuovo ID conferenza venga comunicato a tutti. Per aggiornare le riunioni esistenti, gli utenti potranno utilizzare lo strumento di migrazione delle riunioni Skype for Business . Per informazioni sul download, sull'installazione e sull'esecuzione dello strumento, vedere:> [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](http://go.microsoft.com/fwlink/?LinkID=626046)
  
- Per ulteriori informazioni sul cmdlet, vedi [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- L'ID conferenza deve soddisfare la lunghezza in cifre impostata nel bridge di conferenza telefonica con accesso esterno. Negli ID conferenza non puoi usare né caratteri dell'alfabeto né caratteri speciali, ma solo numeri.
    
- L'ID conferenza per tutti gli utenti di conferenza telefonica con accesso esterno deve contenere sette cifre per impostazione predefinita. Inoltre, il numero di cifre non può variare.
    
- Se l'utente passa dal provider di conferenza telefonica con accesso esterno Microsoft a un provider di servizi di audioconferenza di terze parti o se il provider di conferenza telefonica con accesso esterno è impostato su **Nessuno**, l'ID conferenza smetterà di funzionare. Vedi [Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md) oppure[Modificare il provider di servizi di conferenza telefonica con accesso esterno per gli utenti](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e).
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Vedere anche

#### 

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

