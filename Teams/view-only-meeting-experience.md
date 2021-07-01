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
ms.openlocfilehash: 4f3546983c3d783c8eb08e0fc371cb9a9feb84f8
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219113"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="7e65b-103">Esperienza di sola visualizzazione nelle riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="7e65b-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="7e65b-104">Le trasmissioni nella modalità di sola visualizzazione sono disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="7e65b-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="7e65b-105">Questa caratteristica sarà abilitata come predefinita l'1 marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="7e65b-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="7e65b-106">La distribuzione di questa funzionalità in Microsoft 365 Government Community Cloud (GCC) inizierà alla fine di marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="7e65b-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="7e65b-107">Government Community Cloud High (GCCH) e Department of Defense (DoD) saranno distribuiti in seguito.</span><span class="sxs-lookup"><span data-stu-id="7e65b-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="7e65b-108">È necessario modificare i criteri predefiniti dopo tale data se si attivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7e65b-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="7e65b-109">Usare PowerShell per abilitare i criteri `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="7e65b-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="7e65b-110">Se la riunione raggiunge la capacità, Teams scalabilità uniforme per supportare un'esperienza di trasmissione solo visualizzazione di 10.000 persone.</span><span class="sxs-lookup"><span data-stu-id="7e65b-110">If your meeting hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="7e65b-111">Inoltre, durate questo periodo di maggiore telelavoro, si possono organizzare trasmissioni ancora più grandi, per 20.000 persone, fino alla fine di quest'anno.</span><span class="sxs-lookup"><span data-stu-id="7e65b-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="7e65b-112">Microsoft Teams consente fino a 10.000 partecipanti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7e65b-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="7e65b-113">Dopo aver raggiunto la capacità della riunione principale, ovvero quando 1000 utenti aderiscono a una riunione, altri partecipanti si uniranno con un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="7e65b-114">I partecipanti che aderiscono per primi alla riunione, fino alla capacità della riunione principale, otterrà l'esperienza Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="7e65b-115">Possono condividere audio e video, visualizzare i video condivisi e partecipare alla chat delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7e65b-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="7e65b-116">Gli utenti che accedono dopo il superamento della capacità della riunione accederanno a un'esperienza di sola visualizzazione.  </span><span class="sxs-lookup"><span data-stu-id="7e65b-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="7e65b-117">I partecipanti potranno partecipare all'esperienza di sola visualizzazione tramite desktop, Web e Teams mobile (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="7e65b-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="7e65b-118">La capacità limite corrente della "riunione principale", o in altre parole, il numero di utenti completamente interattivi è 1000 e include GCC.</span><span class="sxs-lookup"><span data-stu-id="7e65b-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="7e65b-119">Teams di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="7e65b-119">Teams view-only experience controls</span></span>

<span data-ttu-id="7e65b-120">È possibile abilitare l'esperienza di sola visualizzazione usando il cmdlet dal modulo [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) [di PowerShell SkypeForBusiness](/powershell/module/skype/?view=skype-ps) o almeno dalla versione 2.0.0 del modulo [MicrosoftTeams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="7e65b-120">You enable the view-only experience using the [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet from the [SkypeForBusiness PowerShell module](/powershell/module/skype/?view=skype-ps) or at least version 2.0.0 of the [MicrosoftTeams module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span>

<span data-ttu-id="7e65b-121">Per usare il modulo `MicrosoftTeams` consigliato:</span><span class="sxs-lookup"><span data-stu-id="7e65b-121">To use the recommended `MicrosoftTeams` module:</span></span>

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

<span data-ttu-id="7e65b-122">Per abilitare l'esperienza di sola visualizzazione, è possibile usare il frammento di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="7e65b-122">To enable the view-only experience, you can use the following PowerShell snippet:</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="7e65b-123">Per disabilitare l'esperienza di sola visualizzazione, è anche possibile usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e65b-123">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="7e65b-124">In futuro sarà possibile abilitare o disabilitare l'esperienza di sola visualizzazione nell'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-124">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="7e65b-125">Impatto sugli utenti</span><span class="sxs-lookup"><span data-stu-id="7e65b-125">Impact to users</span></span>

<span data-ttu-id="7e65b-126">L'esperienza d'uso varia a seconda di numerosi fattori.</span><span class="sxs-lookup"><span data-stu-id="7e65b-126">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="7e65b-127">Quando il limite di partecipati della riunione principale viene raggiunto, i partecipanti non possono accedere alla riunione se una qualsiasi delle seguenti condizioni è vera: </span><span class="sxs-lookup"><span data-stu-id="7e65b-127">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="7e65b-128">Un amministratore ha disabilitato l'Teams di sola visualizzazione per l'organizzatore o per l'intero tenant.</span><span class="sxs-lookup"><span data-stu-id="7e65b-128">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="7e65b-129">Il partecipante di sola visualizzazione non può ignorare la sala d'attesa.</span><span class="sxs-lookup"><span data-stu-id="7e65b-129">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="7e65b-130">Ad esempio, se un organizzatore di una  riunione sceglie di fare in modo che solo le persone dell'organizzazione esemplino la sala d'attesa e un partecipante esterno all'organizzazione tenti di partecipare come partecipante di sola visualizzazione, non potrà partecipare.</span><span class="sxs-lookup"><span data-stu-id="7e65b-130">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="7e65b-131">Una volta raggiunta la capacità della riunione principale, l'organizzatore della riunione e i relatori vedranno uno striscione che informa che i nuovi partecipanti si uniranno come partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-131">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![il cient di Teams e il banner di notifica per organizzatori e relatori](media/chat-and-banner-message.png)

<span data-ttu-id="7e65b-133">Quando viene raggiunto il limite di partecipanti della riunione principale, i partecipanti vengono informati nella schermata preliminare di accesso che stanno accedendo a un'esperienza di sola visualizzazione. </span><span class="sxs-lookup"><span data-stu-id="7e65b-133">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![la schermata preliminare di accesso e il messaggio per i partecipanti che notifica  che si sta accedendo a un'esperienza di sola visualizzazione](media/view-only-pre-join-screen.png)

<span data-ttu-id="7e65b-135">Se lo spazio è sufficiente, i nuovi utenti accedono sempre alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="7e65b-135">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="7e65b-136">Se il limite della riunione principale viene raggiunto e uno o più utenti abbandonano la riunione, la riunione principale ha una capacità sufficiente.</span><span class="sxs-lookup"><span data-stu-id="7e65b-136">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="7e65b-137">I partecipanti che accedono (o riaccedono) alla riunione entreranno nella sala principale fino al raggiungimento del limite di utenti.</span><span class="sxs-lookup"><span data-stu-id="7e65b-137">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="7e65b-138">I partecipanti all'esperienza di sola visualizzazione non verranno alzati di livello automaticamente alla riunione principale e non potranno essere alzati di livello manualmente alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="7e65b-138">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="7e65b-139">Se sono stati impostati ruoli di relatore e partecipante e un relatore prova a partecipare a una riunione dopo che la riunione principale ha raggiunto la capacità, partecipa come partecipante di sola visualizzazione e ha le stesse limitazioni degli altri partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-139">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="7e65b-140">Supporto per garantire che tutti i relatori che aderiscono alla riunione principale siano in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7e65b-140">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="7e65b-141">L'organizzatore avrà sempre uno spazio garantito nella riunione principale.</span><span class="sxs-lookup"><span data-stu-id="7e65b-141">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="7e65b-142">Impatto sui relatori e gli organizzatori della riunione</span><span class="sxs-lookup"><span data-stu-id="7e65b-142">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="7e65b-143">Le limitazioni per relatori e organizzatori della riunione includono:</span><span class="sxs-lookup"><span data-stu-id="7e65b-143">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="7e65b-144">Non sono disponibili informazioi sui partecipanti in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-144">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="7e65b-145">I processi e-discovery non sono supportati per i partecipanti in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-145">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="7e65b-146">Gli utenti della riunione principale non possono vedere i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-146">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="7e65b-147">Non è possibile rimuovere i partecipanti in modalità di sola visualizzazione dalle riunioni.</span><span class="sxs-lookup"><span data-stu-id="7e65b-147">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="7e65b-148">Il numero di partecipanti rifletterà solo le persone nella riunione principale e non le persone nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-148">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="7e65b-149">Pertanto, i presentatori non possono conoscere esattamente il numero degli utenti nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-149">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="7e65b-150">Esperienza per gli in modalità nella sala di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="7e65b-150">Experience for view-only attendees</span></span>

<span data-ttu-id="7e65b-151">L'esperienza di sola visualizzazione consente ai partecipanti di:</span><span class="sxs-lookup"><span data-stu-id="7e65b-151">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="7e65b-152">Ascoltare i partecipanti alla riunione principale di Teams.</span><span class="sxs-lookup"><span data-stu-id="7e65b-152">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="7e65b-153">Vedere il feed video del relatore attivo (se il relatore sta condividendo il video).</span><span class="sxs-lookup"><span data-stu-id="7e65b-153">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="7e65b-154">Visualizzare il contenuto condiviso usando la funzionalità condividi desktop o schermo.</span><span class="sxs-lookup"><span data-stu-id="7e65b-154">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="7e65b-155">I partecipanti nella sala di sola visualizzazione non potranno usare le seguenti opzioni delle riunioni:</span><span class="sxs-lookup"><span data-stu-id="7e65b-155">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="7e65b-156">Partecipare alle riunioni se il partecipante non è autorizzato a ignorare la sala di attesa in base ai criteri o alle opzioni configurati della sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="7e65b-156">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="7e65b-157">Accedere alla sala di solo visualizzazione usando la funzionalità di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7e65b-157">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="7e65b-158">Partecipare alla sala di sola visualizzazione usando Microsoft Teams Rooms o i servizi CVI (Cloud Video Interop).</span><span class="sxs-lookup"><span data-stu-id="7e65b-158">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="7e65b-159">Condividere l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="7e65b-159">Share their audio or video.</span></span>
- <span data-ttu-id="7e65b-160">Leggere o partecipare alla chat della riunione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-160">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="7e65b-161">Visualizzare il video trasmesso dai partecipanti alla riunione, se non sono i relatori attivi.</span><span class="sxs-lookup"><span data-stu-id="7e65b-161">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="7e65b-162">Vedere PowerPoint file condivisi usando la funzionalità live PowerPoint o le singole condivisioni di applicazioni ,ad esempio desktop o condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="7e65b-162">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="7e65b-163">Alzare la mano durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-163">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="7e65b-164">Inviare o visualizzare le reazioni.</span><span class="sxs-lookup"><span data-stu-id="7e65b-164">Send or see reactions.</span></span>
- <span data-ttu-id="7e65b-165">Interagisci con qualsiasi app 3P che si integra nella riunione Teams, inclusi i sondaggi.</span><span class="sxs-lookup"><span data-stu-id="7e65b-165">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="7e65b-166">Limitazioni della funzionalità di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="7e65b-166">View-only feature limitations</span></span>

- <span data-ttu-id="7e65b-167">I partecipanti di sola visualizzazione potranno vedere solo i sottotitoli in tempo reale sul desktop e sul Web.</span><span class="sxs-lookup"><span data-stu-id="7e65b-167">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="7e65b-168">Al momento sono supportati solo i sottotitoli in inglese.</span><span class="sxs-lookup"><span data-stu-id="7e65b-168">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="7e65b-169">I partecipanti nella sala di sola visualizzazione saranno supportati dalla tecnologia di streaming.</span><span class="sxs-lookup"><span data-stu-id="7e65b-169">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="7e65b-170">I partecipanti nella sala di sola visualizzazione non vengono inclusi nel report sui partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7e65b-170">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="7e65b-171">I partecipanti nella sala di sola visualizzazione hanno un'esperienza video singola.</span><span class="sxs-lookup"><span data-stu-id="7e65b-171">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="7e65b-172">Possono accedere l'altoparlante attivo o i contenuti che vengono condivisi, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="7e65b-172">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="7e65b-173">Al momento non supportiamo i layout **Galleria**, **Galleria estesa**, o **Modalità Insieme** per gli utenti nella sala di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-173">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="7e65b-174">Gli utenti nella sala di sola visualizzazione non avranno la stessa latenza degli utenti regolari.</span><span class="sxs-lookup"><span data-stu-id="7e65b-174">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="7e65b-175"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7e65b-175"><sup>1</sup></span></span>

  <span data-ttu-id="7e65b-176"><sup>1</sup> I partecipanti nella sala di sola visualizzazione avrannno un ritardo audio e video di 30 secondi durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="7e65b-176"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
