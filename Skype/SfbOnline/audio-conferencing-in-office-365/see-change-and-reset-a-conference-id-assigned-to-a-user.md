---
title: Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza a un utente in Skype per le aziende e quali la conferenza ID devono essere parametri. '
ms.openlocfilehash: 73c5d3cc95b7967cd9d6eaae83a14e19143e431b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2018
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="1a47f-103">Consente di visualizzare e reimpostare un ID conferenza assegnato a un utente</span><span class="sxs-lookup"><span data-stu-id="1a47f-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="1a47f-104">Al Skype per utenti Business o Microsoft Teams viene automaticamente assegnato un ID conferenza quando sono configurati per l'audioconferenza in Office 365 e utilizzare Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="1a47f-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="1a47f-105">L'ID conferenza assegnato viene inviato nell'invito alla riunione durante la riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="1a47f-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="1a47f-106">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="1a47f-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="1a47f-107">Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile che quando un utente non desidera utilizzare questo e si desidera impostare per un determinato numero o quando gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="1a47f-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="1a47f-108">È possibile utilizzare il **Skype per interfaccia di amministrazione di Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="1a47f-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="1a47f-109">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefinito o se si reimposta l'ID conferenza verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="1a47f-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="1a47f-110">Per ulteriori informazioni sulla reimpostazione PIN di un organizzatore della conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1a47f-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="1a47f-111">Consente di visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="1a47f-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="1a47f-112">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="1a47f-112">To view the conference ID</span></span>

<span data-ttu-id="1a47f-113">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="1a47f-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="1a47f-114">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="1a47f-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1a47f-115">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="1a47f-116">In **Servizi di conferenza Audio**, cercare nella casella **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1a47f-117">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza nella posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="1a47f-118">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="1a47f-119">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1a47f-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="1a47f-120">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="1a47f-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="1a47f-121">È possibile visualizzare l'ID conferenza e inviare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a47f-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="1a47f-122">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a47f-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a47f-123">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a47f-124">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, selezionare l'utente che ha necessità di ID conferenza</span><span class="sxs-lookup"><span data-stu-id="1a47f-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="1a47f-125">Nella pagina azione cercare nella casella **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1a47f-126">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="1a47f-127">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="1a47f-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="1a47f-128">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1a47f-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="1a47f-129">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="1a47f-129">To reset the conference ID</span></span>

<span data-ttu-id="1a47f-130">È possibile reimpostare un ID conferenza per un utente se, ad esempio, se si dimentica.</span><span class="sxs-lookup"><span data-stu-id="1a47f-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="1a47f-131">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="1a47f-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="1a47f-132">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="1a47f-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1a47f-133">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="1a47f-134">In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="1a47f-135">Nella finestra di **reimpostare ID conferenza** , fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="1a47f-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="1a47f-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="1a47f-137">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a47f-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="1a47f-138">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a47f-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="1a47f-139">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="1a47f-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1a47f-140">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a47f-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a47f-141">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1a47f-142">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="1a47f-143">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="1a47f-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="1a47f-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="1a47f-145">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a47f-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="1a47f-146">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a47f-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="1a47f-147">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="1a47f-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="1a47f-148">Dopo che viene creato un nuovo ID conferenza o una viene reimpostata, l'ID conferenza precedente non può essere utilizzato per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="1a47f-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="1a47f-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="1a47f-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="1a47f-150">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="1a47f-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="1a47f-151">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business dello strumento di migrazione di riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="1a47f-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="1a47f-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a47f-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="1a47f-153">L'ID conferenza deve soddisfare la lunghezza in cifre impostare ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="1a47f-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="1a47f-154">Non è possibile utilizzare caratteri speciali o alfabetici conferenza ID; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="1a47f-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="1a47f-155">L'ID conferenza per tutti gli utenti di audioconferenze con accesso esterno sarà 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="1a47f-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1a47f-156">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1a47f-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1a47f-p112">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="1a47f-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1a47f-160">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a47f-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1a47f-161">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="1a47f-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1a47f-p113">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a47f-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1a47f-164">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="1a47f-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1a47f-165">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a47f-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1a47f-166">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a47f-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1a47f-167">See also</span><span class="sxs-lookup"><span data-stu-id="1a47f-167">Related topics</span></span>

[<span data-ttu-id="1a47f-168">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="1a47f-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

