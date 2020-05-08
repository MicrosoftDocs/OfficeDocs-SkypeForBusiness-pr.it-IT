---
title: Visualizzare, modificare e reimpostare un ID conferenza assegnato a un utente in Skype for business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype for Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: caa94984b06ff73d8f14acf4727870a988298974
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163915"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="12139-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="12139-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="12139-104">Per informazioni sugli ID conferenza utente in Microsoft teams, vedere [visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="12139-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="12139-p101">Un ID conferenza viene assegnato automaticamente a un utente di Skype for business quando è configurato per le conferenze audio in Microsoft 365 o Office 365 e USA Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è programmata. A ogni riunione in cui viene pianificato un utente verrà assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="12139-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="12139-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="12139-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="12139-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="12139-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="12139-112">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="12139-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="12139-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="12139-113">To view the conference ID</span></span>

<span data-ttu-id="12139-114">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="12139-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="12139-115">È possibile visualizzare l'ID conferenza e inviarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="12139-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="12139-116">Accedere con l'account di lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="12139-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="12139-117">Accedere all'interfaccia di amministrazione > **Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="12139-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="12139-118">Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="12139-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="12139-119">Nella pagina Azione, cerca in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="12139-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="12139-120">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni sulla conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="12139-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="12139-121">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="12139-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="12139-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="12139-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="12139-124">Per ulteriori informazioni sul cmdlet, vedere [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) .</span><span class="sxs-lookup"><span data-stu-id="12139-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="12139-125">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="12139-125">To reset the conference ID</span></span>

<span data-ttu-id="12139-126">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="12139-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="12139-127">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="12139-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="12139-128">Accedere con l'account di lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="12139-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="12139-129">Accedere all'interfaccia di amministrazione > **Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="12139-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="12139-130">Negli**utenti**di servizi di> **audioconferenza** > per l'interfaccia di **amministrazione di Skype for business**, nel riquadro azioni in **ID conferenza**fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="12139-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="12139-131">Nella finestra **Reimposta ID conferenza** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="12139-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="12139-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="12139-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="12139-133">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="12139-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="12139-134">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12139-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="12139-135">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="12139-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="12139-136">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="12139-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="12139-137">Dopo la creazione di un nuovo ID conferenza o di un reset, il vecchio ID conferenza non può essere usato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="12139-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="12139-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="12139-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="12139-139">Gli utenti possono usare lo strumento di migrazione delle riunioni di Skype for business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="12139-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="12139-140">Per scoprire come scaricare, installare ed eseguire lo strumento, vedere: strumento di [aggiornamento per le riunioni per Skype for business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="12139-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="12139-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12139-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="12139-142">L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="12139-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="12139-143">Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="12139-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="12139-144">L'ID conferenza per tutti gli utenti di audioconferenze sarà di 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="12139-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="12139-145">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="12139-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="12139-146">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="12139-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="12139-147">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="12139-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="12139-148">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="12139-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="12139-149">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12139-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="12139-150">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="12139-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="12139-151">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="12139-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="12139-152">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="12139-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="12139-153">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12139-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="12139-154">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="12139-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="12139-155">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="12139-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="12139-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="12139-156">Related topics</span></span>

[<span data-ttu-id="12139-157">Provare o acquistare servizi di audioconferenza in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="12139-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

