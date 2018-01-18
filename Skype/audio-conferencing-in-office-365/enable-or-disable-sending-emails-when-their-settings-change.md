---
title: Abilitare o disabilitare l'invio messaggi di posta elettronica quando le relative impostazioni di modifica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per le audioconferenze. È possibile che, tuttavia, se si desidera ridurre il numero di messaggi di posta elettronica inviati a Skype per utenti Business e Microsoft Teams. In tal caso, è possibile disabilitare l'invio di posta elettronica.
  
Se si disattiva invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenze con accesso esterno non verranno inviate agli utenti, inclusi messaggi di posta elettronica per quando gli utenti sono abilitati o disattivati per le conferenze audio, quando viene reimpostato il proprio PIN e l'ID conferenza e i servizi di conferenza predefinito cambia il numero di telefono .
  
Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per le conferenze Audio:
  
![Posta elettronica per conferenze audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:
    
  - Quando una licenza di **Conferenze Audio** viene assegnata loro.
    
  - Quando si reimposta manualmente conferenza PIN dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Se la licenza di **Conferenze Audio** viene rimosso da essi.
    
  - Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.
    
  - Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Attivare o disattivare la posta elettronica non verrà inviato agli utenti

È possibile utilizzare Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.
  
 **Utilizzo di Skype per interfaccia di amministrazione di Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
4. Fare clic su **Salva**.
    
    > [!TIP]
    > È inoltre possibile inviare posta elettronica a un utente con le impostazioni di conferenza audio **all'audioconferenza** > **gli utenti**, selezionare l'utente e fare clic su **Invia informazioni conferenza tramite posta elettronica**.  In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non il PIN.  Per ulteriori informazioni, vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
 **Utilizzo di Windows PowerShell**
  
- Eseguire il cmdlet seguente per disabilitare l'invio messaggi di posta elettronica: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Per assistenza per questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Quando i messaggi di posta elettronica automatiche sono disabilitate, è possibile attivare ancora manualmente messaggio di posta elettronica con il numero di ID e il telefono di conferenza utilizzando il Skype per interfaccia di amministrazione di Business. Tuttavia, in tal caso, il PIN non sarà incluso. Se si desidera reimpostare il PIN di conferenza audio e l'invio di messaggi di posta elettronica è disattivato, sarà necessario inviarla all'utente in un altro modo.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome tramite Windows PowerShell e inoltre utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    >  Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente di consentano i messaggi di posta elettronica che provengono da personalizzato specificato dall'indirizzo.
  
  - Immetti l'indirizzo di posta elettronica nel parametro  _SendEmailFromAddress_.
    
  - Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
  - Il parametro _SendEmailOverride_ impostato su _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Messaggi di posta elettronica inviati agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md)

[Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md)

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)

