---
title: Esperienza di riunione di sola visualizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di riunione in sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf6787c3118ba36b71175f0ddb3360e980732a71
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867065"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="b2f53-103">Esperienza di riunione in sola visualizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="b2f53-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="b2f53-104">Le trasmissioni di sola visualizzazione saranno disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b2f53-104">View-only broadcasts will be available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="b2f53-105">Questa caratteristica verrà abilitata l'1 marzo 2021 come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2f53-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="b2f53-106">Questa funzionalità nei piani G3/G5 per enti pubblici di Microsoft 365 sarà disponibile in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b2f53-106">This feature in Microsoft 365 Government G3/G5 plans will be available at a later date.</span></span> <span data-ttu-id="b2f53-107">È necessario modificare il criterio predefinito dopo tale data se si vuole che la caratteristica sia attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2f53-107">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="b2f53-108">Usare PowerShell per abilitare il `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` criterio.</span><span class="sxs-lookup"><span data-stu-id="b2f53-108">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="b2f53-109">Se la riunione o il webinar raggiunge la capacità, Teams si adatta perfettamente a un'esperienza di trasmissione solo visualizzazione di 10.000 persone.</span><span class="sxs-lookup"><span data-stu-id="b2f53-109">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="b2f53-110">Inoltre, durante questo periodo di maggiore attività remota, sfruttare le trasmissioni di 20.000 persone ancora più grandi fino alla fine di quest'anno.</span><span class="sxs-lookup"><span data-stu-id="b2f53-110">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="b2f53-111">Microsoft Teams consente a un massimo di 10.000 partecipanti di partecipare a una riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2f53-111">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="b2f53-112">Dopo aver raggiunto la capacità della riunione principale, altri partecipanti si uniranno con un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-112">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="b2f53-113">I partecipanti che aderiscono per primi alla riunione, fino alla capacità della riunione, otterrà l'esperienza completa della riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2f53-113">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="b2f53-114">Possono condividere audio e video, vedere i video condivisi e partecipare alla chat delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b2f53-114">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="b2f53-115">I partecipanti che aderiscono dopo aver raggiunto la capacità della riunione principale avranno un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-115">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="b2f53-116">Abbiamo il supporto completo per Android e iOS per dispositivi mobili a cui un partecipante può partecipare.</span><span class="sxs-lookup"><span data-stu-id="b2f53-116">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="b2f53-117">Il limite corrente per il numero di persone che possono chattare e chiamare a una riunione è 300 in WW e 250 in GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="b2f53-117">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="b2f53-118">L'esperienza di sola visualizzazione è disabilitata per impostazione predefinita per qualsiasi organizzatore con SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b2f53-118">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="b2f53-119">Non sono necessarie altre configurazioni o configurazioni.</span><span class="sxs-lookup"><span data-stu-id="b2f53-119">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="b2f53-120">Disabilitare l'esperienza di sola visualizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="b2f53-120">Disable Teams view-only experience</span></span>

<span data-ttu-id="b2f53-121">Gli amministratori possono disabilitare l'esperienza di sola visualizzazione usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2f53-121">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="b2f53-122">In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2f53-122">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="b2f53-123">Impatto sugli utenti</span><span class="sxs-lookup"><span data-stu-id="b2f53-123">Impact to users</span></span>

<span data-ttu-id="b2f53-124">L'esperienza di un utente varia a seconda di diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="b2f53-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="b2f53-125">Una volta raggiunta la capacità della riunione principale, un partecipante non sarà in grado di partecipare alla riunione se una delle condizioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="b2f53-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="b2f53-126">Un amministratore ha disabilitato l'esperienza di sola visualizzazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2f53-126">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="b2f53-127">Il partecipante non ha l'autorizzazione per ignorare la sala d'attesa.</span><span class="sxs-lookup"><span data-stu-id="b2f53-127">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="b2f53-128">Una volta raggiunta la capacità della riunione principale, l'organizzatore della riunione e i relatori vedranno uno striscione che informa che la capacità della riunione è stata raggiunta e che i nuovi partecipanti si uniranno a un partecipante di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-128">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![il client Teams e il messaggio banner per organizzatori e relatori](media/chat-and-banner-message.png)

<span data-ttu-id="b2f53-130">Una volta raggiunta la capacità della riunione principale, i partecipanti alla riunione verranno informati nella schermata di pre-partecipazione che stanno partecipando in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-130">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la schermata di pre-partecipazione di Teams e il messaggio per i partecipanti che informano che si uniranno in modalità di sola visualizzazione](media/view-only-pre-join-screen.png)

<span data-ttu-id="b2f53-132">Se c'è spazio, un utente partecipa sempre alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="b2f53-132">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="b2f53-133">Se la riunione principale raggiunge la capacità e uno o più partecipanti lasciano la riunione principale, la riunione principale ha la capacità disponibile.</span><span class="sxs-lookup"><span data-stu-id="b2f53-133">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="b2f53-134">I partecipanti che aderiscono alla riunione (o a cui si partecipa di nuovo) aderiscono alla riunione principale finché non raggiunge di nuovo la capacità.</span><span class="sxs-lookup"><span data-stu-id="b2f53-134">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="b2f53-135">I partecipanti all'esperienza di sola visualizzazione non verranno alzati di livello automaticamente alla riunione principale e non potranno essere alzati di livello manualmente alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="b2f53-135">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="b2f53-136">Se i ruoli relatore/partecipante non sono stati impostati, gli spazi nella riunione principale vengono riempiti in base al primo arrivato e al primo servizio.</span><span class="sxs-lookup"><span data-stu-id="b2f53-136">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="b2f53-137">Una volta raggiunta la capacità della riunione, tutti gli altri utenti potranno partecipare con un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-137">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="b2f53-138">Impatto sui relatori della riunione</span><span class="sxs-lookup"><span data-stu-id="b2f53-138">Impact to meeting presenters</span></span>

