---
title: Send an email to a user with their dial-in information
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Send your users an email with their audio conferencing information.
ms.openlocfilehash: f1e4ddd06011d7eb85253e06d6b7de775a207683
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a><span data-ttu-id="03bac-103">Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="03bac-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="03bac-104">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information.</span><span class="sxs-lookup"><span data-stu-id="03bac-104">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="03bac-105">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span><span class="sxs-lookup"><span data-stu-id="03bac-105">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="03bac-106">When you send this email, it will contain all of the audio conferencing information, including:</span><span class="sxs-lookup"><span data-stu-id="03bac-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="03bac-107">Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="03bac-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="03bac-108">L'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="03bac-108">The user's conference ID.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03bac-109">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span><span class="sxs-lookup"><span data-stu-id="03bac-109">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="03bac-110">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="03bac-110">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="03bac-111">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="03bac-111">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
<span data-ttu-id="03bac-112">Here is an example of the email that is sent:</span><span class="sxs-lookup"><span data-stu-id="03bac-112">Here is an example of the email that is sent:</span></span>
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="03bac-114">Send an email with audio conferencing information to a user</span><span class="sxs-lookup"><span data-stu-id="03bac-114">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="03bac-115">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="03bac-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="03bac-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="03bac-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="03bac-117">Click **Users**, and then select the user.</span><span class="sxs-lookup"><span data-stu-id="03bac-117">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="03bac-118">Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="03bac-118">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="03bac-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="03bac-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="03bac-120">Cos'altro occorre sapere su questo messaggio di posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="03bac-120">What else should you know about this email?</span></span>

- <span data-ttu-id="03bac-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span><span class="sxs-lookup"><span data-stu-id="03bac-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="03bac-122">When an **Audio Conferencing** license is assigned to them.</span><span class="sxs-lookup"><span data-stu-id="03bac-122">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="03bac-123">When you manually reset the user's audio conferencing PIN.</span><span class="sxs-lookup"><span data-stu-id="03bac-123">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="03bac-124">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="03bac-124">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="03bac-125">When an **Audio Conferencing** license is removed from them.</span><span class="sxs-lookup"><span data-stu-id="03bac-125">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="03bac-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span><span class="sxs-lookup"><span data-stu-id="03bac-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="03bac-127">When the audio conferencing provider for a user is changed to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03bac-127">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="03bac-128">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="03bac-128">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="03bac-129">To make changes to the email address that is sending the email to users, you must:</span><span class="sxs-lookup"><span data-stu-id="03bac-129">To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="03bac-130">Enter the email address in the SendEmailFromAddress parameter.</span><span class="sxs-lookup"><span data-stu-id="03bac-130">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="03bac-131">Set the SendEmailOverride parameter to True.</span><span class="sxs-lookup"><span data-stu-id="03bac-131">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="03bac-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span><span class="sxs-lookup"><span data-stu-id="03bac-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="03bac-133">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="03bac-133">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="03bac-134">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="03bac-134">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="03bac-135">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="03bac-135">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="03bac-136">To send an email to the user with their audio conferencing information, run the following:</span><span class="sxs-lookup"><span data-stu-id="03bac-136">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="03bac-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="03bac-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="03bac-140">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="03bac-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="03bac-141">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03bac-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="03bac-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="03bac-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="03bac-144">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="03bac-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="03bac-145">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="03bac-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="03bac-146">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="03bac-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="03bac-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="03bac-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="03bac-149">See also</span><span class="sxs-lookup"><span data-stu-id="03bac-149">Related topics</span></span>

[<span data-ttu-id="03bac-150">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="03bac-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
