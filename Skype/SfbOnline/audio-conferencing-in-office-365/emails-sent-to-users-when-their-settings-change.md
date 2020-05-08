---
title: Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Scopri quali informazioni vengono inviate automaticamente agli utenti tramite posta elettronica quando modificano le impostazioni di conferenza telefonica in Skype for Business online. '
ms.openlocfilehash: e2f58bfe582b7adc6672c06bec0e90571ff9a96a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164275"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online

> [!Note]
> Se desideri informazioni relative alla posta elettronica automatica in Microsoft Teams, consulta[Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

I messaggi di posta elettronica vengono inviati automaticamente agli utenti che sono [abilitati per le audioconferenze](set-up-audio-conferencing.md) tramite Microsoft come provider di servizi di audioconferenza.
  
Per impostazione predefinita, sono disponibili quattro tipi di messaggi di posta elettronica che verranno inviati agli utenti abilitati per i servizi di audioconferenza. Tuttavia, se si vuole limitare il numero di messaggi di posta elettronica inviati agli utenti, è possibile disattivarlo. I servizi di audioconferenza in Microsoft 365 o Office 365 invieranno messaggi di posta elettronica all'indirizzo di posta elettronica degli utenti quando:
  
- **Viene assegnata loro una licenza di Audioconferenza o quando cambi il provider di audioconferenza e passi a Microsoft.**
    
     This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Verificare la licenza Skype for Business](../images/audio-conferencing-user-enabled.png)
  
    È possibile trovare ulteriori informazioni sulla licenza Skype for Business visualizzando [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID conferenza o il numero di telefono per le conferenze predefinito di un utente cambia.**
    
    This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user. But this email doesn't include the user's audio conferencing PIN. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Le informazioni sulle conferenze telefoniche sono state modificate.](../images/audio-conferencing-info-change.png)
  
- **Viene reimpostato il PIN di audioconferenza di un utente.**
    
    This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user. See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![PIN di conferenza telefonica modificato.](../images/audio-conferencing-pin-has-changed.png)
  
- **Una licenza dell'utente è stata rimossa o quando il provider di servizi di audioconferenza viene modificato da Microsoft a altri provider o nessuno.**
    
    This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.
    
    Vedere [assegnare o rimuovere licenze per le app Microsoft 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Conferenza telefonica disattivata.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Apportare modifiche ai messaggi di posta elettronica inviati

È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, inclusi l'indirizzo di posta elettronica e il nome visualizzato incluso nelle informazioni *di contatto da* . Per impostazione predefinita, il mittente dei messaggi di posta elettronica sarà da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio di posta elettronica agli utenti, è necessario:
  
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
- Imposta il parametro _SendEmailOverride_ su _true_.
    
È possibile apportare modifiche al messaggio di posta elettronica inviato agli utenti, ad esempio l'indirizzo di posta elettronica da cui viene inviato il messaggio e il nome visualizzato per il messaggio di posta elettronica, eseguendo:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address. If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users. You can do this by testing this with one user in your organization.
  
Puoi usare il cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, incluso il messaggio di posta elettronica.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se non vuoi che la posta elettronica venga inviata a loro?

When you disable sending emails to users, email won't be sent even when a user gets assigned a license. In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user. When this happens, you must tell the user by sending them a separate email or by calling them.
  
Per impostazione predefinita, verranno inviati messaggi di posta elettronica agli utenti, ma se desideri impedire loro di ricevere posta elettronica per le audioconferenze, puoi utilizzare l'interfaccia di amministrazione di Skype for Business o Windows PowerShell. 
 
![Icona che mostra il logo](../images/sfb-logo-30x30.png)di Skype for business**con l'interfaccia di amministrazione di Skype for business**  
    
1. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, **Vai a** > **impostazioni di Microsoft Bridge**per audioconferenza.
    
2. Nella pagina **delle impostazioni di Microsoft Bridge** selezionare o deselezionare **Invia automaticamente i messaggi di posta elettronica agli utenti se le impostazioni dei servizi di audioconferenza cambiano**. 
    
3. Fare clic su **Salva**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Uso di Windows PowerShell**
  
1. Esegui le operazioni seguenti per disabilitare l'invio di posta elettronica a tutti gli utenti:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Puoi usare il cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, incluso il messaggio di posta elettronica.
  
## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Per ulteriori informazioni su come abilitare e disabilitare automaticamente l'invio di posta elettronica agli utenti, consulta [Attivare o disattivare l'invio messaggi di posta elettronica quando le impostazioni di Audioconferenza vengono modificate](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Sometimes users lose their audio information and you need to be able to send them all of their audio information to them. You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). However, this information doesn't include the audio conferencing PIN.
    
    Di seguito è riportato un esempio del messaggio di posta elettronica che verrà inviato:
    
     ![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per impostazione predefinita, il mittente dei messaggi di posta elettronica sarà da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell riguarda la gestione degli utenti e gli elementi consentiti o non consentiti. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Perché è necessario usare Microsoft 365 o Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Abilitare o disabilitare l'invio di messaggi di posta elettronica in caso di modifica delle impostazioni di audioconferenza](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md)
