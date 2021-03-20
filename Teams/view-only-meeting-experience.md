---
title: Esperienza di solo visualizzazione nelle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875056"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="b2679-103">Esperienza di sola visualizzazione nelle riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="b2679-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="b2679-104">Le trasmissioni nella modalità di sola visualizzazione sono disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b2679-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="b2679-105">Questa caratteristica sarà abilitata come predefinita l'1 marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="b2679-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="b2679-106">La distribuzione di questa funzionalità in Microsoft 365 Government Community Cloud (GCC) inizierà alla fine di marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="b2679-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="b2679-107">Government Community Cloud High (GCCH) e Department of Defense (DoD) saranno distribuiti in seguito.</span><span class="sxs-lookup"><span data-stu-id="b2679-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="b2679-108">È necessario modificare i criteri predefiniti dopo tale data se si attivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b2679-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="b2679-109">Usare PowerShell per abilitare i criteri `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="b2679-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="b2679-110">Se la riunione o il webinar supera la capacità, Teams si adatterà rapidamente per offrire un'esperienza di trasmissione in modalità solo visualizzazione per 10.000 persone. </span><span class="sxs-lookup"><span data-stu-id="b2679-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="b2679-111">Inoltre, durate questo periodo di maggiore telelavoro, si possono organizzare trasmissioni ancora più grandi, per 20.000 persone, fino alla fine di quest'anno.</span><span class="sxs-lookup"><span data-stu-id="b2679-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="b2679-112">Microsoft Teams consente fino a 10.000 partecipanti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b2679-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="b2679-113">Una volta raggiunta la capacità della riunione principale, gli altri partecipanti accederanno un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="b2679-114">Gli utenti che accedono alla riunione per primi vivranno l'esperienza di riunione completa, fino al raggiungimento del limite della riunione.</span><span class="sxs-lookup"><span data-stu-id="b2679-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="b2679-115">Possono condividere audio e video, visualizzare i video condivisi e partecipare alla chat delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b2679-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="b2679-116">Gli utenti che accedono dopo il superamento della capacità della riunione accederanno a un'esperienza di sola visualizzazione.  </span><span class="sxs-lookup"><span data-stu-id="b2679-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="b2679-117">La partecipazione alle riunioni supporta pienamente i dispositivi mobili Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="b2679-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="b2679-118">Il limite attuale del numero di persone che possono chattare e chiamare durante le riunioni è 300 per WW, 250 per GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="b2679-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="b2679-119">L'esperienza di sola visualizzazione è disabilitata per impostazione predefinita per tutti gli organizzatori dotati con SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b2679-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="b2679-120">Non sono necessarie altre operazioni di configurazione o impostazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="b2679-121">Disabilitare l'esperienza di solo visualizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="b2679-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="b2679-122">Gli amministratori possono disabilitare l'esperienza di sola visualizzazione con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2679-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="b2679-123">In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2679-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="b2679-124">Impatto sugli utenti</span><span class="sxs-lookup"><span data-stu-id="b2679-124">Impact to users</span></span>

<span data-ttu-id="b2679-125">L'esperienza d'uso varia a seconda di numerosi fattori.</span><span class="sxs-lookup"><span data-stu-id="b2679-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="b2679-126">Quando il limite di partecipati della riunione principale viene raggiunto, i partecipanti non possono accedere alla riunione se una qualsiasi delle seguenti condizioni è vera: </span><span class="sxs-lookup"><span data-stu-id="b2679-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="b2679-127">L'esperienza di sola visualizzazione di Teams è stata disabilitata da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="b2679-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="b2679-128">Il partecipante non è autorizzato a ignorare la sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="b2679-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="b2679-129">Quando viene raggiunto il limite di partecipanti della riunione principale, l'organizzatore della riunione e i presentatori vedranno un banner, che notifica che il limite è stato raggiunto e i nuovi partecipanti accederanno solo a un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![il cient di Teams e il banner di notifica per organizzatori e relatori](media/chat-and-banner-message.png)

<span data-ttu-id="b2679-131">Quando viene raggiunto il limite di partecipanti della riunione principale, i partecipanti vengono informati nella schermata preliminare di accesso che stanno accedendo a un'esperienza di sola visualizzazione. </span><span class="sxs-lookup"><span data-stu-id="b2679-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la schermata preliminare di accesso e il messaggio per i partecipanti che notifica  che si sta accedendo a un'esperienza di sola visualizzazione](media/view-only-pre-join-screen.png)

