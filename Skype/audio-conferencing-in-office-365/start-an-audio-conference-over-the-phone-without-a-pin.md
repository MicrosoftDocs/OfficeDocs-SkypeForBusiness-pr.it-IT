---
title: "Avviare un'audioconferenza tramite telefono senza il PIN"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# Avviare un'audioconferenza tramite telefono senza il PIN

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](d5b1f775-d7ed-4d30-853a-1d49f81e8fde.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/d5b1f775-d7ed-4d30-853a-1d49f81e8fde). 
  
Può essere frustrante per gli utenti che accedono a una riunione da mantenere nella sala di attesa della riunione ascoltare musica perché Skype for Business o Microsoft Teams organizzatore della riunione è iniziato la riunione.
  
Se l'organizzatore della riunione chiama la riunione, per impostazione predefinita è necessario un PIN per avviare la riunione. Puoi eseguire la configurazione in modo che tutti possano eseguire l'accesso esterno alla riunione senza specificare un PIN per avviare la riunione. Puoi eseguire la configurazione in modo che un singolo utente o tutti gli utenti connessi con chiamata in ingresso nell'organizzazione possano avviare le riunioni senza un PIN. Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.
  
Se qualcuno ha iniziato alla riunione di Skype per Business o Microsoft Teams app non è necessario per l'organizzatore della riunione un PIN. Il PIN è solo necessaria per l'organizzatore della riunione unisce la riunione su un telefono. Il PIN per le riunioni viene inviato all'utente di connessione quando viene assegnate la licenza di **Conferenze Audio** e abilitati per conferenze audio. Vedere[Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) e[Messaggi che vengono automaticamente inviati agli utenti quando modificare le impostazioni di conferenze Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro passare a **conferenze Audio** > **utenti accesso esterno**.
    
4. Seleziona l'utente nell'elenco e nel riquadro Azioni fai clic su **Modifica**.
    
5. Nella pagina delle proprietà dell'utente, in **Opzioni riunione**, seleziona o deseleziona **Consenti ai chiamanti non autenticati di essere i primi utenti a partecipare a una riunione. In caso contrario, resteranno in sala di attesa finché non esegue l'accesso un utente autenticato**.
    
6. Fare clic su **Salva**.
    
 **Per abilitare o disabilitare i chiamanti anonimi a tutte le riunioni dell'utente usando Windows Powershell**
  
- Esegui il seguente comando: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## Quali altre informazioni devi conoscere?

- Se si desidera reimpostare il PIN, vedere [Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Se è abilitata la funzionalità di accesso anonimo o di avvio della riunione senza il PIN:
    
  - Se la riunione è iniziato (non è non sia visibile nella riunione ancora): un chiamante verrà chiesto se si è l'organizzatore se dice Sì, verrà chiesto per il PIN dopo input he il PIN, di inizio della riunione e l'utente verrà aggiunto alla riunione.
    
  - Se la riunione è già stato avviato (un altro utente è già nella riunione): un chiamante non verrà chiesto se si è l'organizzatore e non verrà mai chiesto il PIN, la riunione è già stata avviata, il chiamante verrà parteciparvi.
    
- Se l'accesso anonimo o che non richiedono un PIN per avviare una riunione è disattivata:
    
  - Se la riunione è iniziato (non è non sia visibile nella riunione ancora): un chiamante non verrà chiesto se si è l'organizzatore e non verrà mai chiesto il PIN. Poiché l'impostazione dell'organizzatore è impostata su No, di inizio della riunione e i chiamanti anonimi verranno aggiunto alla riunione.
    
  - Se la riunione è già stato avviato (un altro utente è già nella riunione): un chiamante non verrà chiesto se si è l'organizzatore e non verrà mai chiesto il PIN, la riunione è già stata avviata, il chiamante verrà parteciparvi.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione per più utenti, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

