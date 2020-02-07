---
title: Esperienza del client di Teams e conformità alle modalità di coesistenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Esperienza del client di Teams e conformità alle modalità di coesistenza
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea9d83a582bfe463233cfafe9564a238e00e198
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837376"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="c31fc-103">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="c31fc-103">Teams client experience and conformance to coexistence modes</span></span>


<span data-ttu-id="c31fc-104">Lo scopo delle modalità di coesistenza di Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è quello di creare un'esperienza semplice e prevedibile per gli utenti finali come organizzazioni di transizione da Skype for business a teams.</span><span class="sxs-lookup"><span data-stu-id="c31fc-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="c31fc-105">Per un'organizzazione che si sposta in teams, la modalità **solo teams** è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati **solo a teams** (o qualsiasi altra modalità) allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="c31fc-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="c31fc-106">Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una qualsiasi delle modalità di coesistenza di Skype for business per garantire una comunicazione prevedibile tra gli utenti **solo team** e quelli che non sono ancora stati.</span><span class="sxs-lookup"><span data-stu-id="c31fc-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="c31fc-107">Quando un utente si trova in una delle modalità Skype for business, tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c31fc-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="c31fc-108">Per evitare la confusione degli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client teams vengono disabilitate quando un utente si trova in una delle modalità Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c31fc-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="c31fc-109">Analogamente, la pianificazione delle riunioni in teams viene disabilitata esplicitamente quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e abilitata esplicitamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="c31fc-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="c31fc-110">Poiché la presenza è un'indicazione della raggiungibilità tramite chat e chiamate, quando la chat e le chiamate sono disabilitate, l'autonomia in teams (ovvero la visualizzazione della propria presenza nel client teams nell'immagine dell'utente) è nascosta.</span><span class="sxs-lookup"><span data-stu-id="c31fc-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="c31fc-111">Come vengono modificate le funzionalità disponibili in teams client in base alla modalità</span><span class="sxs-lookup"><span data-stu-id="c31fc-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="c31fc-112">La funzionalità disponibile in teams dipende dalla modalità di coesistenza dell'utente, come impostato da TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="c31fc-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="c31fc-113">La tabella seguente riepiloga il comportamento:</span><span class="sxs-lookup"><span data-stu-id="c31fc-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="c31fc-114">Modalità effettiva dell'utente</span><span class="sxs-lookup"><span data-stu-id="c31fc-114">User's effective mode</span></span>|<span data-ttu-id="c31fc-115">Esperienza nel client Teams</span><span class="sxs-lookup"><span data-stu-id="c31fc-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="c31fc-116">Qualsiasi modalità Skype for business</span><span class="sxs-lookup"><span data-stu-id="c31fc-116">Any Skype for Business mode</span></span>|<span data-ttu-id="c31fc-117">La chiamata, la chat e la presenza personale sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="c31fc-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="c31fc-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="c31fc-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="c31fc-119">La pianificazione delle riunioni è disponibile</span><span class="sxs-lookup"><span data-stu-id="c31fc-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="c31fc-120">SfBWithTeamsCollab o SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c31fc-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="c31fc-121">La pianificazione delle riunioni non è disponibile</span><span class="sxs-lookup"><span data-stu-id="c31fc-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="c31fc-122">Gli screenshot seguenti illustrano la differenza tra **solo team** o modalità **isole** e tutte le altre modalità.</span><span class="sxs-lookup"><span data-stu-id="c31fc-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="c31fc-123">Tieni presente che le icone della chat e delle chiamate sono disponibili per impostazione predefinita con **solo team** o modalità **isole** (schermata a sinistra), ma non con le altre modalità (schermata destra):</span><span class="sxs-lookup"><span data-stu-id="c31fc-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Confronto affiancato delle modalità Teams](media/teams-mode-comparison.png)

