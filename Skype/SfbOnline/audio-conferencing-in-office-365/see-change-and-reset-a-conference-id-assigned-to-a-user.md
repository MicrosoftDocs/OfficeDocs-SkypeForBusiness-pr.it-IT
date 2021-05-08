---
title: Visualizzare, modificare e reimpostare un ID conferenza assegnato a un utente in Skype for Business Online
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
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237052"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="ebf60-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ebf60-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="ebf60-104">Per informazioni sugli ID conferenza utente in Microsoft Teams, vedere Visualizzare e reimpostare un ID conferenza assegnato a un utente [in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="ebf60-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="ebf60-105">Un ID conferenza viene assegnato automaticamente a un utente Skype for Business quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e usa Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="ebf60-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="ebf60-106">L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è pianificata.</span><span class="sxs-lookup"><span data-stu-id="ebf60-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="ebf60-107">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="ebf60-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="ebf60-108">Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure quando gli utenti non ricordano o non hanno perso l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="ebf60-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="ebf60-109">È possibile utilizzare l'**interfaccia di amministrazione di Skype for Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="ebf60-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="ebf60-110">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="ebf60-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="ebf60-111">Per ulteriori informazioni sulla reimpostazione del PIN dell'organizzatore di una conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ebf60-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="ebf60-112">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="ebf60-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="ebf60-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="ebf60-113">To view the conference ID</span></span>

<span data-ttu-id="ebf60-114">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="ebf60-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="ebf60-115">È possibile visualizzare l'ID conferenza e inviarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ebf60-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="ebf60-116">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="ebf60-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="ebf60-117">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebf60-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="ebf60-118">Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="ebf60-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="ebf60-119">Nella pagina Azione, cerca in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="ebf60-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ebf60-120">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio  di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento Invia informazioni conferenza tramite posta elettronica dopo aver selezionato l'utente nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="ebf60-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="ebf60-121">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ebf60-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ebf60-122">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="ebf60-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="ebf60-123">A questo scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ebf60-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="ebf60-124">Per altre informazioni sul cmdlet, vedere [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="ebf60-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="ebf60-125">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="ebf60-125">To reset the conference ID</span></span>

<span data-ttu-id="ebf60-126">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="ebf60-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="ebf60-127">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="ebf60-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="ebf60-128">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="ebf60-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="ebf60-129">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebf60-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="ebf60-130">**Nell'Skype for Business di amministrazione audioconferenza** Utenti , nel riquadro Azioni in ID >    >   **conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="ebf60-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="ebf60-131">Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="ebf60-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="ebf60-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="ebf60-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="ebf60-133">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ebf60-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ebf60-134">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebf60-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="ebf60-135">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ebf60-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="ebf60-136">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ebf60-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="ebf60-137">Dopo la creazione o la reimpostazione di un nuovo ID conferenza, il vecchio ID conferenza non può essere usato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="ebf60-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="ebf60-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="ebf60-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="ebf60-139">Gli utenti possono usare lo strumento Skype for Business migrazione delle riunioni per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="ebf60-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="ebf60-140">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: Strumento di aggiornamento delle riunioni per [Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business Online, Strumento di migrazione delle riunioni [(64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business Online, Strumento di migrazione delle riunioni [(32 bit).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="ebf60-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="ebf60-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ebf60-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="ebf60-142">L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="ebf60-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="ebf60-143">Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="ebf60-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="ebf60-144">L'ID conferenza per tutti gli utenti di audioconferenza sarà di 9 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ebf60-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ebf60-145">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ebf60-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ebf60-146">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="ebf60-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ebf60-147">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività.</span><span class="sxs-lookup"><span data-stu-id="ebf60-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ebf60-148">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="ebf60-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ebf60-149">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ebf60-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="ebf60-150">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebf60-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="ebf60-151">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ebf60-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ebf60-152">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ebf60-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="ebf60-153">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ebf60-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="ebf60-154">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ebf60-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="ebf60-155">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ebf60-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="ebf60-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ebf60-156">Related topics</span></span>

[<span data-ttu-id="ebf60-157">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="ebf60-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
