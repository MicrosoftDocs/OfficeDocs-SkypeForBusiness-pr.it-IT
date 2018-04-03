---
title: Abilitare o disabilitare l'invio messaggi di posta elettronica quando le relative impostazioni di modifica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: e2a57a63cbc7b633e0240b7ec94f2d548a2dbe31
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="8f665-103">Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="8f665-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="8f665-104">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="8f665-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8f665-105">È possibile che, tuttavia, se si desidera ridurre il numero di messaggi di posta elettronica inviati a Skype per utenti Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f665-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="8f665-106">In tal caso, è possibile disabilitare l'invio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8f665-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="8f665-107">Se si disattiva invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenze con accesso esterno non verranno inviate agli utenti, inclusi messaggi di posta elettronica per quando gli utenti sono abilitati o disattivati per le conferenze audio, quando viene reimpostato il proprio PIN e l'ID conferenza e i servizi di conferenza predefinito cambia il numero di telefono .</span><span class="sxs-lookup"><span data-stu-id="8f665-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="8f665-108">Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per le conferenze Audio:</span><span class="sxs-lookup"><span data-stu-id="8f665-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Posta elettronica per conferenze audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="8f665-110">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="8f665-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="8f665-111">Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:</span><span class="sxs-lookup"><span data-stu-id="8f665-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="8f665-112">Quando una licenza di **Conferenze Audio** viene assegnata loro.</span><span class="sxs-lookup"><span data-stu-id="8f665-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="8f665-113">Quando si reimposta manualmente conferenza PIN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8f665-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="8f665-114">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8f665-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="8f665-115">Se la licenza di **Conferenze Audio** viene rimosso da essi.</span><span class="sxs-lookup"><span data-stu-id="8f665-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="8f665-116">Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="8f665-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="8f665-117">Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f665-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="8f665-118">Attivare o disattivare la posta elettronica non verrà inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="8f665-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="8f665-119">È possibile utilizzare Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8f665-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="8f665-120">**Utilizzo di Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="8f665-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="8f665-121">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="8f665-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8f665-122">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="8f665-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="8f665-123">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="8f665-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="8f665-124">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f665-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8f665-125">È inoltre possibile inviare posta elettronica a un utente con le impostazioni di conferenza audio **all'audioconferenza** > **gli utenti**, selezionare l'utente e fare clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8f665-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="8f665-126">In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="8f665-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="8f665-127">Per ulteriori informazioni, vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="8f665-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="8f665-128">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8f665-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="8f665-129">Eseguire il cmdlet seguente per disabilitare l'invio messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="8f665-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="8f665-130">Per assistenza per questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="8f665-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="8f665-131">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="8f665-131">What else should you know?</span></span>

- <span data-ttu-id="8f665-132">Quando i messaggi di posta elettronica automatiche sono disabilitate, è possibile attivare ancora manualmente messaggio di posta elettronica con il numero di ID e il telefono di conferenza utilizzando il Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="8f665-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="8f665-133">Tuttavia, in tal caso, il PIN non sarà incluso.</span><span class="sxs-lookup"><span data-stu-id="8f665-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="8f665-134">Se si desidera reimpostare il PIN di conferenza audio e l'invio di messaggi di posta elettronica è disattivato, sarà necessario inviarla all'utente in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="8f665-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="8f665-135">Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome tramite Windows PowerShell e inoltre utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="8f665-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="8f665-136">Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente di consentano i messaggi di posta elettronica che provengono da personalizzato specificato dall'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8f665-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="8f665-137">Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="8f665-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="8f665-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="8f665-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="8f665-139">Il parametro _SendEmailOverride_ impostato su _True_.</span><span class="sxs-lookup"><span data-stu-id="8f665-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="8f665-140">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f665-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8f665-141">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8f665-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8f665-142">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8f665-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="8f665-143">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8f665-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="8f665-144">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8f665-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="8f665-145">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f665-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="8f665-146">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8f665-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="8f665-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8f665-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8f665-150">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="8f665-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8f665-151">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f665-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="8f665-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8f665-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="8f665-154">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f665-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8f665-155">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f665-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8f665-156">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f665-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="8f665-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="8f665-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8f665-159">See also</span><span class="sxs-lookup"><span data-stu-id="8f665-159">Related topics</span></span>

[<span data-ttu-id="8f665-160">Messaggi di posta elettronica inviati agli utenti quando modificano le impostazioni di conferenza Audio</span><span class="sxs-lookup"><span data-stu-id="8f665-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="8f665-161">Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="8f665-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


