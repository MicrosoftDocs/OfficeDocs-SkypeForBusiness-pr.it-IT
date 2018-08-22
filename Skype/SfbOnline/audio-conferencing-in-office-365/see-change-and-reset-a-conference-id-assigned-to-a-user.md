---
title: Vedere, modificare e ripristinare un ID conferenza assegnato a un utente in Skype Business online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: 19a5af7a3a9a06e99556eda09f00566843551a34
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490636"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="28f3c-103">Consente di visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="28f3c-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="28f3c-104">Per informazioni sulla conferenza utente ID in Teams Microsoft, vedere [View e reimpostare un ID conferenza assegnato a un utente in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="28f3c-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="28f3c-105">Un ID conferenza viene assegnato a un Skype per gli utenti aziendali automaticamente quando sono configurati per l'audioconferenza in Office 365 e utilizzare Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="28f3c-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="28f3c-106">L'ID conferenza assegnato viene inviato nell'invito alla riunione durante la riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="28f3c-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="28f3c-107">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="28f3c-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="28f3c-108">Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile che quando un utente non desidera utilizzare questo e si desidera impostare per un determinato numero o quando gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="28f3c-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="28f3c-109">È possibile utilizzare il **Skype per interfaccia di amministrazione di Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="28f3c-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="28f3c-110">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefinito o se si reimposta l'ID conferenza verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="28f3c-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="28f3c-111">Per ulteriori informazioni sulla reimpostazione PIN di un organizzatore della conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="28f3c-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="28f3c-112">Consente di visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="28f3c-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="28f3c-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="28f3c-113">To view the conference ID</span></span>

<span data-ttu-id="28f3c-114">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="28f3c-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="28f3c-115">È possibile visualizzare l'ID conferenza e inviare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="28f3c-115">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="28f3c-116">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="28f3c-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="28f3c-117">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="28f3c-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="28f3c-118">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, selezionare l'utente che ha necessità di ID conferenza</span><span class="sxs-lookup"><span data-stu-id="28f3c-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="28f3c-119">Nella pagina azione cercare nella casella **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="28f3c-119">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="28f3c-120">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="28f3c-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="28f3c-121">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="28f3c-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="28f3c-122">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="28f3c-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="28f3c-123">A tale scopo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="28f3c-123">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="28f3c-124">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="28f3c-124">To reset the conference ID</span></span>

<span data-ttu-id="28f3c-125">Se, ad esempio, si dimentica, è possibile reimpostare un ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="28f3c-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>
 
<span data-ttu-id="28f3c-126">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="28f3c-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="28f3c-127">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="28f3c-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="28f3c-128">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="28f3c-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="28f3c-129">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="28f3c-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="28f3c-130">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="28f3c-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="28f3c-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="28f3c-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
<span data-ttu-id="28f3c-132">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="28f3c-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="28f3c-133">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28f3c-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="28f3c-134">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="28f3c-134">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="28f3c-135">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="28f3c-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="28f3c-136">Dopo che viene creato un nuovo ID conferenza o una viene reimpostata, l'ID conferenza precedente non può essere utilizzato per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="28f3c-136">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="28f3c-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="28f3c-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="28f3c-138">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="28f3c-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="28f3c-139">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business dello strumento di migrazione di riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="28f3c-139">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="28f3c-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28f3c-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="28f3c-141">L'ID conferenza deve soddisfare la lunghezza in cifre impostare ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="28f3c-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="28f3c-142">Non è possibile utilizzare caratteri speciali o alfabetici conferenza ID; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="28f3c-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="28f3c-143">L'ID conferenza per tutti gli utenti di audioconferenze con accesso esterno sarà 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="28f3c-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="28f3c-144">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="28f3c-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="28f3c-p109">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="28f3c-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="28f3c-148">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="28f3c-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="28f3c-149">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="28f3c-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="28f3c-p110">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="28f3c-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="28f3c-152">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="28f3c-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="28f3c-153">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="28f3c-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="28f3c-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="28f3c-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="28f3c-155">See also</span><span class="sxs-lookup"><span data-stu-id="28f3c-155">Related topics</span></span>

[<span data-ttu-id="28f3c-156">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="28f3c-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

