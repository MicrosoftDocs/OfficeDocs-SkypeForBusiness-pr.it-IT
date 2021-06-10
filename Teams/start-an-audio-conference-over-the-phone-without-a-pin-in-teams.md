---
title: Avviare l'audioconferenza tramite telefono senza un PIN in Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: "Informazioni su come abilitare o disabilitare la partecipazione di chiamanti anonimi a una riunione dall'Teams di amministrazione. "
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116964"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="d60ed-103">Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d60ed-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="d60ed-104">Può essere frustrante per gli utenti che a una riunione a una riunione si svolgono nella sala d'attesa della riunione ascoltando musica perché l'organizzatore della riunione di Microsoft Teams non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="d60ed-105">Se l'organizzatore della riunione chiama per impostazione predefinita, è necessario un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="d60ed-106">È possibile configurarla in modo che chiunque possa accedere a una riunione e non venga richiesto un PIN per avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="d60ed-107">È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="d60ed-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="d60ed-108">Non è necessario un PIN per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Microsoft Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="d60ed-109">Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="d60ed-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="d60ed-110">Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza **di audioconferenza** e viene abilitato per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="d60ed-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="d60ed-111">Vedere [Inviare un messaggio di posta](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) elettronica a un utente con le informazioni relative alle audioconferenze e i messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando cambiano le [impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d60ed-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="d60ed-112">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="d60ed-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="d60ed-113">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d60ed-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d60ed-114">Nel riquadro di spostamento sinistro fare clic su **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="d60ed-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="d60ed-115">Selezionare un utente nell'elenco e quindi fare clic **su Modifica** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="d60ed-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="d60ed-116">Accanto a **Audioconferenza** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="d60ed-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="d60ed-117">Nel riquadro **Audioconferenza,** abilitare o disabilitare i chiamanti con accesso esterno può essere la prima **persona in una riunione.**</span><span class="sxs-lookup"><span data-stu-id="d60ed-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="d60ed-118">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="d60ed-118">Click **Apply**.</span></span> 

<span data-ttu-id="d60ed-119">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d60ed-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="d60ed-120">Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="d60ed-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="d60ed-121">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d60ed-121">What else should you know?</span></span>

- <span data-ttu-id="d60ed-122">Per reimpostare il PIN, vedere Reimpostare [il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d60ed-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="d60ed-123">Se l'accesso anonimo o la richiesta di un PIN per avviare una riunione è disabilitata:</span><span class="sxs-lookup"><span data-stu-id="d60ed-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="d60ed-124">Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): un chiamante riceverà una richiesta se è l'organizzatore; se dice sì, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente si unirà alla riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="d60ed-125">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="d60ed-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="d60ed-126">Se l'accesso anonimo, o non richiede un PIN per avviare una riunione, è abilitato:</span><span class="sxs-lookup"><span data-stu-id="d60ed-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="d60ed-127">Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN.</span><span class="sxs-lookup"><span data-stu-id="d60ed-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="d60ed-128">Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.</span><span class="sxs-lookup"><span data-stu-id="d60ed-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="d60ed-129">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="d60ed-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d60ed-130">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d60ed-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d60ed-131">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="d60ed-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d60ed-132">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d60ed-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d60ed-133">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d60ed-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d60ed-134">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="d60ed-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d60ed-135">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d60ed-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="d60ed-136">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d60ed-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d60ed-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d60ed-137">Related topics</span></span>

[<span data-ttu-id="d60ed-138">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d60ed-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)