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
ms.openlocfilehash: c7582030765db6951c972dc3fa59610aca73417e
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="c7800-103">Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="c7800-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="c7800-104">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="c7800-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c7800-105">È possibile che, tuttavia, se si desidera ridurre il numero di messaggi di posta elettronica inviati a Skype per utenti Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7800-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="c7800-106">In tal caso, è possibile disabilitare l'invio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c7800-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="c7800-107">Se si disattiva invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenze con accesso esterno non verranno inviate agli utenti, inclusi messaggi di posta elettronica per quando gli utenti sono abilitati o disattivati per le conferenze audio, quando viene reimpostato il proprio PIN e l'ID conferenza e i servizi di conferenza predefinito cambia il numero di telefono .</span><span class="sxs-lookup"><span data-stu-id="c7800-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="c7800-108">Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per le conferenze Audio:</span><span class="sxs-lookup"><span data-stu-id="c7800-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Posta elettronica per conferenze audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="c7800-110">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="c7800-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="c7800-111">Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:</span><span class="sxs-lookup"><span data-stu-id="c7800-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="c7800-112">Quando una licenza di **Conferenze Audio** viene assegnata loro.</span><span class="sxs-lookup"><span data-stu-id="c7800-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c7800-113">Quando si reimposta manualmente conferenza PIN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c7800-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="c7800-114">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c7800-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c7800-115">Se la licenza di **Conferenze Audio** viene rimosso da essi.</span><span class="sxs-lookup"><span data-stu-id="c7800-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c7800-116">Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="c7800-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c7800-117">Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7800-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="c7800-118">Attivare o disattivare la posta elettronica non verrà inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="c7800-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="c7800-119">È possibile utilizzare Microsoft Teams, Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c7800-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="c7800-120">**Utilizzo del team di Microsoft e Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="c7800-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="c7800-121">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="c7800-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c7800-122">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="c7800-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="c7800-123">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.</span><span class="sxs-lookup"><span data-stu-id="c7800-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c7800-124">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="c7800-124">Click **Apply**.</span></span>
  
<span data-ttu-id="c7800-125">**Utilizzo di Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="c7800-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="c7800-126">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistra fare clic su **audioconferenze**.</span><span class="sxs-lookup"><span data-stu-id="c7800-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="c7800-127">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="c7800-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="c7800-128">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c7800-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c7800-129">È inoltre possibile inviare posta elettronica a un utente con le impostazioni di conferenza audio **all'audioconferenza** > **gli utenti**, selezionare l'utente e fare clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="c7800-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="c7800-130">In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="c7800-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="c7800-131">Per ulteriori informazioni, vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="c7800-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="c7800-132">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c7800-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="c7800-133">Eseguire il cmdlet seguente per disabilitare l'invio messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="c7800-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="c7800-134">Per assistenza per questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="c7800-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="c7800-135">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="c7800-135">What else should you know?</span></span>

- <span data-ttu-id="c7800-136">Quando i messaggi di posta elettronica automatiche sono disabilitate, è possibile attivare ancora manualmente messaggio di posta elettronica con il numero di ID e il telefono di conferenza utilizzando il Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="c7800-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="c7800-137">Tuttavia, in tal caso, il PIN non sarà incluso.</span><span class="sxs-lookup"><span data-stu-id="c7800-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="c7800-138">Se si desidera reimpostare il PIN di conferenza audio e l'invio di messaggi di posta elettronica è disattivato, sarà necessario inviarla all'utente in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="c7800-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="c7800-139">Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome tramite Windows PowerShell e inoltre utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="c7800-139">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="c7800-140">Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente di consentano i messaggi di posta elettronica che provengono da personalizzato specificato dall'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c7800-140">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="c7800-141">Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="c7800-141">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="c7800-142">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="c7800-142">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="c7800-143">Il parametro _SendEmailOverride_ impostato su _True_.</span><span class="sxs-lookup"><span data-stu-id="c7800-143">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="c7800-144">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7800-144">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c7800-145">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c7800-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c7800-146">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c7800-146">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="c7800-147">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="c7800-147">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="c7800-148">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="c7800-148">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="c7800-149">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7800-149">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="c7800-150">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="c7800-150">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="c7800-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="c7800-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c7800-154">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c7800-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c7800-155">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7800-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c7800-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="c7800-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c7800-158">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7800-158">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c7800-159">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7800-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c7800-160">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7800-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c7800-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="c7800-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c7800-163">See also</span><span class="sxs-lookup"><span data-stu-id="c7800-163">Related topics</span></span>

[<span data-ttu-id="c7800-164">Messaggi di posta elettronica inviati agli utenti quando modificano le impostazioni di conferenza Audio</span><span class="sxs-lookup"><span data-stu-id="c7800-164">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="c7800-165">Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="c7800-165">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


