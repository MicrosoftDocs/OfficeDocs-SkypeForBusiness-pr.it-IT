---
title: Abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio in Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4d52603fb0d2701cbebd58644cd002dbc94baf89
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490586"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="8e3d2-103">Abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="8e3d2-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="8e3d2-104">Se si desidera abilitare o disabilitare l'invio messaggi di posta elettronica in Teams Microsoft, vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio nel team di Microsoft](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8e3d2-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="8e3d2-105">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8e3d2-106">È possibile che, tuttavia, se si desidera ridurre il numero di messaggi di posta elettronica inviati a Skype per gli utenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="8e3d2-107">In tal caso, è possibile disabilitare l'invio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="8e3d2-108">Se si disattiva invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenze con accesso esterno non verranno inviate agli utenti, inclusi messaggi di posta elettronica per quando gli utenti sono abilitati o disattivati per le conferenze audio, quando viene reimpostato il proprio PIN e l'ID conferenza e i servizi di conferenza predefinito cambia il numero di telefono .</span><span class="sxs-lookup"><span data-stu-id="8e3d2-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="8e3d2-109">Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per le conferenze Audio:</span><span class="sxs-lookup"><span data-stu-id="8e3d2-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Posta elettronica per conferenze audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="8e3d2-111">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="8e3d2-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="8e3d2-112">Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:</span><span class="sxs-lookup"><span data-stu-id="8e3d2-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="8e3d2-113">Quando una licenza di **Conferenze Audio** viene assegnata loro.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="8e3d2-114">Quando si reimposta manualmente conferenza PIN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="8e3d2-115">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="8e3d2-116">Se la licenza di **Conferenze Audio** viene rimosso da essi.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="8e3d2-117">Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="8e3d2-118">Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="8e3d2-119">Attivare o disattivare la posta elettronica non verrà inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="8e3d2-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="8e3d2-120">È possibile utilizzare Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="8e3d2-121">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="8e3d2-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="8e3d2-122">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistra fare clic su **audioconferenze**.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="8e3d2-123">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="8e3d2-124">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8e3d2-125">È inoltre possibile inviare posta elettronica a un utente con le impostazioni di conferenza audio **all'audioconferenza** > **gli utenti**, selezionare l'utente e fare clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="8e3d2-126">In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="8e3d2-127">Per ulteriori informazioni, vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="8e3d2-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="8e3d2-128">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8e3d2-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="8e3d2-129">Eseguire il cmdlet seguente per disabilitare l'invio messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="8e3d2-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="8e3d2-130">Per assistenza per questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="8e3d2-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="8e3d2-131">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="8e3d2-131">What else should you know?</span></span>

- <span data-ttu-id="8e3d2-132">Quando i messaggi di posta elettronica automatiche sono disabilitate, è possibile attivare ancora manualmente messaggio di posta elettronica con il numero di ID e il telefono di conferenza utilizzando il Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="8e3d2-133">Tuttavia, in tal caso, il PIN non sarà incluso.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="8e3d2-134">Se si desidera reimpostare il PIN di conferenza audio e l'invio di messaggi di posta elettronica è disattivato, sarà necessario inviarla all'utente in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="8e3d2-135">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8e3d2-136">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8e3d2-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8e3d2-137">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="8e3d2-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8e3d2-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="8e3d2-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8e3d2-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="8e3d2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="8e3d2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="8e3d2-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8e3d2-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="8e3d2-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8e3d2-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8e3d2-145">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="8e3d2-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8e3d2-146">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e3d2-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="8e3d2-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8e3d2-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="8e3d2-149">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8e3d2-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8e3d2-150">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8e3d2-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8e3d2-151">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8e3d2-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="8e3d2-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="8e3d2-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8e3d2-154">See also</span><span class="sxs-lookup"><span data-stu-id="8e3d2-154">Related topics</span></span>

[<span data-ttu-id="8e3d2-155">Messaggi di posta elettronica inviati agli utenti quando modificano le impostazioni di conferenza Audio</span><span class="sxs-lookup"><span data-stu-id="8e3d2-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="8e3d2-156">Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="8e3d2-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


