---
title: Esperienza di riunione in sola visualizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di riunione di sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237456"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="54c7b-103">Esperienza di riunione in sola visualizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="54c7b-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="54c7b-104">L'esperienza di sola visualizzazione per le riunioni sarà disponibile all'inizio di marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="54c7b-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="54c7b-105">L'esperienza di sola visualizzazione è stata temporaneamente aumentata per 20.000 partecipanti, ma il supporto verrà ripristinato a 10.000 partecipanti il 30 giugno 2021.</span><span class="sxs-lookup"><span data-stu-id="54c7b-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="54c7b-106">Microsoft Teams consente a un massimo di 10.000 partecipanti di partecipare a una riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="54c7b-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="54c7b-107">Una volta raggiunta la capacità della riunione principale, altri partecipanti potranno partecipare con un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="54c7b-108">I partecipanti che aderiscono per primi alla riunione, fino alla capacità della riunione, otterrà l'esperienza completa della riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="54c7b-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="54c7b-109">Possono condividere audio e video, vedere i video condivisi e partecipare alla chat della riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="54c7b-110">I partecipanti che aderiscono dopo aver raggiunto la capacità principale della riunione avranno un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="54c7b-111">Per un partecipante è disponibile il supporto completo per dispositivi mobili Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="54c7b-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="54c7b-112">Il limite corrente per il numero di persone che possono chattare e chiamare per una riunione è 300 in WW e 250 in GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="54c7b-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="54c7b-113">L'esperienza di sola visualizzazione è abilitata per impostazione predefinita per tutti gli organizzatori che hanno SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="54c7b-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="54c7b-114">Non sono necessarie altre configurazioni o configurazioni.</span><span class="sxs-lookup"><span data-stu-id="54c7b-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="54c7b-115">Disabilitare l'esperienza di sola visualizzazione di Teams</span><span class="sxs-lookup"><span data-stu-id="54c7b-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="54c7b-116">Gli amministratori possono disabilitare l'esperienza di sola visualizzazione con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54c7b-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="54c7b-117">In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="54c7b-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="54c7b-118">Impatto sugli utenti</span><span class="sxs-lookup"><span data-stu-id="54c7b-118">Impact to users</span></span>

<span data-ttu-id="54c7b-119">L'esperienza di un utente varia in base a diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="54c7b-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="54c7b-120">Una volta raggiunta la capacità della riunione principale, un partecipante non sarà in grado di partecipare se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54c7b-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="54c7b-121">Un amministratore ha disabilitato l'esperienza di sola visualizzazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="54c7b-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="54c7b-122">Il partecipante non è autorizzato a ignorare la sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="54c7b-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="54c7b-123">Una volta raggiunta la capacità della riunione principale, l'organizzatore e i relatori della riunione vedranno un banner che li informa che è stata raggiunta la capacità della riunione e che i nuovi partecipanti potranno partecipare a un partecipante di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![The Teams client and banner messsage for organizers and presenters](media/chat-and-banner-message.png)

<span data-ttu-id="54c7b-125">Quando viene raggiunta la capacità della riunione principale, i partecipanti alla riunione vengono informati nella schermata di pre-accesso che stanno partecipando in modalità di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![schermata di pre-partecipazione di Teams e messaggio per i partecipanti che li informa che potranno partecipare in modalità di sola visualizzazione](media/view-only-pre-join-screen.png)

<span data-ttu-id="54c7b-127">Se c'è spazio, un utente partecipa sempre alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="54c7b-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="54c7b-128">Se la riunione principale raggiunge la capacità e uno o più partecipanti lasciano la riunione principale, la riunione principale ha la capacità disponibile.</span><span class="sxs-lookup"><span data-stu-id="54c7b-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="54c7b-129">I partecipanti che a partecipare (o a rientrare) alla riunione principale non raggiungeranno nuovamente la capacità.</span><span class="sxs-lookup"><span data-stu-id="54c7b-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="54c7b-130">I partecipanti che hanno esperienza di sola visualizzazione non verranno automaticamente alzati di livello alla riunione principale e al momento non possono essere alzati manualmente alla riunione principale.</span><span class="sxs-lookup"><span data-stu-id="54c7b-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="54c7b-131">Se i ruoli di relatore/partecipante non sono stati impostati, gli spazi nella riunione principale vengono compilati in base al primo utente.</span><span class="sxs-lookup"><span data-stu-id="54c7b-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="54c7b-132">Una volta raggiunta la capacità della riunione, tutti gli altri utenti potranno partecipare con un'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="54c7b-133">Impatto sui relatori della riunione</span><span class="sxs-lookup"><span data-stu-id="54c7b-133">Impact to meeting presenters</span></span>

