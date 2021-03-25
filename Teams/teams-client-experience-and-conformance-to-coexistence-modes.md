---
title: Esperienza del client di Teams e conformità alle modalità di coesistenza
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Informazioni sull'esperienza client di Teams e sulla conformità alle modalità di coesistenza (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119255"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="17a77-103">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="17a77-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="17a77-104">Lo scopo delle modalità di coesistenza di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è fornire agli utenti finali un'esperienza semplice e prevedibile durante la transizione da Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="17a77-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="17a77-105">Per un'organizzazione che si sposta in Teams, la modalità Solo **Teams** è la destinazione finale per ogni utente, anche se non è necessario assegnare a tutti gli utenti solo **Teams** (o qualsiasi altra modalità) contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="17a77-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="17a77-106">Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare qualsiasi modalità di coesistenza di Skype for Business per garantire comunicazioni prevedibili tra gli utenti che sono solo **Teams** e quelli che non lo sono ancora.</span><span class="sxs-lookup"><span data-stu-id="17a77-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="17a77-107">Quando un utente è in una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono instradati al client Skype for Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="17a77-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="17a77-108">Per evitare confusione con l'utente finale e garantire la corretta funzionalità di routing, chiamate e chat nel client Teams viene disabilitata quando un utente si trova in una delle modalità Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17a77-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="17a77-109">Analogamente, la pianificazione delle riunioni in Teams viene disabilitata in modo esplicito quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata in modo esplicito quando un utente è in modalità SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="17a77-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="17a77-110">Poiché la presenza è un'indicazione della raggiungibilità tramite chat e chiamate, quando la chat e le chiamate sono disabilitate, anche l'auto-presenza in Teams (ovvero la visualizzazione della propria presenza nel client Teams nell'immagine dell'utente) è nascosta.</span><span class="sxs-lookup"><span data-stu-id="17a77-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="17a77-111">Modalità di modifica delle funzionalità disponibili nel client Teams in base alla modalità</span><span class="sxs-lookup"><span data-stu-id="17a77-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="17a77-112">La funzionalità disponibile in Teams dipende dalla modalità di coesistenza dell'utente, come impostato da TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="17a77-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="17a77-113">La tabella seguente riepiloga il comportamento:</span><span class="sxs-lookup"><span data-stu-id="17a77-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="17a77-114">Modalità effettiva dell'utente</span><span class="sxs-lookup"><span data-stu-id="17a77-114">User's effective mode</span></span>|<span data-ttu-id="17a77-115">Esperienza nel client di Teams</span><span class="sxs-lookup"><span data-stu-id="17a77-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="17a77-116">Qualsiasi modalità Skype for Business</span><span class="sxs-lookup"><span data-stu-id="17a77-116">Any Skype for Business mode</span></span>|<span data-ttu-id="17a77-117">Le chiamate, le chat e l'auto-presenza sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="17a77-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="17a77-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="17a77-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="17a77-119">La pianificazione delle riunioni è disponibile</span><span class="sxs-lookup"><span data-stu-id="17a77-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="17a77-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="17a77-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="17a77-121">La pianificazione delle riunioni non è disponibile</span><span class="sxs-lookup"><span data-stu-id="17a77-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="17a77-122">Gli screenshot seguenti illustrano la differenza tra **la modalità Solo Teams** o **Isole** e tutte le altre modalità.</span><span class="sxs-lookup"><span data-stu-id="17a77-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="17a77-123">Si noti che le icone delle chat e  delle chiamate sono disponibili per impostazione predefinita con la modalità Solo **Teams** o Isole (screenshot a sinistra), ma non con le altre modalità (screenshot a destra):</span><span class="sxs-lookup"><span data-stu-id="17a77-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Confronto affiancato delle modalità di Teams](media/teams-mode-comparison.png)

