---
title: Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN, e su come impostare la lunghezza delle riunioni in Skype for Business.
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164535"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="52307-103">Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="52307-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="52307-104">Per informazioni su come impostare la lunghezza del PIN in Microsoft Teams, consulta [Impostare la lunghezza del PIN per le riunioni in Audioconferenza in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="52307-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="52307-p101">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="52307-p101">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="52307-p102">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="52307-p102">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="52307-112">Impostazione della lunghezza del PIN</span><span class="sxs-lookup"><span data-stu-id="52307-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="52307-113">**Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, vai alle impostazioni bridge Microsoft per le   >  **audioconferenze.**</span><span class="sxs-lookup"><span data-stu-id="52307-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="52307-114">In **Lunghezza** PIN di sicurezza selezionare il numero di cifre desiderato per il PIN e quindi fare  >  clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="52307-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="52307-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span><span class="sxs-lookup"><span data-stu-id="52307-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="52307-119">Vuoi saperne di più sulle impostazioni del PIN?</span><span class="sxs-lookup"><span data-stu-id="52307-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="52307-p104">PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.</span><span class="sxs-lookup"><span data-stu-id="52307-p104">PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="52307-p105">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span><span class="sxs-lookup"><span data-stu-id="52307-p105">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="52307-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span><span class="sxs-lookup"><span data-stu-id="52307-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="52307-127">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="52307-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="52307-128">Per risparmiare tempo o automatizzare questa operazione, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=715757)</span><span class="sxs-lookup"><span data-stu-id="52307-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="52307-129">Per impostare a 8 il numero di cifre del PIN:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="52307-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="52307-p107">Windows PowerShell riguarda la gestione degli utenti e le operazioni che sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="52307-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="52307-133">Perché è necessario usare PowerShell di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="52307-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="52307-134">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52307-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="52307-p108">Windows PowerShell presenta molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="52307-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="52307-137">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="52307-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="52307-138">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="52307-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="52307-139">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="52307-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="52307-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="52307-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="52307-p109">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="52307-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52307-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52307-143">See also</span></span>

[<span data-ttu-id="52307-144">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="52307-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