<span data-ttu-id="54c7b-134">Nella riunione normale verrà prenotato uno spazio per gli utenti esplicitamente indicati come relatori nelle opzioni della riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="54c7b-135">Se un relatore lascia la riunione e in seguito rientra nella riunione, il relatore passerà alla riunione come relatore.</span><span class="sxs-lookup"><span data-stu-id="54c7b-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="54c7b-136">Le limitazioni per i relatori della riunione includono:</span><span class="sxs-lookup"><span data-stu-id="54c7b-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="54c7b-137">Non si hanno informazioni sul partecipante di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="54c7b-138">L'e-discovery non è disponibile per i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="54c7b-139">Gli utenti non possono vedere i partecipanti di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="54c7b-140">Non è possibile rimuovere un partecipante di sola visualizzazione dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="54c7b-141">Il numero di partecipanti rifletterà solo le persone presenti alla riunione e non le persone nella sala di riversamento.</span><span class="sxs-lookup"><span data-stu-id="54c7b-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="54c7b-142">Di conseguenza, i relatori non possono ottenere il conteggio esatto degli utenti nell'esperienza di sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="54c7b-143">Esperienza per i partecipanti di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="54c7b-143">Experience for view-only attendees</span></span>

<span data-ttu-id="54c7b-144">L'esperienza di sola visualizzazione di Teams consente ai partecipanti di:</span><span class="sxs-lookup"><span data-stu-id="54c7b-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="54c7b-145">Ascoltare i partecipanti alla riunione di Teams principale.</span><span class="sxs-lookup"><span data-stu-id="54c7b-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="54c7b-146">Vedere il feed video dell'altoparlante attivo (se il relatore attivo sta condividendo il video).</span><span class="sxs-lookup"><span data-stu-id="54c7b-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="54c7b-147">Visualizzare il contenuto condiviso usando la funzionalità Condividi desktop.</span><span class="sxs-lookup"><span data-stu-id="54c7b-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="54c7b-148">Il partecipante di sola visualizzazione non sarà in grado di visualizzare le opzioni seguenti nelle riunioni:</span><span class="sxs-lookup"><span data-stu-id="54c7b-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="54c7b-149">Partecipare alla riunione se il partecipante non è autorizzato a evitare la sala di attesa in base alle opzioni o ai criteri di attesa impostati.</span><span class="sxs-lookup"><span data-stu-id="54c7b-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="54c7b-150">Partecipare alla sala di riversamento tramite audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="54c7b-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="54c7b-151">Entra nella sala riversamento tramite il sistema Room system di Microsoft Teams o tramite i servizi Cloud Video Interoperabilità (CVI).</span><span class="sxs-lookup"><span data-stu-id="54c7b-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="54c7b-152">Entra nella sala riversamento tramite l'app Teams per dispositivi mobili Android.</span><span class="sxs-lookup"><span data-stu-id="54c7b-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="54c7b-153">Condividere l'audio o il video.</span><span class="sxs-lookup"><span data-stu-id="54c7b-153">Share their audio or video.</span></span>
- <span data-ttu-id="54c7b-154">Visualizzare o partecipare alla chat della riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="54c7b-155">Visualizzare il feed video dei partecipanti alla riunione a meno che il partecipante non sia il relatore attivo.</span><span class="sxs-lookup"><span data-stu-id="54c7b-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="54c7b-156">Visualizzare i file di PowerPoint condivisi usando la funzionalità nativa di PowerPoint condivisa o le singole condivisioni applicazioni (diversa dalla condivisione desktop).</span><span class="sxs-lookup"><span data-stu-id="54c7b-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="54c7b-157">Limitazioni delle caratteristiche di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="54c7b-157">View-only feature limitations</span></span>

- <span data-ttu-id="54c7b-158">I partecipanti in sola visualizzazione visualizzano sempre i sottotitoli in tempo reale, indipendentemente dall'impostazione dei sottotitoli in tempo reale per la riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="54c7b-159">Al momento sono supportati solo i sottotitoli in inglese.</span><span class="sxs-lookup"><span data-stu-id="54c7b-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="54c7b-160">I partecipanti in sola visualizzazione saranno supportati dalla tecnologia di streaming.</span><span class="sxs-lookup"><span data-stu-id="54c7b-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="54c7b-161">I partecipanti di sola visualizzazione non verranno inclusi nel report sulle presenze.</span><span class="sxs-lookup"><span data-stu-id="54c7b-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="54c7b-162">I partecipanti in sola visualizzazione avranno un'unica esperienza video.</span><span class="sxs-lookup"><span data-stu-id="54c7b-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="54c7b-163">Possono vedere il relatore attivo o il contenuto condiviso, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="54c7b-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="54c7b-164">Al momento, i **layout** della **raccolta,** della raccolta **grande** o della modalità Insieme non sono supportati per i partecipanti in sola visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="54c7b-165">I partecipanti di sola visualizzazione non hanno la stessa latenza di un normale partecipante.</span><span class="sxs-lookup"><span data-stu-id="54c7b-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="54c7b-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="54c7b-166"><sup>1</sup></span></span>

  <span data-ttu-id="54c7b-167"><sup>1</sup> I partecipanti in sola visualizzazione avranno un ritardo audio e video di 30 secondi nella riunione.</span><span class="sxs-lookup"><span data-stu-id="54c7b-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="54c7b-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="54c7b-168">Related topics</span></span>

- [<span data-ttu-id="54c7b-169">Componente aggiuntivo per le comunicazioni avanzate per Teams</span><span class="sxs-lookup"><span data-stu-id="54c7b-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="54c7b-170">Limiti e specifiche per Teams</span><span class="sxs-lookup"><span data-stu-id="54c7b-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