<span data-ttu-id="17a77-125">Inoltre, la presenza personale non è disponibile nelle altre modalità, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="17a77-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Screenshot della presenza personale in Meetings First](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="17a77-127">**Nota:** 
 <sup>1</sup> Al momento, SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma lo scopo è la modalità SfBOnly per disabilitare anche la funzionalità Canali e file in Teams.</span><span class="sxs-lookup"><span data-stu-id="17a77-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="17a77-128">Nel frattempo, i canali possono essere nascosti usando il criterio Autorizzazioni app.</span><span class="sxs-lookup"><span data-stu-id="17a77-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="17a77-129">Impatto della modalità su altre impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="17a77-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="17a77-130">Come descritto in precedenza, la modalità di coesistenza di un utente influisce sulle funzionalità disponibili nel client Teams dell'utente.</span><span class="sxs-lookup"><span data-stu-id="17a77-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="17a77-131">Questo significa che il valore della modalità può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità.</span><span class="sxs-lookup"><span data-stu-id="17a77-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="17a77-132">In particolare, la modalità di coesistenza influisce sull'applicazione delle impostazioni dei criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="17a77-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="17a77-133">**Modalità (app)**</span><span class="sxs-lookup"><span data-stu-id="17a77-133">**Modality (App)**</span></span>|<span data-ttu-id="17a77-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="17a77-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="17a77-135">Chat</span><span class="sxs-lookup"><span data-stu-id="17a77-135">Chat</span></span>|<span data-ttu-id="17a77-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="17a77-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="17a77-137">Chiamate</span><span class="sxs-lookup"><span data-stu-id="17a77-137">Calling</span></span>|<span data-ttu-id="17a77-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="17a77-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="17a77-139">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="17a77-139">Meeting scheduling</span></span>|<span data-ttu-id="17a77-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="17a77-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="17a77-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="17a77-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="17a77-142">Gli amministratori *non devono* impostare in modo esplicito queste impostazioni dei criteri quando usano la modalità di coesistenza, ma è importante comprendere che queste impostazioni si comportano in modo efficace nel modo seguente per una determinata modalità.</span><span class="sxs-lookup"><span data-stu-id="17a77-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="17a77-143">Modalità</span><span class="sxs-lookup"><span data-stu-id="17a77-143">Mode</span></span>|<span data-ttu-id="17a77-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="17a77-144">AllowUserChat</span></span>|<span data-ttu-id="17a77-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="17a77-145">AllowPrivateCalling</span></span>|<span data-ttu-id="17a77-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="17a77-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="17a77-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="17a77-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="17a77-148">TeamsOnly o Islands</span><span class="sxs-lookup"><span data-stu-id="17a77-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="17a77-149">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-149">Enabled</span></span>|<span data-ttu-id="17a77-150">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-150">Enabled</span></span>|<span data-ttu-id="17a77-151">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-151">Enabled</span></span>|<span data-ttu-id="17a77-152">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-152">Enabled</span></span>|
|<span data-ttu-id="17a77-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="17a77-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="17a77-154">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-154">Disabled</span></span>|<span data-ttu-id="17a77-155">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-155">Disabled</span></span>|<span data-ttu-id="17a77-156">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-156">Enabled</span></span>|<span data-ttu-id="17a77-157">Abilitata</span><span class="sxs-lookup"><span data-stu-id="17a77-157">Enabled</span></span>|
|<span data-ttu-id="17a77-158">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="17a77-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="17a77-159">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-159">Disabled</span></span>|<span data-ttu-id="17a77-160">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-160">Disabled</span></span>|<span data-ttu-id="17a77-161">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-161">Disabled</span></span>|<span data-ttu-id="17a77-162">Disattiva</span><span class="sxs-lookup"><span data-stu-id="17a77-162">Disabled</span></span>|
||||||

<span data-ttu-id="17a77-163">Quando si usa PowerShell, il cmdlet controlla la configurazione delle impostazioni corrispondenti `Grant-CsTeamsUpgradePolicy` in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni verrebbero sostituite da TeamsUpgradePolicy e, in tal caso, viene fornito un messaggio informativo in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17a77-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="17a77-164">Come indicato in precedenza, non è più necessario impostare queste altre impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="17a77-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="17a77-165">Di seguito è riportato un esempio dell'aspetto dell'avviso di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17a77-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="17a77-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="17a77-166">Related topics</span></span>

[<span data-ttu-id="17a77-167">Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="17a77-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)