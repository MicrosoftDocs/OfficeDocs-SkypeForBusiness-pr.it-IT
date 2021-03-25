---
title: Usare PowerShell per impostare i criteri per gli eventi live
author: cichur
ms.author: v-cichur
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
description: Esempi di come usare PowerShell per impostare criteri in Teams per controllare chi può tenere eventi in tempo reale nell'organizzazione e le funzionalità disponibili negli eventi.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119145"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="2687e-103">Usare PowerShell per impostare i criteri per gli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2687e-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="2687e-104">È possibile usare i cmdlet di Windows PowerShell per impostare e assegnare le impostazioni dei criteri per gli eventi live in Teams:</span><span class="sxs-lookup"><span data-stu-id="2687e-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="2687e-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2687e-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2687e-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2687e-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2687e-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2687e-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2687e-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2687e-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2687e-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="2687e-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="2687e-110">Ecco alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="2687e-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="2687e-111">Prima di eseguire questi cmdlet, è necessario essere connessi a PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2687e-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="2687e-112">Per altre informazioni, vedere [Gestire Skype for Business online con Microsoft 365 o PowerShell di Office 365.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="2687e-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="2687e-113">Consentire agli utenti di pianificare eventi live</span><span class="sxs-lookup"><span data-stu-id="2687e-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="2687e-114">Questi esempi sono relativi agli eventi prodotti in Teams.</span><span class="sxs-lookup"><span data-stu-id="2687e-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="2687e-115">Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="2687e-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="2687e-116">Per altre informazioni, vedere Consentire agli utenti di pianificare eventi prodotti [con un'app o un dispositivo esterno.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="2687e-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="2687e-117">**Consentire a un utente di pianificare eventi live**</span><span class="sxs-lookup"><span data-stu-id="2687e-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="2687e-118">Se all'utente sono assegnati i criteri globali, eseguire e verificare che il parametro *AllowBroadcastScheduling* sia impostato su *True:*</span><span class="sxs-lookup"><span data-stu-id="2687e-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="2687e-119">Quindi assegnare l'utente ai criteri globali, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="2687e-120">Scenari utente</span><span class="sxs-lookup"><span data-stu-id="2687e-120">User scenarios</span></span>
<span data-ttu-id="2687e-121">**Si vuole che tutti gli utenti dell'organizzazione siano in grado di pianificare eventi live**</span><span class="sxs-lookup"><span data-stu-id="2687e-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="2687e-122">Se agli utenti sono assegnati i criteri globali, eseguire e verificare che *AllowBroadcastScheduling* \*sia impostato su *True:*</span><span class="sxs-lookup"><span data-stu-id="2687e-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="2687e-123">Se agli utenti sono assegnati criteri diversi da quelli globali, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *True:*</span><span class="sxs-lookup"><span data-stu-id="2687e-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="2687e-124">**Si vuole che la pianificazione degli eventi live sia disabilitata nell'intera organizzazione**</span><span class="sxs-lookup"><span data-stu-id="2687e-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="2687e-125">Disabilitare la pianificazione degli eventi in tempo reale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="2687e-126">Assegnare tutti gli utenti dell'organizzazione ai criteri globali, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="2687e-127">**Si vuole che un numero elevato di utenti sia in grado di pianificare eventi live e impedire a un set di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="2687e-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="2687e-128">Eseguire e verificare che *AllowBroadcastScheduling* sia impostato su *True:*</span><span class="sxs-lookup"><span data-stu-id="2687e-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="2687e-129">Quindi assegnare uno o più utenti ai criteri globali, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="2687e-130">Creare un nuovo criterio che non consenta la pianificazione di eventi live, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="2687e-131">Disabilitare la pianificazione degli eventi in tempo reale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="2687e-132">Assegnare quindi gli utenti a questo criterio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="2687e-133">**Si vuole disabilitare la pianificazione degli eventi live per un numero elevato di utenti e consentire a un set di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="2687e-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="2687e-134">Disabilitare la pianificazione degli eventi in tempo reale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="2687e-135">Assegnare quindi questi utenti ai criteri globali, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="2687e-136">Creare un criterio per consentire la pianificazione di eventi in tempo reale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="2687e-137">Abilitare la pianificazione degli eventi in tempo reale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="2687e-138">Assegnare quindi gli utenti a questo criterio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="2687e-139">Impostare gli utenti che possono partecipare a eventi live</span><span class="sxs-lookup"><span data-stu-id="2687e-139">Set who can join live events</span></span>
 
<span data-ttu-id="2687e-140">Impostare i criteri globali per consentire agli utenti di creare eventi a cui tutti, inclusi gli utenti anonimi, possono partecipare, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2687e-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="2687e-141">Impostare l'opzione di registrazione per gli eventi live</span><span class="sxs-lookup"><span data-stu-id="2687e-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="2687e-142">Questa impostazione si applica solo agli eventi prodotti in Teams.</span><span class="sxs-lookup"><span data-stu-id="2687e-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="2687e-143">Impostare i criteri globali per disabilitare la registrazione per gli eventi live:</span><span class="sxs-lookup"><span data-stu-id="2687e-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="2687e-144">Impostare sottotitoli e sottotitoli in tempo reale negli eventi live</span><span class="sxs-lookup"><span data-stu-id="2687e-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="2687e-145">Questa impostazione si applica solo agli eventi prodotti in Teams.</span><span class="sxs-lookup"><span data-stu-id="2687e-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="2687e-146">Impostare i criteri globali per attivare i sottotitoli in tempo reale e i sottotitoli (trascrizione) per i partecipanti all'evento:</span><span class="sxs-lookup"><span data-stu-id="2687e-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="2687e-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2687e-147">Related topics</span></span>
- [<span data-ttu-id="2687e-148">Configurare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="2687e-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="2687e-149">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="2687e-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)