<span data-ttu-id="b2f53-139">Le limitazioni per i relatori della riunione includono:</span><span class="sxs-lookup"><span data-stu-id="b2f53-139">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="b2f53-140">Non si hanno informazioni sul partecipante di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-140">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="b2f53-141">L'individuazione elettronica non è disponibile per i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-141">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="b2f53-142">Gli utenti non possono vedere i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-142">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="b2f53-143">Non è possibile rimuovere un partecipante di sola visualizzazione dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-143">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="b2f53-144">Il conteggio dei partecipanti rifletterà solo le persone nella riunione e non le persone nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-144">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="b2f53-145">Di conseguenza, i relatori non possono ottenere un conteggio esatto degli utenti nell'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-145">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="b2f53-146">Esperienza per i partecipanti di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b2f53-146">Experience for view-only attendees</span></span>

<span data-ttu-id="b2f53-147">L'esperienza di sola visualizzazione di Teams consente ai partecipanti di:</span><span class="sxs-lookup"><span data-stu-id="b2f53-147">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="b2f53-148">Ascoltare i partecipanti alla riunione principale di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2f53-148">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="b2f53-149">Vedere il feed video per l'altoparlante attivo (se l'altoparlante attivo sta condividendo il video).</span><span class="sxs-lookup"><span data-stu-id="b2f53-149">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="b2f53-150">Visualizzare il contenuto condiviso con la funzionalità condividi desktop.</span><span class="sxs-lookup"><span data-stu-id="b2f53-150">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="b2f53-151">Il partecipante di sola visualizzazione non sarà in grado di visualizzare le opzioni seguenti nelle riunioni:</span><span class="sxs-lookup"><span data-stu-id="b2f53-151">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="b2f53-152">Partecipare alla riunione se il partecipante non ha l'autorizzazione per ignorare la sala d'attesa in base alle opzioni o ai criteri di sala d'attesa impostati.</span><span class="sxs-lookup"><span data-stu-id="b2f53-152">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="b2f53-153">Partecipare alla sala di sola visualizzazione usando le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="b2f53-153">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="b2f53-154">Partecipare alla sala di sola visualizzazione usando il sistema Room di Microsoft Teams o i servizi CVI (Cloud Video Interop).</span><span class="sxs-lookup"><span data-stu-id="b2f53-154">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="b2f53-155">Condividere l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="b2f53-155">Share their audio or video.</span></span>
- <span data-ttu-id="b2f53-156">Visualizzare o partecipare alla chat della riunione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-156">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="b2f53-157">Vedere il feed video dei partecipanti alla riunione, a meno che il partecipante non sia il relatore attivo.</span><span class="sxs-lookup"><span data-stu-id="b2f53-157">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="b2f53-158">Vedere File di PowerPoint condivisi con la funzionalità di Condivisione nativa di PowerPoint o singole condivisioni di applicazioni (diverse dalla condivisione desktop).</span><span class="sxs-lookup"><span data-stu-id="b2f53-158">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="b2f53-159">Limitazioni delle funzionalità di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b2f53-159">View-only feature limitations</span></span>

- <span data-ttu-id="b2f53-160">I partecipanti di sola visualizzazione visualizzano sempre i sottotitoli in tempo reale, indipendentemente dall'impostazione dei sottotitoli in tempo reale per la riunione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-160">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="b2f53-161">Al momento sono supportate solo le didascalie in inglese.</span><span class="sxs-lookup"><span data-stu-id="b2f53-161">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="b2f53-162">I partecipanti di sola visualizzazione saranno supportati dalla tecnologia di streaming.</span><span class="sxs-lookup"><span data-stu-id="b2f53-162">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="b2f53-163">I partecipanti di sola visualizzazione non verranno inclusi nel report di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-163">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="b2f53-164">I partecipanti di sola visualizzazione avranno una singola esperienza video.</span><span class="sxs-lookup"><span data-stu-id="b2f53-164">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="b2f53-165">Possono vedere il relatore attivo o il contenuto condiviso, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="b2f53-165">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="b2f53-166">Attualmente non sono supportati i **layout** della **modalità Raccolta,** Raccolta grande o Insieme per i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-166">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="b2f53-167">I partecipanti di sola visualizzazione non hanno la stessa latenza di un partecipante normale.</span><span class="sxs-lookup"><span data-stu-id="b2f53-167">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="b2f53-168"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2f53-168"><sup>1</sup></span></span>

  <span data-ttu-id="b2f53-169"><sup>1</sup> I partecipanti di sola visualizzazione avranno un ritardo audio e video di 30 secondi nella riunione.</span><span class="sxs-lookup"><span data-stu-id="b2f53-169"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