<span data-ttu-id="b2679-133">Se lo spazio è sufficiente, i nuovi utenti accedono sempre alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="b2679-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="b2679-134">Se il limite della riunione principale viene raggiunto e uno o più utenti abbandonano la riunione, la riunione principale ha una capacità sufficiente.</span><span class="sxs-lookup"><span data-stu-id="b2679-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="b2679-135">I partecipanti che accedono (o riaccedono) alla riunione entreranno nella sala principale fino al raggiungimento del limite di utenti.</span><span class="sxs-lookup"><span data-stu-id="b2679-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="b2679-136">I partecipanti che hanno avviato l'esperienza di sola visualizzazione non saranno promossi automaticamente alla riunione principale, e al momento non possono esservi promossi.</span><span class="sxs-lookup"><span data-stu-id="b2679-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="b2679-137">Se i ruoli relatore/partecipante non sono stati configurati, i posti disponibili nella sala vengono assegnati in base all'ordine di accesso.</span><span class="sxs-lookup"><span data-stu-id="b2679-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="b2679-138">Una volta raggiunto il limite della riunione, tutti gli altri utenti potranno accedere a un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="b2679-139">Impatto per i relatori della riunione</span><span class="sxs-lookup"><span data-stu-id="b2679-139">Impact to meeting presenters</span></span>

<span data-ttu-id="b2679-140">Le limitazioni dei relatori delle riunioni includono:</span><span class="sxs-lookup"><span data-stu-id="b2679-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="b2679-141">Non sono disponibili informazioi sui partecipanti in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="b2679-142">I processi e-discovery non sono supportati per i partecipanti in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="b2679-143">Gli utenti non possono vedere gli utenti in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="b2679-144">Non è possibile rimuovere i partecipanti in modalità di sola visualizzazione dalle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b2679-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="b2679-145">Il numero di partecipanti indicato riflette solo gli utenti della riunione, non le persone che si trovano nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="b2679-146">Pertanto, i presentatori non possono conoscere esattamente il numero degli utenti nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="b2679-147">Esperienza per gli in modalità nella sala di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b2679-147">Experience for view-only attendees</span></span>

<span data-ttu-id="b2679-148">L'esperienza di sola visualizzazione consente ai partecipanti di:</span><span class="sxs-lookup"><span data-stu-id="b2679-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="b2679-149">Ascoltare i partecipanti alla riunione principale di Teams.</span><span class="sxs-lookup"><span data-stu-id="b2679-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="b2679-150">Vedere il feed video del relatore attivo (se il relatore sta condividendo il video).</span><span class="sxs-lookup"><span data-stu-id="b2679-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="b2679-151">Visualizzare i contenuti condivisi con la funzionalità di condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="b2679-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="b2679-152">I partecipanti nella sala di sola visualizzazione non potranno usare le seguenti opzioni delle riunioni:</span><span class="sxs-lookup"><span data-stu-id="b2679-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="b2679-153">Partecipare alle riunioni se il partecipante non è autorizzato a ignorare la sala di attesa in base ai criteri o alle opzioni configurati della sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="b2679-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="b2679-154">Accedere alla sala di solo visualizzazione usando la funzionalità di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="b2679-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="b2679-155">Partecipare alla sala di sola visualizzazione usando il sistema della Sala riunioni di Teams o usando i servizi Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="b2679-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="b2679-156">Condividere l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="b2679-156">Share their audio or video.</span></span>
- <span data-ttu-id="b2679-157">Leggere o partecipare alla chat della riunione.</span><span class="sxs-lookup"><span data-stu-id="b2679-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="b2679-158">Visualizzare il video trasmesso dai partecipanti alla riunione, se non sono i relatori attivi.</span><span class="sxs-lookup"><span data-stu-id="b2679-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="b2679-159">Vedere i file di PowerPoint condivisi usando la funzionalità di condivisione nativa di PowerPoint o specifiche applicazioni di condivisione (diverse dalla condivisione desktop).</span><span class="sxs-lookup"><span data-stu-id="b2679-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="b2679-160">Limitazioni della funzionalità di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b2679-160">View-only feature limitations</span></span>

- <span data-ttu-id="b2679-161">I partecipanti nella sala di sola visualizzazione vedranno sempre i sottotitoli, indipendentemente dalle impostazioni dei sottotitoli della riunione.</span><span class="sxs-lookup"><span data-stu-id="b2679-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="b2679-162">Al momento sono supportati solo i sottotitoli in inglese.</span><span class="sxs-lookup"><span data-stu-id="b2679-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="b2679-163">I partecipanti nella sala di sola visualizzazione saranno supportati dalla tecnologia di streaming.</span><span class="sxs-lookup"><span data-stu-id="b2679-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="b2679-164">I partecipanti nella sala di sola visualizzazione non vengono inclusi nel report sui partecipanti.</span><span class="sxs-lookup"><span data-stu-id="b2679-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="b2679-165">I partecipanti nella sala di sola visualizzazione hanno un'esperienza video singola.</span><span class="sxs-lookup"><span data-stu-id="b2679-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="b2679-166">Possono accedere l'altoparlante attivo o i contenuti che vengono condivisi, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="b2679-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="b2679-167">Al momento non supportiamo i layout **Galleria**, **Galleria estesa**, o **Modalità Insieme** per gli utenti nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2679-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="b2679-168">Gli utenti nella sala di sola visualizzazione non avranno la stessa latenza degli utenti regolari.</span><span class="sxs-lookup"><span data-stu-id="b2679-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="b2679-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2679-169"><sup>1</sup></span></span>

  <span data-ttu-id="b2679-170"><sup>1</sup> I partecipanti nella sala di sola visualizzazione avrannno un ritardo audio e video di 30 secondi durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="b2679-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
