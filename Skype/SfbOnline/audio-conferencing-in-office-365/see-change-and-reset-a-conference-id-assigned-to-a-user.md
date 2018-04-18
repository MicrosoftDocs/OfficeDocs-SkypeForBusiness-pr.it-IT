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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza a un utente in Skype per le aziende e quali la conferenza ID devono essere parametri. '
ms.openlocfilehash: 5ce378b7c81fac3700e813a011c9dbafcc95eb8a
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="c927a-103">Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente</span><span class="sxs-lookup"><span data-stu-id="c927a-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="c927a-104">Al Skype per utenti Business o Microsoft Teams viene automaticamente assegnato un ID conferenza quando sono configurati per l'audioconferenza in Office 365 e utilizzare Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="c927a-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c927a-105">L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla riunione durante la riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="c927a-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="c927a-106">ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare.</span><span class="sxs-lookup"><span data-stu-id="c927a-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="c927a-107">Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="c927a-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="c927a-108">Se si desidera assegnare dinamico anziché gli ID, [fare clic qui](using-audio-conferencing-dynamic-ids-in-your-organization.md)di conferenza statico.</span><span class="sxs-lookup"><span data-stu-id="c927a-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="c927a-109">Benché un ID conferenza statica verrà automaticamente creato e assegnato a un utente, è possibile che quando un utente non desidera utilizzare questo e si desidera impostare per un determinato numero o quando gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="c927a-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="c927a-110">È possibile utilizzare il **Skype per interfaccia di amministrazione di Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="c927a-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="c927a-111">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefinito o se si reimposta l'ID conferenza verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="c927a-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="c927a-112">Visualizzare e modificare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="c927a-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="c927a-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="c927a-113">To view the conference ID</span></span>

<span data-ttu-id="c927a-114">È possibile visualizzare l'ID conferenza e inviare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c927a-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="c927a-115">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c927a-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c927a-116">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c927a-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c927a-117">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, selezionare l'utente che ha necessità di ID conferenza</span><span class="sxs-lookup"><span data-stu-id="c927a-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="c927a-118">Nella pagina azione cercare nella casella **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="c927a-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c927a-119">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="c927a-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="c927a-120">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="c927a-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="c927a-121">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c927a-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="c927a-122">Vedere [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) per ulteriori informazioni sul cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c927a-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="c927a-123">Per assegnare o modificare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="c927a-123">To assign or change the conference ID</span></span>

<span data-ttu-id="c927a-124">È possibile assegnare o modificare un ID conferenza per un utente se, ad esempio, si viene invitati un ID conferenza facile da ricordare.</span><span class="sxs-lookup"><span data-stu-id="c927a-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c927a-125">Skype per interfaccia di amministrazione di Business non può essere utilizzato per modificare un ID conferenza che è stato creato automaticamente, ma è possibile utilizzare Windows PowerShell per modificare o cambiare un ID conferenza che è stata impostata.</span><span class="sxs-lookup"><span data-stu-id="c927a-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="c927a-126">Per modificare o cambiare l'ID conferenza per un utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c927a-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="c927a-127">Un ID conferenza deve contenere 7 cifre e non è possibile modificare in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c927a-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="c927a-128">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="c927a-128">To reset the conference ID</span></span>

<span data-ttu-id="c927a-129">È possibile reimpostare un ID conferenza per un utente se, ad esempio, se si dimentica.</span><span class="sxs-lookup"><span data-stu-id="c927a-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="c927a-130">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c927a-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c927a-131">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c927a-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c927a-132">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="c927a-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="c927a-133">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c927a-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c927a-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="c927a-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="c927a-135">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c927a-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="c927a-136">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c927a-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="c927a-137">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="c927a-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="c927a-138">Dopo che viene creato un nuovo ID conferenza o una viene reimpostata, l'ID conferenza precedente non può essere utilizzato per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="c927a-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c927a-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="c927a-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c927a-140">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="c927a-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c927a-141">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business dello strumento di migrazione di riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="c927a-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="c927a-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c927a-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="c927a-143">L'ID conferenza deve soddisfare la lunghezza in cifre impostare ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="c927a-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="c927a-144">Non è possibile utilizzare caratteri speciali o alfabetici conferenza ID; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="c927a-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="c927a-145">L'ID conferenza per tutti gli utenti di audioconferenze con accesso esterno sarà 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="c927a-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c927a-146">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c927a-146">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c927a-p109">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="c927a-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c927a-150">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c927a-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c927a-151">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c927a-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c927a-p110">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c927a-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c927a-154">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="c927a-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c927a-155">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c927a-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c927a-156">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c927a-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c927a-157">See also</span><span class="sxs-lookup"><span data-stu-id="c927a-157">Related topics</span></span>

[<span data-ttu-id="c927a-158">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="c927a-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

