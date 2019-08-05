---
title: Team per l'infrastruttura desktop virtualizzata
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Informazioni su come eseguire Microsoft teams in un ambiente VDI (Virtualizzated Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 132bd532ae8f7da98edb38a81363b4d5b6501532
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "36184870"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="4d2a7-103">Team per l'infrastruttura desktop virtualizzata</span><span class="sxs-lookup"><span data-stu-id="4d2a7-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="4d2a7-104">In questo articolo vengono illustrati i requisiti e le limitazioni per l'uso di Microsoft teams in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="4d2a7-105">Che cos'è VDI?</span><span class="sxs-lookup"><span data-stu-id="4d2a7-105">What is VDI?</span></span>

<span data-ttu-id="4d2a7-106">Virtual Desktop Infrastructure (VDI) è la tecnologia di virtualizzazione che ospita un sistema operativo desktop e le applicazioni su un server centralizzato in un centro dati.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="4d2a7-107">Questo consente agli utenti un'esperienza desktop completamente personalizzata con una fonte centralizzata completamente sicura e conforme.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="4d2a7-108">Attualmente, i team in un ambiente virtualizzato sono disponibili con il supporto per la collaborazione e la funzionalità di chat con un computer virtualizzato persistente dedicato (VM).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="4d2a7-109">Per garantire un'esperienza utente ottimale, seguire le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="4d2a7-110">Requisiti per i team</span><span class="sxs-lookup"><span data-stu-id="4d2a7-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="4d2a7-111">Impostare i criteri per disattivare le funzionalità di chiamata e riunione in teams</span><span class="sxs-lookup"><span data-stu-id="4d2a7-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="4d2a7-112">L'esperienza di chiamata e riunione di teams non è ottimizzata per un ambiente VDI (presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="4d2a7-113">È consigliabile impostare i criteri a livello di utente per disattivare le funzionalità di chiamata e riunione in teams.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="4d2a7-114">Puoi comunque scegliere di eseguire teams completamente in VDI usando l'app desktop teams o l'app Web.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="4d2a7-115">Tuttavia, ti consigliamo di impostare i criteri per evitare di compromettere l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="4d2a7-116">Può essere necessario un po' di tempo (poche ore) per le modifiche ai criteri di propagazione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="4d2a7-117">Se non si vedono immediatamente le modifiche per un account specifico, riprovare in poche ore.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="4d2a7-118">Quando le chiamate e le riunioni di team sono ottimizzate per l'uso in ambienti desktop virtuali, è possibile ripristinare questi criteri e consentire agli utenti di usare i team in modo normale.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="4d2a7-119">Chiamate</span><span class="sxs-lookup"><span data-stu-id="4d2a7-119">Calling</span></span>

<span data-ttu-id="4d2a7-120">USA i cmdlet **CSTeamsCallingPolicy** per controllare se gli utenti possono usare le opzioni di chiamata e chiamata in chat private e di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="4d2a7-121">Ecco l'elenco delle impostazioni dei criteri e i valori consigliati.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="4d2a7-122">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="4d2a7-122">Policy name</span></span>  |<span data-ttu-id="4d2a7-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-123">Description</span></span> |<span data-ttu-id="4d2a7-124">Valore consigliato</span><span class="sxs-lookup"><span data-stu-id="4d2a7-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4d2a7-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="4d2a7-125">AllowCalling</span></span>    |<span data-ttu-id="4d2a7-126">Controlla le funzionalità delle chiamate di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="4d2a7-127">Questa operazione consente agli utenti di Skype for business di avere chiamate uno-a-uno con gli utenti di team e viceversa.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="4d2a7-128">Impostare su false per evitare che le chiamate di utenti di Skype for business vengano sbarcate in teams.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="4d2a7-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="4d2a7-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="4d2a7-130">Controlla se l'app chiamante è disponibile nella barra dell'app sul lato sinistro del client teams e se gli utenti vedono le opzioni per le chiamate e le videochiamate nella chat privata</span><span class="sxs-lookup"><span data-stu-id="4d2a7-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="4d2a7-131">Impostare su false per rimuovere l'app chiamante dalla barra dell'app sul lato sinistro di teams e per rimuovere le opzioni per la chiamata e la videochiamata in chat privata.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="4d2a7-132">Creare e assegnare un criterio di chiamata</span><span class="sxs-lookup"><span data-stu-id="4d2a7-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="4d2a7-133">Avviare una sessione di Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="4d2a7-134">Connettersi al connettore Skype online.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="4d2a7-135">Visualizzare un elenco di opzioni dei criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="4d2a7-136">Cercare l'opzione criteri predefiniti in cui sono disabilitati tutti i criteri di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="4d2a7-137">Ha un aspetto simile a questo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="4d2a7-138">Applicare l'opzione dei criteri predefiniti di DisallowCalling a tutti gli utenti che useranno teams in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="4d2a7-139">Per altre informazioni sui criteri di chiamata dei team, vedere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="4d2a7-140"> Riunioni</span><span class="sxs-lookup"><span data-stu-id="4d2a7-140">Meetings</span></span>

<span data-ttu-id="4d2a7-141">Usare i cmdlet **CsTeamsMeetingPolicy** per controllare il tipo di riunioni che gli utenti possono creare, le caratteristiche a cui possono accedere durante una riunione e le caratteristiche della riunione disponibili per gli utenti anonimi ed esterni.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="4d2a7-142">Ecco l'elenco delle impostazioni dei criteri e i valori consigliati.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="4d2a7-143">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="4d2a7-143">Policy Name</span></span> |<span data-ttu-id="4d2a7-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-144">Description</span></span>|<span data-ttu-id="4d2a7-145">Valore consigliato</span><span class="sxs-lookup"><span data-stu-id="4d2a7-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="4d2a7-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="4d2a7-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="4d2a7-147">Determina se un utente può pianificare riunioni private.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="4d2a7-148">Impostato su false per impedire che l'utente possa pianificare riunioni private.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="4d2a7-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="4d2a7-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="4d2a7-150">Determina se un utente è autorizzato a pianificare le riunioni del canale.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="4d2a7-151">Impostare su false per impedire che l'utente possa pianificare le riunioni del canale.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="4d2a7-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="4d2a7-152">AllowMeetNow</span></span> |<span data-ttu-id="4d2a7-153">Determina se un utente può creare o avviare riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="4d2a7-154">Imposta questo valore su false per impedire che l'utente possa avviare riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="4d2a7-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="4d2a7-155">ScreenSharingMode</span></span> | <span data-ttu-id="4d2a7-156">Determina la modalità in cui un utente può condividere lo schermo in chiamate o riunioni.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="4d2a7-157">Impostato su Disabled per impedire all'utente di condividere gli schermi</span><span class="sxs-lookup"><span data-stu-id="4d2a7-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="4d2a7-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="4d2a7-158">AllowIPVideo</span></span> |<span data-ttu-id="4d2a7-159">Determina se il video è abilitato nelle riunioni o nelle chiamate di un utente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="4d2a7-160">Impostato su false per impedire all'utente di condividere il video</span><span class="sxs-lookup"><span data-stu-id="4d2a7-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="4d2a7-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="4d2a7-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="4d2a7-162">Determina se gli utenti anonimi possono effettuare la chiamata a un numero PSTN.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="4d2a7-163">Impostato su false per impedire la chiamata degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="4d2a7-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="4d2a7-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="4d2a7-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="4d2a7-165">Determina se gli utenti anonimi possono avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="4d2a7-166">Impostare su false per impedire agli utenti di avviare una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="4d2a7-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="4d2a7-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="4d2a7-168">Determina se un utente può pianificare le riunioni di Teams nel client desktop di Outlook.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="4d2a7-169">Impostato su false per impedire a un utente di pianificare le riunioni di Teams nel client desktop di Outlook</span><span class="sxs-lookup"><span data-stu-id="4d2a7-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="4d2a7-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="4d2a7-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="4d2a7-171">Determina se i partecipanti possono richiedere o dare il controllo della condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="4d2a7-172">Impostato su false per impedire all'utente di concedere e richiedere il controllo in una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="4d2a7-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="4d2a7-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="4d2a7-174">Determina se i partecipanti esterni possono richiedere o dare il controllo della condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="4d2a7-175">Impostato su false per impedire l'assegnazione di un utente esterno, richiedendo il controllo in una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="4d2a7-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="4d2a7-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="4d2a7-177">Determina se la condivisione di PowerPoint è consentita nelle riunioni di un utente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="4d2a7-178">Impostato su false per impedire a un utente di condividere i file di PowerPoint in una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="4d2a7-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="4d2a7-179">AllowWhiteboard</span></span> | <span data-ttu-id="4d2a7-180">Determina se la lavagna è consentita nelle riunioni di un utente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="4d2a7-181">Impostare su false per impedire la lavagna in una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="4d2a7-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="4d2a7-182">AllowTranscription</span></span> |<span data-ttu-id="4d2a7-183">Determina se le didascalie e le trascrizioni in tempo reale e/o post-riunione sono consentite nelle riunioni di un utente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="4d2a7-184">Impostare su false per impedire la trascrizione e le didascalie in una riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="4d2a7-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="4d2a7-185">AllowSharedNotes</span></span> | <span data-ttu-id="4d2a7-186">Determina se gli utenti possono prendere note condivise.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="4d2a7-187">Impostato su false per impedire agli utenti di accettare note condivise</span><span class="sxs-lookup"><span data-stu-id="4d2a7-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="4d2a7-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="4d2a7-188">MediaBitRateKB</span></span> |<span data-ttu-id="4d2a7-189">Determina la velocità in bit media per le trasmissioni di condivisione audio/video/app nelle riunioni</span><span class="sxs-lookup"><span data-stu-id="4d2a7-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="4d2a7-190">Il valore suggerito è 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="4d2a7-191">È possibile modificarla in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="4d2a7-192">Creare e assegnare un criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="4d2a7-193">Avviare una sessione di Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="4d2a7-194">Connettersi al connettore Skype online.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="4d2a7-195">Visualizzare un elenco delle opzioni dei criteri di riunione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="4d2a7-196">Cercare l'opzione criteri predefiniti in cui sono disabilitati tutti i criteri riunione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="4d2a7-197">Ha un aspetto simile a questo.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="4d2a7-198">Applicare l'opzione dei criteri predefiniti di AllOff a tutti gli utenti che useranno teams in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="4d2a7-199">Per altre informazioni sui criteri di riunione dei team, vedere [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="4d2a7-200">Requisiti del provider di virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-200">Virtualization provider requirements</span></span>

<span data-ttu-id="4d2a7-201">L'app teams è stata convalidata nei principali provider di soluzioni di virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="4d2a7-202">Con più fornitori di mercato, consulta il provider di soluzioni di virtualizzazione per verificare che siano soddisfatti i requisiti minimi.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="4d2a7-203">Requisiti della macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="4d2a7-203">Virtual Machine requirements</span></span>

<span data-ttu-id="4d2a7-204">Con i diversi carichi di lavoro e le esigenze degli utenti in un ambiente virtualizzato, di seguito è riportata la configurazione minima consigliata per le VM.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="4d2a7-205">Parametro</span><span class="sxs-lookup"><span data-stu-id="4d2a7-205">Parameter</span></span>  |<span data-ttu-id="4d2a7-206">Misura</span><span class="sxs-lookup"><span data-stu-id="4d2a7-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="4d2a7-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="4d2a7-207">vCPU</span></span>    |  <span data-ttu-id="4d2a7-208">2 Core</span><span class="sxs-lookup"><span data-stu-id="4d2a7-208">2 cores</span></span>       |
|<span data-ttu-id="4d2a7-209">RAM</span><span class="sxs-lookup"><span data-stu-id="4d2a7-209">RAM</span></span>     |  <span data-ttu-id="4d2a7-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="4d2a7-210">4 GB</span></span>      |
|<span data-ttu-id="4d2a7-211">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="4d2a7-211">Storage</span></span>     | <span data-ttu-id="4d2a7-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="4d2a7-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="4d2a7-213">Requisiti del sistema operativo della macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="4d2a7-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="4d2a7-214">I sistemi operativi supportati per VM sono:</span><span class="sxs-lookup"><span data-stu-id="4d2a7-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="4d2a7-215">Windows 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4d2a7-215">Windows 10 and later</span></span>
- <span data-ttu-id="4d2a7-216">Windows Server 2012 R2 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4d2a7-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="4d2a7-217">Installare teams su VDI</span><span class="sxs-lookup"><span data-stu-id="4d2a7-217">Install Teams on VDI</span></span>

<span data-ttu-id="4d2a7-218">Ecco il processo e gli strumenti per distribuire l'app desktop teams.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="4d2a7-219">Scaricare il pacchetto MSI teams usando uno dei collegamenti seguenti, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="4d2a7-220">È consigliabile usare la versione a 64 bit per una VM VDI con un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="4d2a7-221">versione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="4d2a7-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="4d2a7-222">versione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="4d2a7-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="4d2a7-223">Eseguire il comando seguente per installare il file MSI nella VM VDI o per completare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="4d2a7-224">Questo consente di installare i team nei file di programma.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="4d2a7-225">A questo punto, la configurazione dell'immagine dorata è completa.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="4d2a7-226">La prossima sessione di accesso interattivo avvia team e richiede le credenziali.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="4d2a7-227">Tieni presente che non è possibile disabilitare l'avvio automatico dei team durante l'installazione di teams in VDI tramite la proprietà ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="4d2a7-228">Eseguire il comando seguente per disinstallare il file MSI dalla VM VDI o prepararsi per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="4d2a7-229">In questo articolo vengono disinstallati team da file di programma.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="4d2a7-230">Problemi noti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="4d2a7-230">Known issues and limitations</span></span>

<span data-ttu-id="4d2a7-231">Di seguito sono riportati i problemi noti e le limitazioni per i team in VDI.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="4d2a7-232">**Distribuzioni di tipo host sessione condivisa**: le distribuzioni di tipo host sessione condivisa, ad esempio la configurazione della VM non persistente condivisa, non sono nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="4d2a7-233">**Chiamate e riunioni**:</span><span class="sxs-lookup"><span data-stu-id="4d2a7-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="4d2a7-234">Gli scenari di chiamata e riunione non sono ottimizzati per VDI.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="4d2a7-235">Questi scenari si esibiranno male.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="4d2a7-236">È consigliabile usare criteri a livello di utente come descritto nella sezione [Imposta criteri per disattivare le funzionalità di chiamata e riunione in teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="4d2a7-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="4d2a7-237">Applicando i criteri descritti in questo articolo si ha un impatto sulla possibilità di usare le funzionalità di chiamata e riunione, che a seconda di altri criteri possono influire su altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="4d2a7-238">Se gli utenti dell'organizzazione usano client non VDI, è possibile scegliere di non applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="4d2a7-239">**Partecipare a chiamate e riunioni create da altri utenti**: anche se i criteri impediscono agli utenti di creare riunioni, possono ancora partecipare alle riunioni se un altro utente effettua la chiamata dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="4d2a7-240">In queste riunioni, la possibilità dell'utente di condividere video, usare lavagna e altre funzionalità dipende dal fatto che siano state disabilitate le caratteristiche usando TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="4d2a7-241">**Contenuto memorizzato nella cache**: se l'ambiente virtuale in cui il team è in esecuzione non è persistente (e i dati vengono eliminati alla fine di ogni sessione utente), gli utenti potrebbero notare il degrado delle prestazioni a causa dell'aggiornamento del contenuto, indipendentemente dal fatto che l'utente abbia eseguito la stessa operazione contenuto di una sessione precedente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="4d2a7-242">**Aggiornamenti client**: teams on VDI non viene aggiornato automaticamente con l'installazione MSI per computer.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-242">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="4d2a7-243">È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nella sezione [installare teams in VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="4d2a7-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="4d2a7-244">Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="4d2a7-245">**Esperienza utente**: l'esperienza utente di teams in un ambiente VDI può essere diversa da un ambiente non VDI.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="4d2a7-246">Le differenze potrebbero essere causate dalle impostazioni dei criteri e/o dal supporto delle funzionalità nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="4d2a7-247">Per i problemi noti relativi ai team che non sono correlati a VDI, vedere [problemi noti di Microsoft teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4d2a7-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d2a7-248">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4d2a7-248">Related topics</span></span>

- [<span data-ttu-id="4d2a7-249">Installare Microsoft teams con MSI</span><span class="sxs-lookup"><span data-stu-id="4d2a7-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
