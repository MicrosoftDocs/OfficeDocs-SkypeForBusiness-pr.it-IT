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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni sui passaggi per reimpostare l'ID conferenza di una riunione dell'utente in Skype for business online e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164705"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="05184-103">Reimpostare un ID conferenza per un utente in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="05184-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="05184-104">Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="05184-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="05184-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span><span class="sxs-lookup"><span data-stu-id="05184-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05184-p102">Se il proprio provider di servizi di conferenza è Microsoft, gli ID conferenza degli utenti sono impostati solo su dinamico. Non è possibile modificarlo. Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for business abilitati per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="05184-p102">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only. This cannot be changed. Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="05184-110">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="05184-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="05184-111">Nell'interfaccia **di amministrazione di Skype for business**, fai clic su**utenti**di servizi di **audioconferenza** > , seleziona un utente e quindi nel riquadro azioni in **ID conferenza** fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="05184-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="05184-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span><span class="sxs-lookup"><span data-stu-id="05184-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05184-p104">Dopo aver reimpostato l'ID conferenza, un messaggio di posta elettronica con il nuovo ID conferenza verrà inviato all'utente. Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, nella cassetta postale Microsoft 365 o Office 365. Il messaggio di posta elettronica contiene il nuovo ID conferenza, i numeri di telefono di accesso esterno predefiniti e le istruzioni per usare lo strumento di aggiornamento delle riunioni Skype for business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="05184-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="05184-118">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="05184-118">What else should I know?</span></span>

- <span data-ttu-id="05184-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span><span class="sxs-lookup"><span data-stu-id="05184-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="05184-121">Un ID conferenza conterrà 7 cifre e non è possibile modificarne la lunghezza nell'interfaccia di amministrazione di Skype for business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05184-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="05184-122">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="05184-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="05184-123">L'ID conferenza di un utente per l'audioconferenza può essere visualizzato nella parte inferiore del riquadro azioni in servizi di **audioconferenza** quando si seleziona l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="05184-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="05184-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span><span class="sxs-lookup"><span data-stu-id="05184-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="05184-128">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="05184-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="05184-129">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="05184-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="05184-130">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="05184-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="05184-131">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="05184-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="05184-p107">Quando si tratta di Windows PowerShell si tratta di gestire gli utenti e gli elementi consentiti o non consentiti. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="05184-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="05184-135">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="05184-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="05184-136">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="05184-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- <span data-ttu-id="05184-p108">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="05184-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="05184-139">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05184-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="05184-140">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05184-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="05184-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05184-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="05184-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="05184-142">Related topics</span></span>

[<span data-ttu-id="05184-143">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="05184-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
