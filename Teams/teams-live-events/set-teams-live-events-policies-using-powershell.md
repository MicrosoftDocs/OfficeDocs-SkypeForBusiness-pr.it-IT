---
title: Usare PowerShell per impostare i criteri degli eventi dinamici
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Esempi di come usare PowerShell per impostare i criteri in teams per controllare chi può contenere eventi dinamici nell'organizzazione e le funzionalità disponibili negli eventi.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e49c2dca91dca56366dd6b8a8ce460547043c120
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369151"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="46efe-103">Usare PowerShell per impostare i criteri degli eventi dinamici in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46efe-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="46efe-104">Puoi usare i cmdlet di Windows PowerShell seguenti per impostare e assegnare le impostazioni dei criteri per gli eventi dinamici in teams:</span><span class="sxs-lookup"><span data-stu-id="46efe-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="46efe-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="46efe-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="46efe-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="46efe-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="46efe-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="46efe-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="46efe-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="46efe-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="46efe-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="46efe-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="46efe-110">Ecco alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="46efe-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="46efe-111">Prima di poter eseguire questi cmdlet, è necessario essere connessi a PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="46efe-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="46efe-112">Per altre informazioni, vedere [gestire Skype for business online con Microsoft 365 o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="46efe-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="46efe-113">Consentire agli utenti di pianificare eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="46efe-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="46efe-114">Questi esempi sono per gli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="46efe-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="46efe-115">Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="46efe-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="46efe-116">Per altre informazioni, vedere [consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="46efe-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="46efe-117">**Consentire a un utente di pianificare eventi dinamici**</span><span class="sxs-lookup"><span data-stu-id="46efe-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="46efe-118">Se all'utente viene assegnato il criterio globale, eseguire e verificare che il parametro *AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="46efe-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="46efe-119">Assegnare quindi l'utente al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="46efe-120">Scenari utente</span><span class="sxs-lookup"><span data-stu-id="46efe-120">User scenarios</span></span>
<span data-ttu-id="46efe-121">**Si vuole che tutti gli utenti dell'organizzazione possano pianificare eventi dinamici**</span><span class="sxs-lookup"><span data-stu-id="46efe-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="46efe-122">Se agli utenti viene assegnato il criterio globale, eseguire e verificare che *AllowBroadcastScheduling* \* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="46efe-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="46efe-123">Se agli utenti viene assegnato un criterio diverso dal criterio globale, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="46efe-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="46efe-124">**Si vuole che la programmazione di eventi dinamici venga disabilitata nell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="46efe-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="46efe-125">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="46efe-126">Assegnare tutti gli utenti dell'organizzazione al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="46efe-127">**Si vuole che un numero elevato di utenti sia in grado di programmare eventi dinamici e impedire a un gruppo di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="46efe-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="46efe-128">Eseguire e verificare che *AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="46efe-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="46efe-129">Assegnare quindi un utente o utenti al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="46efe-130">Creare un nuovo criterio che non consenta la pianificazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="46efe-131">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="46efe-132">Quindi, assegna gli utenti a questo criterio, Esegui:</span><span class="sxs-lookup"><span data-stu-id="46efe-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="46efe-133">**Si vuole disabilitare la programmazione di eventi dinamici per un numero elevato di utenti e consentire a un set di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="46efe-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="46efe-134">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="46efe-135">Quindi, assegna gli utenti al criterio globale, Esegui:</span><span class="sxs-lookup"><span data-stu-id="46efe-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="46efe-136">Creare un criterio per consentire la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="46efe-137">Abilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="46efe-138">Quindi, assegna gli utenti a questo criterio, Esegui:</span><span class="sxs-lookup"><span data-stu-id="46efe-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="46efe-139">Impostare gli utenti che possono partecipare agli eventi Live</span><span class="sxs-lookup"><span data-stu-id="46efe-139">Set who can join live events</span></span>
 
<span data-ttu-id="46efe-140">Impostare il criterio globale per consentire agli utenti di creare eventi che tutti, inclusi gli utenti anonimi, possono partecipare, eseguire:</span><span class="sxs-lookup"><span data-stu-id="46efe-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="46efe-141">Impostare l'opzione di registrazione per gli eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="46efe-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="46efe-142">Questa impostazione si applica solo agli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="46efe-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="46efe-143">Impostare il criterio globale per disabilitare la registrazione per gli eventi Live:</span><span class="sxs-lookup"><span data-stu-id="46efe-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="46efe-144">Impostare didascalie e sottotitoli dinamici in eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="46efe-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="46efe-145">Questa impostazione si applica solo agli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="46efe-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="46efe-146">Impostare il criterio globale per attivare le didascalie e i sottotitoli Live (trascrizione) per i partecipanti agli eventi:</span><span class="sxs-lookup"><span data-stu-id="46efe-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="46efe-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="46efe-147">Related topics</span></span>
- [<span data-ttu-id="46efe-148">Configurare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="46efe-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="46efe-149">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="46efe-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

