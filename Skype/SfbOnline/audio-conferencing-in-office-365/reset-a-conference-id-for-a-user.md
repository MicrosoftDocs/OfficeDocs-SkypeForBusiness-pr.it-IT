---
title: Reimpostare un ID conferenza per un utente in Skype for Business online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Skype for Business online e ottenere i collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164705"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="a7d45-103">Reimpostare un ID conferenza per un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="a7d45-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="a7d45-104">Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a7d45-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="a7d45-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span><span class="sxs-lookup"><span data-stu-id="a7d45-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7d45-p102">Se il tuo provider di conferenze è Microsoft, gli ID conferenza degli utenti sono impostati su Solo dinamici. Questa impostazione non può essere modificata. Gli ID conferenza vengono impostati automaticamente solo per gli utenti Skype for Business abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="a7d45-p102">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only. This cannot be changed. Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="a7d45-110">Reimpostazione dell'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="a7d45-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="a7d45-111">**Nell'interfaccia di amministrazione di Skype for Business** fai clic su Utenti servizi di audioconferenza, seleziona un utente, quindi nel riquadro   >  Azione, in **ID** conferenza, fai clic **su Reimposta.**</span><span class="sxs-lookup"><span data-stu-id="a7d45-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="a7d45-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span><span class="sxs-lookup"><span data-stu-id="a7d45-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7d45-p104">Dopo aver reimpostato l'ID conferenza, all'utente verrà inviata un'e-mail con il nuovo ID conferenza. Questo messaggio verrà inviato all'indirizzo di posta elettronica principale, in molti casi alla cassetta postale di Microsoft 365 o Office 365. L'e-mail contiene il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso e le istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="a7d45-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="a7d45-118">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="a7d45-118">What else should I know?</span></span>

- <span data-ttu-id="a7d45-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span><span class="sxs-lookup"><span data-stu-id="a7d45-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="a7d45-121">Un ID conferenza contiene 7 cifre e non puoi modificarne la lunghezza nell'interfaccia di amministrazione di Skype for Business o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7d45-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="a7d45-122">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="a7d45-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="a7d45-123">L'ID conferenza di un utente per i servizi di audioconferenza può essere visualizzato nella parte inferiore del riquadro Azioni in **Audioconferenza** quando si seleziona l'utente nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="a7d45-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="a7d45-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span><span class="sxs-lookup"><span data-stu-id="a7d45-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="a7d45-128">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="a7d45-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="a7d45-129">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="a7d45-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="a7d45-130">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="a7d45-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a7d45-131">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a7d45-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a7d45-p107">Per quanto riguarda Windows PowerShell riguarda la gestione degli utenti e le operazioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="a7d45-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a7d45-135">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="a7d45-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a7d45-136">Perché è necessario usare PowerShell di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="a7d45-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- <span data-ttu-id="a7d45-p108">Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7d45-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a7d45-139">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7d45-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a7d45-140">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a7d45-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a7d45-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a7d45-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a7d45-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a7d45-142">Related topics</span></span>

[<span data-ttu-id="a7d45-143">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="a7d45-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
