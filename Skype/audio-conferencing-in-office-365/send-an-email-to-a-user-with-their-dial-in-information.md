---
title: "Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio"
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
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
In alcuni casi potrebbe essere necessario Skype per gli utenti aziendali o Teams Microsoft di inviare le informazioni di conferenze Audio. È possibile eseguire questa operazione con **Skype for Business admin center** e facendo clic su **Invia informazioni sugli conferenza tramite posta elettronica** in proprietà per un utente. Quando si invia il messaggio di posta elettronica, conterrà tutte le informazioni di audioconferenza, tra cui:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
    > [!NOTE]
    > ID statico vengono utilizzati quando gli utenti dell'organizzazione non vuole ricordare un numero casuale. possono selezionare un determinato numero o usare uno che sia facile da ricordare. Quando si utilizzano ID conferenza dinamici, ogni riunione le pianificazioni di un utente verranno visualizzato assegnato un ID conferenza univoco. Se si desidera assegnare dinamico invece di una conferenza statica ID, [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Ecco un esempio di messaggio di posta elettronica inviati:
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Inviare un messaggio di posta elettronica con informazioni sulle conferenze audio a un utente

1. Accedere a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia **di amministrazione di Office 365** > **Skype for Business**e nella barra di spostamento sinistra, fare clic su **conferenze Audio**.
    
3. Fare clic su **utenti** e quindi selezionare l'utente.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
> [!TIP]
> È anche possibile inviare posta elettronica all'utente con le impostazioni di conferenze audio modificando le proprietà dell'utente e quindi fare clic su **conferenze Audio** > **Invia informazioni sugli conferenza tramite posta elettronica**. 
  
## Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Ci sono diversi i messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo l'abilitazione per le conferenze audio:
    
  - Quando una licenza di **Conferenze Audio** è assegnata.
    
  - Quando si manualmente Reimposta PIN della conferenza audio dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando una licenza di **Conferenze Audio** viene rimosso da essi.
    
  - Quando il provider di conferenze audio per un utente viene modificato da Microsoft a un altro provider o **Nessuno**.
    
  - Quando si modifica il provider di conferenze audio per un utente a Microsoft.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e visualizzare nome mediante Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
    
  - Immettere l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.
    
  - Impostare il parametro SendEmailOverride su True.
    
  - Immettere il nome visualizzato posta elettronica nel parametro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato. 
  
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
    Per inviare un messaggio di posta elettronica all'utente con le informazioni di conferenze audio, eseguire le operazioni seguenti:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Quando si tratta di Windows PowerShell, Skype for Business online è basato sui gestione di utenti e quali utenti sono consentite o non consentite. Con Windows PowerShell, è possibile gestire Office 365 utilizzando un unico punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a utilizzare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi velocità, semplicità e produttività rispetto all'uso solo di amministrazione di Office 365, ad esempio quando si effettuano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su questi vantaggi negli argomenti seguenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

