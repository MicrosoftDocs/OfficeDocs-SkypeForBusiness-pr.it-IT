---
title: Vedere, modificare e ripristinare un ID conferenza assegnato a un utente su Skype for Business online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype for Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: d47e188220f66e320289384c4fbe421328d8eca3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850186"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="01db9-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="01db9-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="01db9-104">Per informazioni sugli ID di conferenza utente in Microsoft Teams, consulta [Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="01db9-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="01db9-105">Un ID conferenza viene assegnato automaticamente a un utente Skype for Business quando questo è configurato per l'audioconferenza in Office 365 e utilizza Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="01db9-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="01db9-106">L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione viene pianificata.</span><span class="sxs-lookup"><span data-stu-id="01db9-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="01db9-107">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="01db9-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="01db9-108">Benché un ID conferenza venga automaticamente creato e assegnato a un utente, può succedere che un utente non desideri utilizzarlo, che voglia impostare un determinato numero, che non se lo ricordi o che lo perda.</span><span class="sxs-lookup"><span data-stu-id="01db9-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="01db9-109">È possibile utilizzare l'**interfaccia di amministrazione di Skype for Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="01db9-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="01db9-110">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="01db9-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="01db9-111">Per ulteriori informazioni sulla reimpostazione del PIN dell'organizzatore di una conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="01db9-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="01db9-112">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="01db9-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="01db9-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="01db9-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="01db9-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'Interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="01db9-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="01db9-115">È possibile visualizzare l'ID conferenza e inviarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="01db9-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="01db9-116">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="01db9-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01db9-117">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="01db9-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01db9-118">Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="01db9-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="01db9-119">Nella pagina Azione, cerca in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="01db9-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="01db9-120">Puoi inviare tutte le informazioni sulla conferenza all'utente in un'email che include l'ID conferenza e i numeri di telefono audio, facendo clic sul collegamento Invia informazioni sulla conferenza tramite posta elettronica dopo aver selezionato l'utente nella pagina Utenti.\*\* \*\* \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="01db9-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="01db9-121">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="01db9-121">**Using Windows PowerShell to manage Lync Online**</span></span>

<span data-ttu-id="01db9-122">È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="01db9-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="01db9-123">Per fare ciò, esegui:</span><span class="sxs-lookup"><span data-stu-id="01db9-123">To do this, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="01db9-124">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="01db9-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="01db9-125">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="01db9-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="01db9-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'Interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="01db9-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="01db9-127">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="01db9-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="01db9-128">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="01db9-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="01db9-129">Nell'**Interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, nel riquadro Azioni su **ID conferenza**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="01db9-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="01db9-130">Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="01db9-130">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span></span> <span data-ttu-id="01db9-131">Verrà creato automaticamente un ID conferenza e verrà inviata un'email all'utente con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="01db9-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="01db9-132">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="01db9-132">**Using Windows PowerShell to manage Lync Online**</span></span>

<span data-ttu-id="01db9-133">È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01db9-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="01db9-134">Per fare ciò, esegui:</span><span class="sxs-lookup"><span data-stu-id="01db9-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="01db9-135">Quali altre informazioni ti servono?</span><span class="sxs-lookup"><span data-stu-id="01db9-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="01db9-136">Una volta reimpostato un ID conferenza o creato uno nuovo, quello precedente non può essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="01db9-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="01db9-137">È necessario invitare gli utenti a pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti.</span><span class="sxs-lookup"><span data-stu-id="01db9-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="01db9-138">Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="01db9-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="01db9-139">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento delle riunioni per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="01db9-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="01db9-140">Consulta [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) per ulteriori informazioni sul cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01db9-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="01db9-141">L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="01db9-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="01db9-142">Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="01db9-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="01db9-143">L'ID conferenza per tutti gli utenti di audioconferenze sarà di 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="01db9-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="01db9-144">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="01db9-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="01db9-p109">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="01db9-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="01db9-148">Introduzione a Windows PowerShell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="01db9-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="01db9-149">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="01db9-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="01db9-p110">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="01db9-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="01db9-152">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="01db9-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="01db9-153">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="01db9-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="01db9-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="01db9-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="01db9-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="01db9-155">Related topics</span></span>

[<span data-ttu-id="01db9-156">Provare o acquistare Audioconferenza in Office 365</span><span class="sxs-lookup"><span data-stu-id="01db9-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

