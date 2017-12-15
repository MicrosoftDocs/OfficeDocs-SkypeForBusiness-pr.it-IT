---
title: "Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente"
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente

Il PIN è un codice numerico creato per ciascun utente abilitato per i servizi di conferenza telefonica con accesso esterno. Il PIN di conferenza telefonica con accesso esterno viene utilizzato dall'organizzatore della riunione per dimostrare di essere l'organizzatore della riunione e poter avviare una riunione tramite telefono. Se per avviare la riunione l'organizzatore utilizza il client Skype for Business, non è necessario il PIN. Se un utente dimentica il PIN e non è in grado di risalirvi tramite il messaggio di posta elettronica ricevuto al momento dell'abilitazione per i servizi di conferenza telefonica con accesso esterno, l'amministratore dovrà reimpostare il PIN. Un utente non può reimpostare il proprio PIN.
  
Le riunioni possono iniziare quando un utente autenticato partecipa utilizzando un client Skype for Business o quando l'organizzatore partecipa con il proprio PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.
  
## 

### Reimpostare il PIN dell'organizzatore della conferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all' **interfaccia di amministrazione di Office 365** > **Skype for Business** e nella barra di spostamento sinistra fai clic su **Conferenza telefonica con accesso esterno**
    
3. Fai clic su **Utenti connessi con chiamata in ingresso** e seleziona l'utente per cui desideri reimpostare il PIN.
    
4. Nel riquadro Azioni fai clic su **Reimposta PIN**.
    
## Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN. Dopo la reimpostazione del PIN da parte dell'amministratore, il PIN sarà visualizzato come *********** nell'interfaccia di amministrazione di Skype for Business e nei risultati quando si utilizza **Get-CsCsOnlineDialInConfencingUser** in Windows PowerShell.
    
- L'invio automatico dei messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN al momento dell'abilitazione per i servizi di conferenza telefonica con accesso esterno o della reimpostazione del PIN. Se invece disabiliti l'invio automatico dei messaggi di posta elettronica, all'utente non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e dovrai inviare manualmente all'utente le informazioni relative al PIN.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita non consente a un chiamante anonimo di avviare una riunione.
    
- Quando viene abilitato per i servizi di conferenza telefonica con accesso esterno, per impostazione predefinita l'utente riceverà messaggi di posta elettronica con informazioni conferenza e il PIN. L'utente deve disporre di una cassetta postale di Office 365, perché quando il PIN viene reimpostato, all'utente verrà inviato un nuovo PIN tramite messaggio di posta elettronica all'indirizzo SMTP primario (alias) impostato per l'utente.
    
- Quando configuri la conferenza telefonica con accesso esterno, devi impostare le cifre necessarie per il PIN nell'organizzazione. I PIN possono contenere da 4 a 12 cifre. La lunghezza predefinita è di 5 cifre. Se modifichi l'impostazione relativa alla lunghezza del PIN, l'impostazione verrà applicata solo ai nuovi PIN generati e non agli utenti esistenti abilitati per i servizi di conferenza telefonica con accesso esterno. Vedi [Impostare la lunghezza del PIN per le riunioni di conferenze Audio](set-the-length-of-the-pin-for-audio-conferencing-meetings.md)
    
- Il messaggio di posta elettronica verrà inviato per impostazione predefinita all'indirizzo SMTP primario di Office 365 dell'utente, ma puoi inviare un messaggio di posta elettronica anche a un indirizzo non Office 365, ad esempio Hotmail o MSN. Se usi Windows PowerShell puoi ignorare l'indirizzo di posta elettronica predefinito. Questa opzione è particolarmente utile se gli utenti non dispongono di una cassetta postale di Exchange in Office 365.
    
- Per ignorare l'indirizzo utente predefinito a cui viene inviato il messaggio di posta elettronica, l'amministratore tenant può utilizzare il seguente cmdlet:  `Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"`. È necessario il parametro  _SendEmail_ per ignorare l'indirizzo di posta elettronica dell'utente.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Puoi impostare il PIN per Amos Marble eseguendo:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](http://go.microsoft.com/fwlink/?LinkId=294688)
  

