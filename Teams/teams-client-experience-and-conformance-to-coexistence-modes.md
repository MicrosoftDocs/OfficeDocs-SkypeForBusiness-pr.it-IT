---
title: Esperienza e conformità del client teams alle modalità di coesistenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Esperienza e conformità del client teams alle modalità di coesistenza
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183925"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="884c2-103">Esperienza e conformità del client teams alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="884c2-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="884c2-104">Questa pagina descrive le modifiche importanti e recentemente rilasciate nel comportamento del client teams quando gli utenti si trovano in una delle modalità Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="884c2-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="884c2-105">Lo scopo delle modalità di coesistenza consiste nel creare un'esperienza semplice e prevedibile per gli utenti finali come transizione delle organizzazioni da Skype for business a teams.</span><span class="sxs-lookup"><span data-stu-id="884c2-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="884c2-106">Per un'organizzazione che si sposta in teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati TeamsOnly (o qualsiasi altra modalità) allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="884c2-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="884c2-107">Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare qualsiasi modalità Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) per garantire una comunicazione prevedibile tra gli utenti TeamsOnly e quelli che non sono ancora stati.</span><span class="sxs-lookup"><span data-stu-id="884c2-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="884c2-108">Quando un utente si trova in una delle modalità Skype for business, tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="884c2-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="884c2-109">Per evitare la confusione degli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client teams vengono disabilitate quando un utente si trova in una delle modalità Skype for business.</span><span class="sxs-lookup"><span data-stu-id="884c2-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="884c2-110">Analogamente, la pianificazione delle riunioni in teams viene disabilitata esplicitamente quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e abilitata esplicitamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="884c2-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="884c2-111">Come vengono modificate le funzionalità disponibili in teams client in base alla modalità</span><span class="sxs-lookup"><span data-stu-id="884c2-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="884c2-112">La funzionalità disponibile in teams dipende dalla modalità di coesistenza dell'utente, come impostato da TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="884c2-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="884c2-113">La tabella seguente riepiloga il comportamento:</span><span class="sxs-lookup"><span data-stu-id="884c2-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="884c2-114">Modalità effettiva dell'utente</span><span class="sxs-lookup"><span data-stu-id="884c2-114">User's effective mode</span></span>|<span data-ttu-id="884c2-115">Esperienza nel client Teams</span><span class="sxs-lookup"><span data-stu-id="884c2-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="884c2-116">Qualsiasi modalità Skype for business</span><span class="sxs-lookup"><span data-stu-id="884c2-116">Any Skype for Business mode</span></span>|<span data-ttu-id="884c2-117">La chiamata e la chat sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="884c2-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="884c2-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="884c2-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="884c2-119">La pianificazione delle riunioni è disponibile</span><span class="sxs-lookup"><span data-stu-id="884c2-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="884c2-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="884c2-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="884c2-121">La pianificazione delle riunioni non è disponibile</span><span class="sxs-lookup"><span data-stu-id="884c2-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="884c2-122">Gli screenshot seguenti illustrano la differenza tra la modalità TeamsOnly o Islands e tutte le altre modalità.</span><span class="sxs-lookup"><span data-stu-id="884c2-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="884c2-123">Tieni presente che le icone della chat e delle chiamate sono disponibili con la modalità TeamsOnly o Islands (schermata a sinistra), ma non con le altre modalità (schermata destra):</span><span class="sxs-lookup"><span data-stu-id="884c2-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Confronto affiancato delle modalità Teams](media/teams-mode-comparison.png)


 
<span data-ttu-id="884c2-125">**Nota:**
<sup>1</sup> per il momento, SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma lo scopo è la modalità SfBOnly per disabilitare anche la funzionalità canali e file in teams; Tuttavia, attualmente non sono presenti impostazioni che consentano la disabilitazione di questa funzionalità in teams.</span><span class="sxs-lookup"><span data-stu-id="884c2-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="884c2-126">Impatto della modalità in altre impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="884c2-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="884c2-127">Come descritto in precedenza, l'impatto della modalità di coesistenza di un utente è la funzionalità disponibile nel client Teams dell'utente.</span><span class="sxs-lookup"><span data-stu-id="884c2-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="884c2-128">Questo significa che il valore della modalità può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità.</span><span class="sxs-lookup"><span data-stu-id="884c2-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="884c2-129">In particolare, la modalità di coesistenza ha un impatto sull'onorabilità delle seguenti impostazioni dei criteri:</span><span class="sxs-lookup"><span data-stu-id="884c2-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="884c2-130">**Modalità (app)**</span><span class="sxs-lookup"><span data-stu-id="884c2-130">**Modality (App)**</span></span>|<span data-ttu-id="884c2-131">**Policy. setting**</span><span class="sxs-lookup"><span data-stu-id="884c2-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="884c2-132">Chat</span><span class="sxs-lookup"><span data-stu-id="884c2-132">Chat</span></span>|<span data-ttu-id="884c2-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="884c2-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="884c2-134">Chiamate</span><span class="sxs-lookup"><span data-stu-id="884c2-134">Calling</span></span>|<span data-ttu-id="884c2-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="884c2-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="884c2-136">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="884c2-136">Meeting scheduling</span></span>|<span data-ttu-id="884c2-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="884c2-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="884c2-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="884c2-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="884c2-139">Gli amministratori *non* devono impostare in modo esplicito queste impostazioni dei criteri quando si usa la modalità di coesistenza, ma è importante capire che queste impostazioni si comportano in modo efficace come segue per una modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="884c2-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="884c2-140">Modalità</span><span class="sxs-lookup"><span data-stu-id="884c2-140">Mode</span></span>|<span data-ttu-id="884c2-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="884c2-141">AllowUserChat</span></span>|<span data-ttu-id="884c2-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="884c2-142">AllowPrivateCalling</span></span>|<span data-ttu-id="884c2-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="884c2-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="884c2-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="884c2-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="884c2-145">TeamsOnly o isole</span><span class="sxs-lookup"><span data-stu-id="884c2-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="884c2-146">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-146">Enabled</span></span>|<span data-ttu-id="884c2-147">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-147">Enabled</span></span>|<span data-ttu-id="884c2-148">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-148">Enabled</span></span>|<span data-ttu-id="884c2-149">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-149">Enabled</span></span>|
|<span data-ttu-id="884c2-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="884c2-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="884c2-151">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-151">Disabled</span></span>|<span data-ttu-id="884c2-152">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-152">Disabled</span></span>|<span data-ttu-id="884c2-153">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-153">Enabled</span></span>|<span data-ttu-id="884c2-154">Abilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-154">Enabled</span></span>|
|<span data-ttu-id="884c2-155">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="884c2-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="884c2-156">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-156">Disabled</span></span>|<span data-ttu-id="884c2-157">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-157">Disabled</span></span>|<span data-ttu-id="884c2-158">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-158">Disabled</span></span>|<span data-ttu-id="884c2-159">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="884c2-159">Disabled</span></span>|
||||||

<span data-ttu-id="884c2-160">Quando si usa PowerShell, `Grant-CsTeamsUpgradePolicy` il cmdlet controlla la configurazione delle impostazioni corrispondenti in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni verrebbero sostituite da TeamsUpgradePolicy e, in caso affermativo, un il messaggio informativo viene fornito in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="884c2-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="884c2-161">Come indicato sopra, non è più necessario impostare queste altre impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="884c2-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="884c2-162">Di seguito è riportato un esempio di come appare l'avviso di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="884c2-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="884c2-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="884c2-163">Related topics</span></span>

[<span data-ttu-id="884c2-164">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="884c2-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