<span data-ttu-id="c31fc-125">Inoltre, la presenza automatica non è disponibile nelle altre modalità, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c31fc-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Screenshot della presenza automatica nelle riunioni prima](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="c31fc-127">**Nota:**
<sup>1</sup> in questo momento, SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma lo scopo è la modalità SfBOnly per disabilitare anche la funzionalità canali e file in teams.</span><span class="sxs-lookup"><span data-stu-id="c31fc-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="c31fc-128">Nel frattempo i canali possono essere nascosti usando i criteri delle autorizzazioni dell'app.</span><span class="sxs-lookup"><span data-stu-id="c31fc-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="c31fc-129">Impatto della modalità in altre impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="c31fc-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="c31fc-130">Come descritto in precedenza, l'impatto della modalità di coesistenza di un utente è la funzionalità disponibile nel client Teams dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c31fc-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="c31fc-131">Questo significa che il valore della modalità può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità.</span><span class="sxs-lookup"><span data-stu-id="c31fc-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="c31fc-132">In particolare, la modalità di coesistenza ha un impatto sull'onorabilità delle seguenti impostazioni dei criteri:</span><span class="sxs-lookup"><span data-stu-id="c31fc-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="c31fc-133">**Modalità (app)**</span><span class="sxs-lookup"><span data-stu-id="c31fc-133">**Modality (App)**</span></span>|<span data-ttu-id="c31fc-134">**Policy. setting**</span><span class="sxs-lookup"><span data-stu-id="c31fc-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="c31fc-135">Chat</span><span class="sxs-lookup"><span data-stu-id="c31fc-135">Chat</span></span>|<span data-ttu-id="c31fc-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="c31fc-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="c31fc-137">Chiamate</span><span class="sxs-lookup"><span data-stu-id="c31fc-137">Calling</span></span>|<span data-ttu-id="c31fc-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c31fc-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="c31fc-139">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="c31fc-139">Meeting scheduling</span></span>|<span data-ttu-id="c31fc-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c31fc-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="c31fc-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c31fc-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="c31fc-142">Gli amministratori *non* devono impostare in modo esplicito queste impostazioni dei criteri quando si usa la modalità di coesistenza, ma è importante capire che queste impostazioni si comportano in modo efficace come segue per una modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="c31fc-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="c31fc-143">Modalità</span><span class="sxs-lookup"><span data-stu-id="c31fc-143">Mode</span></span>|<span data-ttu-id="c31fc-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="c31fc-144">AllowUserChat</span></span>|<span data-ttu-id="c31fc-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c31fc-145">AllowPrivateCalling</span></span>|<span data-ttu-id="c31fc-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c31fc-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="c31fc-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c31fc-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="c31fc-148">TeamsOnly o isole</span><span class="sxs-lookup"><span data-stu-id="c31fc-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="c31fc-149">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-149">Enabled</span></span>|<span data-ttu-id="c31fc-150">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-150">Enabled</span></span>|<span data-ttu-id="c31fc-151">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-151">Enabled</span></span>|<span data-ttu-id="c31fc-152">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-152">Enabled</span></span>|
|<span data-ttu-id="c31fc-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="c31fc-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="c31fc-154">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-154">Disabled</span></span>|<span data-ttu-id="c31fc-155">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-155">Disabled</span></span>|<span data-ttu-id="c31fc-156">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-156">Enabled</span></span>|<span data-ttu-id="c31fc-157">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-157">Enabled</span></span>|
|<span data-ttu-id="c31fc-158">SfBWithTeamsCollab o SfBOnly</span><span class="sxs-lookup"><span data-stu-id="c31fc-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="c31fc-159">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-159">Disabled</span></span>|<span data-ttu-id="c31fc-160">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-160">Disabled</span></span>|<span data-ttu-id="c31fc-161">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-161">Disabled</span></span>|<span data-ttu-id="c31fc-162">Disabilitata</span><span class="sxs-lookup"><span data-stu-id="c31fc-162">Disabled</span></span>|
||||||

<span data-ttu-id="c31fc-163">Quando si usa PowerShell, `Grant-CsTeamsUpgradePolicy` il cmdlet controlla la configurazione delle impostazioni corrispondenti in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni verrebbero sostituite da TeamsUpgradePolicy e, in caso affermativo, viene fornito un messaggio informativo in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c31fc-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="c31fc-164">Come indicato sopra, non è più necessario impostare queste altre impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c31fc-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="c31fc-165">Di seguito è riportato un esempio di come appare l'avviso di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c31fc-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="c31fc-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c31fc-166">Related topics</span></span>

[<span data-ttu-id="c31fc-167">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="c31fc-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




