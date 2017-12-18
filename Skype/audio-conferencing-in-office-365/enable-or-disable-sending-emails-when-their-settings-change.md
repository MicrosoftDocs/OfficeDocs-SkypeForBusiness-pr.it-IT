---
title: "Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Gli utenti sono automaticamente una notifica tramite posta elettronica quando sono abilitati per conferenze Audio. A volte può essere, tuttavia, quando si desidera ridurre il numero di messaggi di posta elettronica inviati al Skype per Business e Teams Microsoft utente. In tal caso, è possibile disattivare l'invio di posta elettronica.
  
Se si disattiva l'invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenza non verranno inviate agli utenti, tra cui messaggi di posta elettronica per quando gli utenti sono attivati o disabilitati per le conferenze audio quando reimpostazione del PIN e l'ID conferenza e telefoniche con accesso esterno predefinito cambia il numero di telefono .
  
Ecco un esempio di messaggio di posta elettronica inviati agli utenti quando sono abilitati per conferenze Audio:
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## I messaggi di posta elettronica quando vengono inviati agli utenti?

- Ci sono diversi i messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo l'abilitazione per le conferenze audio:
    
  - Quando una licenza di **Conferenze Audio** è assegnata.
    
  - Quando si manualmente Reimposta PIN della conferenza audio dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando la licenza di **Conferenze Audio** viene rimosso da essi.
    
  - Quando il provider di conferenze audio di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.
    
  - Quando si modifica il provider di conferenze audio di un utente a Microsoft.
    
## Attivazione o disattivazione di posta elettronica non verrà inviato agli utenti

È possibile utilizzare Skype for Business admin center o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.
  
 **Utilizzo di Skype per di amministrazione di Business**
  
1. Accedere a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia **di amministrazione di Office 365** > **Skype for Business**e nella barra di spostamento sinistra, fare clic su **conferenze Audio**.
    
3. Nella pagina **delle impostazioni del bridge Microsoft**, selezionare o deselezionare **Invia automaticamente i messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenze audio**.
    
4. Fare clic su **Salva**.
    
    > [!TIP]
    > È anche possibile inviare posta elettronica a un utente con le impostazioni di conferenze audio facendo clic su **conferenze Audio** > **utenti**, selezionare l'utente e fare clic su **Invia informazioni sugli conferenza tramite posta elettronica**. > Se si esegue questa operazione, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di una conferenza, ma non il PIN. > Per ulteriori informazioni, vedere [Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) .
  
 **Uso di Windows PowerShell**
  
- Esegui il comando seguente per disattivare l'invio di e-mail: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Per assistenza con questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## Quali altre informazioni devi conoscere?

- Quando sono disabilitati automatiche messaggi di posta elettronica, è possibile attivare comunque manualmente l'invio di un messaggio di posta elettronica con il numero di telefono e ID conferenza mediante la Skype Business di amministrazione per. Tuttavia, se si esegue questa operazione, il PIN non sarà incluso. Se si desidera reimpostare il PIN della conferenza audio e invio di messaggi di posta elettronica è disattivata, sarà necessario inviare all'utente in un altro modo.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e visualizzare nome usando Windows PowerShell e anche utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'ambiente in uso consentano i messaggi in arrivo dall'indirizzo specificato. 
  
  - Immetti l'indirizzo di posta elettronica nel parametro  _SendEmailFromAddress_.
    
  - Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
  - Imposta il parametro  _SendEmailOverride_ su _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- È possibile utilizzare i cmdlet per risparmiare tempo o automatizzare questa operazione.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Rimuovi CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è necessario utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi velocità, semplicità e produttività rispetto all'uso solo di amministrazione di Office 365, ad esempio quando si effettuano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su questi vantaggi negli argomenti seguenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
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

[Servizi di conferenza telefonica con accesso esterno in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

