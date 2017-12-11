---
title: "Impostare la lunghezza del PIN per le riunioni di conferenze Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# Impostare la lunghezza del PIN per le riunioni di conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](b86d31c6-1543-478f-b8c6-4b71e708403a.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/b86d31c6-1543-478f-b8c6-4b71e708403a). 
  
Quando configurano audioconferenza in per Skype for Business o Teams Microsoft, verrà visualizzato un bridge di conferenza audio. Un bridge di conferenza può contenere uno o più numeri di telefono. Il numero di telefono che è impostato verrà inclusi in inviti alle riunioni di Skype per le aziende e Microsoft Teams app.
  
Bridge audioconferenza risponde a una chiamata per le persone che accedono a una riunione tramite telefono. Vengono fornite risposte alle chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, possono riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni del bridge Microsoft** consente di modificare le impostazioni per le notifiche di riunioni e partecipare esperienza della riunione e impostare la lunghezza dei pin vengono usati dagli organizzatori della riunione. Gli organizzatori della riunione utilizzare PIN per avviare riunioni se che non è possibile partecipare alla riunione usando il Skype per Business o Microsoft Teams app.
  
## Impostazione della lunghezza dei PIN

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge Microsoft**.
    
4. In **sicurezza** > **Lunghezza PIN**, selezionare il numero di cifre desiderato per il PIN e quindi fare clic su **Salva**.
    
> [!NOTE]
> Il PIN è diverso da un ID conferenza. Gli ID conferenza servono ai chiamanti quando accedono alla riunione. Sono utilizzati per identificare la riunione. Il PIN serve per autenticare un chiamante come organizzatore della riunione. 
  
## Ulteriori informazioni sulle impostazioni del PIN

- PIN può contenere da 4 a 12 cifre. il valore predefinito è "5". I numeri vengono utilizzati solo durante la creazione dei pin. Non utilizzare lettere e caratteri speciali.
    
- Il PIN è solo richiesti per l'organizzatore della riunione quando un utente di Microsoft Teams o Skype for Business non è già stata avviata la riunione. Se tutti gli utenti è accedono alla riunione, il PIN è necessario per l'organizzatore della riunione avviare la riunione.
    
- Impostazioni di protezione PIN vengono applicate a tutti i numeri di telefono che sono associati a un bridge Microsoft. Sono verrà applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un bridge specificato.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Per impostare il numero di cifre del PIN su 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell è basato sui gestione di utenti e quali utenti sono consentite o non consentite. Con Windows PowerShell, è possibile gestire Office 365 utilizzando un unico punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a utilizzare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi velocità, semplicità e produttività rispetto all'uso solo di amministrazione di Office 365, ad esempio quando si eseguono modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su questi vantaggi negli argomenti seguenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

