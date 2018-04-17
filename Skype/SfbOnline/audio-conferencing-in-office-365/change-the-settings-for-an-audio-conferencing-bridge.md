---
title: Change the settings for an Audio Conferencing bridge
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/03/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "Get the steps you need to change settings for a conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business or Microsoft Teams apps. "
ms.openlocfilehash: 727392bc81bce2fb3cfd84029e6a275e1eed3e24
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="030d9-103">Change the settings for an Audio Conferencing bridge</span><span class="sxs-lookup"><span data-stu-id="030d9-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="030d9-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="030d9-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="030d9-105">A conferencing bridge can contain one or more phone numbers.</span><span class="sxs-lookup"><span data-stu-id="030d9-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="030d9-106">These phone numbers are used when callers dial in to a meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="030d9-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span><span class="sxs-lookup"><span data-stu-id="030d9-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="030d9-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span><span class="sxs-lookup"><span data-stu-id="030d9-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="030d9-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span><span class="sxs-lookup"><span data-stu-id="030d9-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="030d9-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="030d9-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a><span data-ttu-id="030d9-112">Using the Microsoft Teams and Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="030d9-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="030d9-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span><span class="sxs-lookup"><span data-stu-id="030d9-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="030d9-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="030d9-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="030d9-115">In the **Bridge settings** pane, select:</span><span class="sxs-lookup"><span data-stu-id="030d9-115">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="030d9-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="030d9-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span><span class="sxs-lookup"><span data-stu-id="030d9-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="030d9-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="030d9-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="030d9-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="030d9-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="030d9-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="030d9-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span><span class="sxs-lookup"><span data-stu-id="030d9-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="030d9-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span><span class="sxs-lookup"><span data-stu-id="030d9-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="030d9-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="030d9-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="030d9-124">Click **Apply**.</span><span class="sxs-lookup"><span data-stu-id="030d9-124">Click **Apply**.</span></span> 

## <a name="using-skype-for-business-admin-center"></a><span data-ttu-id="030d9-125">Using Skype for Business admin center</span><span class="sxs-lookup"><span data-stu-id="030d9-125">Using Skype for Business admin center</span></span>

 <span data-ttu-id="030d9-126">**Set up the meeting experience when callers join a meeting**</span><span class="sxs-lookup"><span data-stu-id="030d9-126">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="030d9-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="030d9-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="030d9-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span><span class="sxs-lookup"><span data-stu-id="030d9-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="030d9-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="030d9-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="030d9-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="030d9-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span><span class="sxs-lookup"><span data-stu-id="030d9-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="030d9-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="030d9-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="030d9-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="030d9-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="030d9-134">**Ask callers to record their name before joining the meeting** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="030d9-134">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="030d9-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="030d9-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="030d9-136">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="030d9-136">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="030d9-137">**Set the PIN length for meetings**</span><span class="sxs-lookup"><span data-stu-id="030d9-137">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="030d9-138">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="030d9-138">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="030d9-139">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="030d9-139">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="030d9-140">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="030d9-140">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="030d9-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="030d9-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="030d9-142">The PIN must be between 4 and 12 digits.</span><span class="sxs-lookup"><span data-stu-id="030d9-142">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="030d9-143">**Select whether to send email to your users**</span><span class="sxs-lookup"><span data-stu-id="030d9-143">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="030d9-144">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="030d9-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="030d9-145">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="030d9-145">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="030d9-146">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="030d9-146">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="030d9-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="030d9-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="030d9-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="030d9-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="030d9-149">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="030d9-149">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="030d9-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="030d9-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="030d9-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="030d9-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="030d9-154">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="030d9-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="030d9-155">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="030d9-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="030d9-p108">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="030d9-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="030d9-158">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="030d9-158">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="030d9-159">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="030d9-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="030d9-160">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="030d9-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="030d9-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="030d9-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="030d9-163">See also</span><span class="sxs-lookup"><span data-stu-id="030d9-163">Related topics</span></span>

[<span data-ttu-id="030d9-164">Configurare l’audioconferenza</span><span class="sxs-lookup"><span data-stu-id="030d9-164">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
