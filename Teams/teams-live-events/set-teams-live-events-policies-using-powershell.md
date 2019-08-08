---
title: Usare PowerShell per impostare i criteri degli eventi dinamici in Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Esempi di come usare PowerShell per impostare i criteri in teams per controllare chi può contenere eventi dinamici nell'organizzazione e le caratteristiche disponibili negli eventi creati
appliesto:
- Microsoft Teams
ms.openlocfilehash: b92d52178f7b57b453eaaec010ded4731d166caf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243649"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="47a18-103">Usare PowerShell per impostare i criteri degli eventi dinamici in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47a18-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="47a18-104">Puoi usare i cmdlet di Windows PowerShell seguenti per impostare e assegnare le impostazioni dei criteri per gli eventi dinamici in teams:</span><span class="sxs-lookup"><span data-stu-id="47a18-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="47a18-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="47a18-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="47a18-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="47a18-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="47a18-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="47a18-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="47a18-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="47a18-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="47a18-109">Ecco alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="47a18-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="47a18-110">Consentire agli utenti di pianificare eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="47a18-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="47a18-111">Questi esempi sono per gli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="47a18-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="47a18-112">Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="47a18-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="47a18-113">Per altre informazioni, vedere [consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="47a18-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="47a18-114">**Consentire a un utente di pianificare eventi dinamici**</span><span class="sxs-lookup"><span data-stu-id="47a18-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="47a18-115">Se all'utente viene assegnato il criterio globale, eseguire e verificare che il parametro *AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="47a18-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="47a18-116">Assegnare quindi l'utente al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="47a18-117">Scenari utente</span><span class="sxs-lookup"><span data-stu-id="47a18-117">User scenarios</span></span>
<span data-ttu-id="47a18-118">**Si vuole che tutti gli utenti dell'organizzazione possano pianificare eventi dinamici**</span><span class="sxs-lookup"><span data-stu-id="47a18-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="47a18-119">Se agli utenti viene assegnato il criterio globale, eseguire e verificare che *AllowBroadcastScheduling* \* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="47a18-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="47a18-120">Se agli utenti viene assegnato un criterio diverso dal criterio globale, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="47a18-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="47a18-121">**Si vuole che la programmazione di eventi dinamici venga disabilitata nell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="47a18-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="47a18-122">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="47a18-123">Assegnare tutti gli utenti dell'organizzazione al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="47a18-124">**Si vuole che un numero elevato di utenti sia in grado di programmare eventi dinamici e impedire a un gruppo di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="47a18-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="47a18-125">Eseguire e verificare che *AllowBroadcastScheduling* sia impostato su *true*:</span><span class="sxs-lookup"><span data-stu-id="47a18-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="47a18-126">Assegnare quindi un utente o utenti al criterio globale, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="47a18-127">Creare un nuovo criterio che non consenta la pianificazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="47a18-128">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="47a18-129">Quindi, assegna gli utenti a questo criterio, Esegui:</span><span class="sxs-lookup"><span data-stu-id="47a18-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="47a18-130">**Si vuole disabilitare la programmazione di eventi dinamici per un numero elevato di utenti e consentire a un set di utenti di pianificarli**</span><span class="sxs-lookup"><span data-stu-id="47a18-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="47a18-131">Disabilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="47a18-132">Quindi, assegna gli utenti al criterio globale, Esegui:</span><span class="sxs-lookup"><span data-stu-id="47a18-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="47a18-133">Creare un criterio per consentire la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="47a18-134">Abilitare la programmazione di eventi dinamici, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="47a18-135">Quindi, assegna gli utenti a questo criterio, Esegui:</span><span class="sxs-lookup"><span data-stu-id="47a18-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="47a18-136">Impostare gli utenti che possono partecipare agli eventi Live</span><span class="sxs-lookup"><span data-stu-id="47a18-136">Set who can join live events</span></span>
 
<span data-ttu-id="47a18-137">Impostare il criterio globale per consentire agli utenti di creare eventi che tutti, inclusi gli utenti anonimi, possono partecipare, eseguire:</span><span class="sxs-lookup"><span data-stu-id="47a18-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="47a18-138">Impostare l'opzione di registrazione per gli eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="47a18-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="47a18-139">Questa impostazione si applica solo agli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="47a18-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="47a18-140">Impostare il criterio globale per disabilitare la registrazione per gli eventi Live:</span><span class="sxs-lookup"><span data-stu-id="47a18-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="47a18-141">Impostare didascalie e sottotitoli dinamici in eventi dinamici</span><span class="sxs-lookup"><span data-stu-id="47a18-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="47a18-142">Questa impostazione si applica solo agli eventi prodotti in teams.</span><span class="sxs-lookup"><span data-stu-id="47a18-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="47a18-143">Impostare il criterio globale per attivare le didascalie e i sottotitoli Live (trascrizione) per i partecipanti agli eventi:</span><span class="sxs-lookup"><span data-stu-id="47a18-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="47a18-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="47a18-144">Related topics</span></span>
- [<span data-ttu-id="47a18-145">Configurare gli eventi di teams Live</span><span class="sxs-lookup"><span data-stu-id="47a18-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


