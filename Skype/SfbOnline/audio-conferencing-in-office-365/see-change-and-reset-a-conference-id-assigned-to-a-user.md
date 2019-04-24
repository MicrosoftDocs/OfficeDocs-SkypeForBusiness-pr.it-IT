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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype for Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: eb7d42fa88c54b917e89eb97ce9f52bd03af4935
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229332"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="27926-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="27926-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="27926-104">Per informazioni sugli ID di conferenza utente in Microsoft Teams, consulta [Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="27926-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="27926-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="27926-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="27926-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="27926-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="27926-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="27926-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="27926-112">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="27926-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="27926-113">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="27926-113">To view the conference ID</span></span>

<span data-ttu-id="27926-114">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="27926-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="27926-115">È possibile visualizzare l'ID conferenza e inviarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="27926-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="27926-116">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="27926-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="27926-117">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="27926-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="27926-118">Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="27926-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="27926-119">Nella pagina Azione, cerca in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="27926-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="27926-120">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="27926-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="27926-121">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27926-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="27926-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="27926-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="27926-124">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="27926-124">To reset the conference ID</span></span>

<span data-ttu-id="27926-125">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="27926-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="27926-126">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="27926-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="27926-127">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="27926-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="27926-128">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="27926-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="27926-129">In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="27926-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="27926-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="27926-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="27926-132">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27926-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="27926-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="27926-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="27926-135">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="27926-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="27926-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="27926-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="27926-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27926-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="27926-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="27926-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="27926-143">L'ID conferenza per tutti gli utenti di audioconferenze sarà di 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="27926-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="27926-144">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="27926-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="27926-p109">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="27926-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="27926-148">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="27926-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="27926-149">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="27926-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="27926-p110">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27926-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="27926-152">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="27926-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="27926-153">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="27926-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="27926-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="27926-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="27926-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="27926-155">Related topics</span></span>

[<span data-ttu-id="27926-156">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="27926-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

