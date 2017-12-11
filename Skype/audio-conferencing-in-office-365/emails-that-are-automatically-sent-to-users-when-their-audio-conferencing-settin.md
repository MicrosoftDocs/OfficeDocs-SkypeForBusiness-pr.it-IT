---
title: "Messaggi che vengono automaticamente inviati agli utenti quando modificare le impostazioni di conferenze Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# Messaggi che vengono automaticamente inviati agli utenti quando modificare le impostazioni di conferenze Audio

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](1b46da6d-f93a-4cc0-9ae8-af765935b007.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/1b46da6d-f93a-4cc0-9ae8-af765935b007). 
  
Messaggi di posta elettronica inviati automaticamente agli utenti abilitati [Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) utilizzano Microsoft come provider di conferenze audio.
  
Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica che verrà inviato agli utenti abilitati per conferenze Audio. Tuttavia, se si desidera limitare il numero di messaggi di posta elettronica inviati agli utenti, è possibile disattivare il. Audioconferenza in Office 365 Invia messaggio di posta elettronica agli utenti quando di posta elettronica:
  
- **Per gli utenti o quando si modifica il provider di conferenze audio a Microsoft, viene assegnata una licenza di conferenze Audio.**
    
    Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito conferenza per le riunioni e conferenze audio PIN per l'utente e le istruzioni e collegamento utilizzare il Skype for Business Online Meeting Update Tool che viene utilizzato per aggiornare le riunioni esistenti per la utenti. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o[Assegnare Microsoft come provider di conferenze audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Se l'organizzazione è stata attivata per gli ID conferenza, tutte le riunioni di un utente che la pianificazione avrà conferenza univoco ID. È possibile impostare [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Ecco un esempio di questo messaggio e-mail
    
     ![Skype for Business Verify License](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    È possibile trovare ulteriori informazioni su Skype for Business licenze visualizzando [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Viene modificato l'ID conferenza o il numero di telefono predefinito per le conferenze.**
    
    Questo messaggio di posta elettronica contiene l'ID conferenza, numero di telefono predefinito conferenza e le istruzioni e collegamento per l'utilizzo di Skype for Business Online Meeting Update Tool che viene utilizzato per aggiornare le riunioni esistenti per l'utente. Ma questo messaggio di posta elettronica non include PIN della conferenza audio dell'utente. Vedere [Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Se l'organizzazione è stata attivata per gli ID conferenza, tutte le riunioni di un utente che la pianificazione avrà conferenza univoco ID. È possibile impostare [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Ecco un esempio di questo messaggio e-mail
    
     ![Le informazioni sulla conferenza telefonica con accesso esterno sono state modificate.](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **Sono reimpostare il PIN di un utente di conferenze audio.**
    
    Questo messaggio di posta elettronica contiene audioconferenza dell'organizzatore PIN, ID conferenza esistente e il numero di telefono predefinito conferenza per l'utente. Vedere [Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > Se l'organizzazione è stata attivata per gli ID conferenza, tutte le riunioni di un utente che la pianificazione avrà conferenza univoco ID. È possibile impostare [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Ecco un esempio di questo messaggio e-mail
    
     ![Il PIN per la conferenza telefonica con accesso esterno è stato cambiato.](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **Licenza dell'utente viene rimosso o alla modifica dei provider di conferenze audio da Microsoft per gli altri provider o nessuno.**
    
    Si verifica quando la licenza di **Conferenze Audio** viene rimosso da un utente o quando si modifica il provider di conferenze audio di un utente da Microsoft a un provider di conferenze audio di terze parti o quando si imposta il provider su **Nessuno**. Questo messaggio di posta elettronica contiene le istruzioni e informazioni per l'utente a utilizzare Skype for Business Online Meeting Update Tool per rimuovere informazioni specifiche di conferenze audio, ad esempio l'impostazione predefinita ID conferenza telefonica numero o una conferenza.
    
    Vedere [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) o[Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Ecco un esempio di questo messaggio e-mail
    
     ![La conferenza telefonica con accesso esterno è disattivata.](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## Apportare modifiche ai messaggi e-mail inviati

È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti inclusi l'indirizzo di posta elettronica e il nome visualizzato inclusi nelle informazioni di contatto  *da*  . Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e nome visualizzato usando Windows PowerShell e il cmdlet[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
  
- Immetti l'indirizzo di posta elettronica nel parametro  _SendEmailFromAddress_.
    
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Imposta il parametro  _SendEmailOverride_ su _True_.
    
È possibile apportare modifiche ai messaggi inviati agli utenti, ad esempio l'indirizzo di posta elettronica inviato da messaggio di posta elettronica e il nome visualizzato per la posta elettronica, eseguendo:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'ambiente in uso consentano i messaggi in arrivo dall'indirizzo specificato. > Se decidi di ignorare le informazioni sul contatto del mittente (campo  *Da*  ), ti consigliamo di verificare che le e-mail vengano inviate correttamente agli utenti. Per eseguire questa operazione, svolgi la verifica con un utente dell'organizzazione.
  
È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## Se non voglio che vengano inviate e-mail agli utenti?

Quando si disattiva invio messaggi di posta elettronica agli utenti, posta elettronica non verranno inviata anche quando un utente viene assegnato una licenza. In questo caso, ID conferenza predefinito numero della conferenza e, soprattutto, loro audioconferenza PIN non verrà inviata all'utente. In questo caso, è necessario fornire all'utente inviando un messaggio o mediante chiamata.
  
Per impostazione predefinita, verranno inviati messaggi di posta elettronica agli utenti, ma se si vuole impedire che riceve la posta elettronica per le conferenze audio, è possibile utilizzare il Skype per Business admin center o Windows PowerShell.
  
 **Utilizzo di Skype per di amministrazione di Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge Microsoft**.
    
4. Nella pagina **delle impostazioni del bridge Microsoft**, selezionare o deselezionare **Invia automaticamente i messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenze audio**.
    
5. Fare clic su **Salva**.
    
 **Uso di Windows PowerShell**
  
1. Esegui il comando seguente per disabilitare l'invio di tutti i messaggi e-mail agli utenti:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Per attivare in altre e disattivare automaticamente l'invio di posta elettronica agli utenti, vedere [Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
    
- In alcuni casi utenti perderanno le informazioni di audio ed è necessario essere in grado di inviare loro tutte le informazioni corrispondenti audio loro. È possibile eseguire questa operazione utilizzando di Skype per Business admin center e facendo clic su **Invia informazioni sugli conferenza tramite posta elettronica** in proprietà audioconferenza per un utente. Vedere[Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md). Tuttavia, queste informazioni non includono il PIN della conferenza audio.
    
    Di seguito è disponibile un'e-mail di esempio:
    
     ![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
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

[Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

