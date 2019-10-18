---
title: Visualizzare, modificare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come assegnare un ID conferenza a un utente in Microsoft teams e quali sono i parametri dell'ID conferenza. "
ms.openlocfilehash: d134a3664a6cee588d08f3d1a33bc6018d97a1fa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571338"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="6c892-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c892-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="6c892-104">Un ID conferenza viene assegnato automaticamente a un utente di Microsoft teams quando è configurato per le conferenze audio in Office 365 e USA Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6c892-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="6c892-105">L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è programmata.</span><span class="sxs-lookup"><span data-stu-id="6c892-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="6c892-106">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="6c892-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="6c892-107">Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, potrebbero esserci momenti in cui un utente non vuole usarlo e si vuole impostarlo su un certo numero o quando gli utenti non riescono a ricordare o hanno perso l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="6c892-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="6c892-108">Puoi usare l'interfaccia di amministrazione di Microsoft teams o Windows PowerShell per visualizzare, modificare e reimpostare l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="6c892-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="6c892-109">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="6c892-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="6c892-110">Per ulteriori informazioni sulla reimpostazione del PIN dell'organizzatore di una conferenza, [fare clic qui](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6c892-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="6c892-111">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="6c892-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="6c892-112">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="6c892-112">To view the conference ID</span></span>

<span data-ttu-id="6c892-113">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="6c892-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6c892-114">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="6c892-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6c892-115">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c892-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="6c892-116">In servizi di **audioconferenza**, vedere in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="6c892-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6c892-117">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza nel messaggio di posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="6c892-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="6c892-118">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6c892-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="6c892-119">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="6c892-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="6c892-120">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="6c892-120">To reset the conference ID</span></span>

<span data-ttu-id="6c892-121">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="6c892-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="6c892-122">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="6c892-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6c892-123">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="6c892-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6c892-124">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c892-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="6c892-125">In **audioconferenza**fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="6c892-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="6c892-126">Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="6c892-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="6c892-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="6c892-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="6c892-128">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6c892-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="6c892-129">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="6c892-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="6c892-130">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="6c892-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="6c892-131">Dopo la creazione di un nuovo ID conferenza o di un reset, il vecchio ID conferenza non può essere usato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="6c892-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="6c892-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="6c892-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="6c892-133">L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="6c892-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="6c892-134">Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="6c892-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6c892-135">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c892-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6c892-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6c892-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6c892-139">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="6c892-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6c892-140">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c892-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6c892-141">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6c892-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6c892-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c892-142">Related topics</span></span>

[<span data-ttu-id="6c892-143">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="6c892-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

