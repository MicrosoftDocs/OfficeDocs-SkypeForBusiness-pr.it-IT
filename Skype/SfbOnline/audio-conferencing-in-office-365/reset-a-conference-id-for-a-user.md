---
title: Reimpostare un ID conferenza per un utente in Skype for business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni sui passaggi per reimpostare l'ID conferenza di una riunione dell'utente in Skype for business online e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: 0e214444b80f6562c733526acbb6f87c66e46922
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792106"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="8f8ae-103">Reimpostare un ID conferenza per un utente in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="8f8ae-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="8f8ae-104">Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8f8ae-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="8f8ae-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f8ae-107">Se il proprio provider di servizi di conferenza è Microsoft, gli ID conferenza degli utenti sono impostati solo su dinamico.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="8f8ae-108">Non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-108">This cannot be changed.</span></span> <span data-ttu-id="8f8ae-109">Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="8f8ae-110">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="8f8ae-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="8f8ae-111">Nell'interfaccia **di amministrazione di Skype for business**, fai clic su**utenti**di servizi di **audioconferenza** > , seleziona un utente e quindi nel riquadro azioni in **ID conferenza** fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="8f8ae-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f8ae-p104">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="8f8ae-118">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="8f8ae-118">What else should I know?</span></span>

- <span data-ttu-id="8f8ae-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="8f8ae-121">Un ID conferenza conterrà 7 cifre e non è possibile modificarne la lunghezza nell'interfaccia di amministrazione di Skype for business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="8f8ae-122">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="8f8ae-123">L'ID conferenza di un utente per l'audioconferenza può essere visualizzato nella parte inferiore del riquadro azioni in servizi di **audioconferenza** quando si seleziona l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="8f8ae-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="8f8ae-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="8f8ae-128">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="8f8ae-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="8f8ae-129">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="8f8ae-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="8f8ae-130">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="8f8ae-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8f8ae-131">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8f8ae-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8f8ae-p107">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="8f8ae-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8f8ae-135">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f8ae-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8f8ae-136">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="8f8ae-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="8f8ae-137">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8f8ae-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8f8ae-138">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="8f8ae-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8f8ae-139">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="8f8ae-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8f8ae-140">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f8ae-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8f8ae-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8f8ae-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8f8ae-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8f8ae-142">Related topics</span></span>

[<span data-ttu-id="8f8ae-143">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="8f8ae-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
