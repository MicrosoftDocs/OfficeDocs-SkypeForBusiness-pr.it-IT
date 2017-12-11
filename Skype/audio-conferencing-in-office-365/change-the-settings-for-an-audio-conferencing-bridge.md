---
title: "Modificare le impostazioni per un bridge per audioconferenza"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
---

# Modificare le impostazioni per un bridge per audioconferenza

Quando configuri i servizi di audioconferenza in Office 365, riceverai numeri di telefono per gli utenti da un bridge per audioconferenze o con accesso esterno. Un bridge di conferenza può contenere uno o più numeri di telefono, utilizzati quando i chiamanti accedono a una riunione tramite telefono. I numeri sono riportati nella parte inferiore dell'invito a una riunione Skype for Business o Microsoft Teams.
  
Il bridge di conferenza risponde a una chiamata con comandi vocali di un operatore automatico. Quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa in assenza di una app Skype for Business o Microsoft Teams.
  
> [!IMPORTANT]
> Il PIN è necessario solo per l'organizzatore della riunione se un utente della app Skype for Business o Microsoft Teams non ha già avviato la riunione. Se tutti gli utenti accedono alla riunione con un telefono, il PIN è necessario per consentire l'avvio della riunione da parte dell'organizzatore. 
  
## Modificare le impostazioni per un bridge per audioconferenza

 **Impostare l'esperienza della riunione quando i chiamanti vi partecipano**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Impostazioni bridge Microsoft**.
    
4. Nella pagina **Impostazioni bridge Microsoft**, in **Esperienza di partecipazione a una riunione** seleziona:
    
  - **Consenti attivazione notifiche di accesso e uscita da una riunione** Questa opzione è selezionata per impostazione predefinita. Se la deselezioni, gli utenti che hanno già eseguito l'accesso alla riunione non ricevono una notifica quando qualcuno entra o esce dalla riunione.
    
    Quando selezioni **Abilita l'attivazione delle notifiche di entrata e uscita dalla riunione** puoi selezionare queste opzioni dall'elenco **Tipo di annuncio di entrata-uscita**:
    
  - **Nomi o numeri di telefono** Quando un utente accede a una riunione, il suo numero di telefono viene riprodotto quando un utente si unisce alla riunione.
    
  - **Toni** Quando un utente accede a una riunione con accesso esterno, viene riprodotto un tono audio quando un utente si unisce alla riunione.
    
    > [!NOTE]
    > L'uso di **Toni** come tipo di annuncio è attualmente disponibile per tutti i clienti come funzione di anteprima.
  
  - **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se la deselezioni, ai chiamanti non sarà richiesto di registrare il proprio nome prima di partecipare a una riunione.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
 **Impostare la lunghezza dei PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Impostazioni bridge Microsoft**.
    
4. Nella pagina **Impostazioni bridge Microsoft**, alla voce **Sicurezza**, inserisci il numero di cifre desiderato per il PIN in **Lunghezza PIN** e quindi fai clic su **Salva**.
    
    > [!IMPORTANT]
    > Il PIN deve contenere tra 4 e 12 cifre. 
  
 **Specificare se inviare un messaggio e-mail agli utenti**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Impostazioni bridge Microsoft**.
    
4. Nella pagina **Impostazioni bridge Microsoft** seleziona o deseleziona la casella **Invia automaticamente messaggi di posta elettronica agli utenti in caso di modifiche alla configurazione delle audioconferenze** e quindi fai clic su **Salva**.
    
    Vedi [Messaggi che vengono automaticamente inviati agli utenti quando modificare le impostazioni di conferenze Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md) per maggiori informazioni.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per rendere automatica la procedura o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché usare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## Vedere anche

#### 

[Servizi di conferenza telefonica con accesso esterno in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

