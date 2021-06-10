---
title: Visualizzare, modificare e reimpostare l'ID conferenza di un utente
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Informazioni su come assegnare un ID conferenza a un utente in Microsoft Teams i parametri degli ID conferenza.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117209"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="2f987-103">Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f987-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="2f987-104">Un ID conferenza viene assegnato automaticamente a un utente Microsoft Teams quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e usa Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="2f987-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="2f987-105">L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è pianificata.</span><span class="sxs-lookup"><span data-stu-id="2f987-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="2f987-106">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="2f987-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="2f987-107">Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure quando gli utenti non ricordano o non hanno perso l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="2f987-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="2f987-108">È possibile usare l Microsoft Teams di amministrazione o Windows PowerShell per visualizzare, modificare e reimpostare l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="2f987-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="2f987-109">Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN.</span><span class="sxs-lookup"><span data-stu-id="2f987-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="2f987-110">Per altre informazioni su come reimpostare il PIN di un organizzatore della conferenza, vedere Reimpostare un ID conferenza per un utente [in Microsoft Teams.](reset-a-conference-id-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="2f987-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="2f987-111">Visualizzare e reimpostare gli ID conferenza</span><span class="sxs-lookup"><span data-stu-id="2f987-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="2f987-112">Per visualizzare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="2f987-112">To view the conference ID</span></span>

<span data-ttu-id="2f987-113">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="2f987-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2f987-114">Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2f987-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2f987-115">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f987-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="2f987-116">In **Audioconferenza** cercare in **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="2f987-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2f987-117">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento Invia informazioni conferenza **tramite posta** elettronica.</span><span class="sxs-lookup"><span data-stu-id="2f987-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="2f987-118">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2f987-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2f987-119">Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="2f987-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="2f987-120">Per reimpostare l'ID conferenza</span><span class="sxs-lookup"><span data-stu-id="2f987-120">To reset the conference ID</span></span>

<span data-ttu-id="2f987-121">È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.</span><span class="sxs-lookup"><span data-stu-id="2f987-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="2f987-122">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="2f987-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2f987-123">Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2f987-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2f987-124">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f987-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="2f987-125">In **Audioconferenza** fare clic **su Reimposta ID conferenza.**</span><span class="sxs-lookup"><span data-stu-id="2f987-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="2f987-126">Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="2f987-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="2f987-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="2f987-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="2f987-128">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2f987-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2f987-129">Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="2f987-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="2f987-130">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2f987-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="2f987-131">Dopo la creazione o la reimpostazione di un nuovo ID conferenza, il vecchio ID conferenza non può essere usato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="2f987-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2f987-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="2f987-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="2f987-133">L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="2f987-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="2f987-134">Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.</span><span class="sxs-lookup"><span data-stu-id="2f987-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2f987-135">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2f987-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2f987-136">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="2f987-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2f987-137">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="2f987-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2f987-138">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f987-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2f987-139">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="2f987-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="2f987-140">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2f987-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="2f987-141">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2f987-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2f987-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2f987-142">Related topics</span></span>

[<span data-ttu-id="2f987-143">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="2f987-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)