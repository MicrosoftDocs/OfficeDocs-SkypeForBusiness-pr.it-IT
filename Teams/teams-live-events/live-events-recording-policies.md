---
title: Criteri di registrazione degli eventi live
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni sui criteri di registrazione degli eventi live.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9654c139433ffa764767e0a2140896eab52204b
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513849"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="33863-103">Criteri di registrazione degli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33863-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="33863-104">Sono disponibili diverse opzioni per registrare un evento Microsoft Teams live.</span><span class="sxs-lookup"><span data-stu-id="33863-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="33863-105">Le opzioni di registrazione vengono impostate usando i criteri di registrazione.</span><span class="sxs-lookup"><span data-stu-id="33863-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="33863-106">Questo articolo descrive le varie impostazioni.</span><span class="sxs-lookup"><span data-stu-id="33863-106">This article describes the various settings.</span></span>

<span data-ttu-id="33863-107">Le opzioni di registrazione vengono impostate usando il comando di PowerShell [Set-CsTeamsMeetingBroadcastPolicy.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="33863-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="33863-108">Comportamenti di pianificazione e opzioni</span><span class="sxs-lookup"><span data-stu-id="33863-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="33863-109">Durante la pianificazione di una registrazione di un evento live sono disponibili due opzioni per l'organizzatore:</span><span class="sxs-lookup"><span data-stu-id="33863-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="33863-110">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="33863-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="33863-111">File di registrazione: fornisce un file di registrazione che i produttori e i relatori possono scaricare al termine dell'evento.</span><span class="sxs-lookup"><span data-stu-id="33863-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="33863-112">Registrazione disponibile per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="33863-112">Recording available for attendees</span></span>

  - <span data-ttu-id="33863-113">DVR: un videoregistratore digitale (DVR) consente ai partecipanti di riavvolgere e mettere in pausa durante l'evento</span><span class="sxs-lookup"><span data-stu-id="33863-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="33863-114">VOD: un video su richiesta (VOD) consente ai partecipanti di guardare al termine dell'evento</span><span class="sxs-lookup"><span data-stu-id="33863-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="33863-115">Impostazione dei criteri di registrazione broadcast</span><span class="sxs-lookup"><span data-stu-id="33863-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="33863-116">Nell'ambito dei criteri di trasmissione, è possibile attivare o disattivare la registrazione per un evento live.</span><span class="sxs-lookup"><span data-stu-id="33863-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="33863-117">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="33863-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="33863-118">Registrazione disponibile per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="33863-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="33863-119">Registra sempre</span><span class="sxs-lookup"><span data-stu-id="33863-119">Always record</span></span>               | <span data-ttu-id="33863-120">Disabilitato e selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-120">Disabled and selected</span></span>                                | <span data-ttu-id="33863-121">Abilitato e selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-121">Enabled and selected</span></span>         |
| <span data-ttu-id="33863-122">L'organizzatore può registrare o meno</span><span class="sxs-lookup"><span data-stu-id="33863-122">Organizer can record or not</span></span> | <span data-ttu-id="33863-123">Abilitato e selezionato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="33863-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="33863-124">Abilitato e selezionato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="33863-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="33863-125">Non registrare mai</span><span class="sxs-lookup"><span data-stu-id="33863-125">Never record</span></span>               | <span data-ttu-id="33863-126">Disabilitato e non selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-126">Disabled and not selected</span></span>                            | <span data-ttu-id="33863-127">Disabilitato e non selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="33863-128">Archiviazione e persistenza</span><span class="sxs-lookup"><span data-stu-id="33863-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="33863-129">Opzione</span><span class="sxs-lookup"><span data-stu-id="33863-129">Option</span></span>                                       | <span data-ttu-id="33863-130">Stato</span><span class="sxs-lookup"><span data-stu-id="33863-130">State</span></span>   | <span data-ttu-id="33863-131">DVR</span><span class="sxs-lookup"><span data-stu-id="33863-131">DVR</span></span>                                                   | <span data-ttu-id="33863-132">VOD</span><span class="sxs-lookup"><span data-stu-id="33863-132">VOD</span></span>                                                     | <span data-ttu-id="33863-133">Registrazione</span><span class="sxs-lookup"><span data-stu-id="33863-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="33863-134">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="33863-134">Recording available to producers and presenters</span></span> | <span data-ttu-id="33863-135">Selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-135">Selected</span></span>     | <span data-ttu-id="33863-136">DVR è disponibile e la risorsa Servizi multimediali di Azure (AMS) viene archiviata per 180 giorni</span><span class="sxs-lookup"><span data-stu-id="33863-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="33863-137">Il partecipante può accedere e guardare l'evento</span><span class="sxs-lookup"><span data-stu-id="33863-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="33863-138">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-138">Not Selected</span></span> | <span data-ttu-id="33863-139">DVR è disponibile e la risorsa AMS viene archiviata per 180 giorni</span><span class="sxs-lookup"><span data-stu-id="33863-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="33863-140">Il partecipante non ottiene l'accesso all'evento al termine</span><span class="sxs-lookup"><span data-stu-id="33863-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="33863-141">Disabilitato (non selezionato)</span><span class="sxs-lookup"><span data-stu-id="33863-141">Disabled (Not selected)</span></span>|<span data-ttu-id="33863-142">DVR è disponibile e la risorsa AMS viene eliminata dopo l'evento</span><span class="sxs-lookup"><span data-stu-id="33863-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="33863-143">Il partecipante non ottiene l'accesso all'evento al termine</span><span class="sxs-lookup"><span data-stu-id="33863-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="33863-144">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="33863-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="33863-145">Selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="33863-146">Viene creato e archiviato un MP4</span><span class="sxs-lookup"><span data-stu-id="33863-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="33863-147">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="33863-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="33863-148">Non viene creato alcun file</span><span class="sxs-lookup"><span data-stu-id="33863-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="33863-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="33863-149">Related topics</span></span>

- [<span data-ttu-id="33863-150">Cosa sono gli eventi live di Teams?</span><span class="sxs-lookup"><span data-stu-id="33863-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="33863-151">Pianificare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="33863-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="33863-152">Configurare le impostazioni degli eventi live in Teams</span><span class="sxs-lookup"><span data-stu-id="33863-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="33863-153">Teams delle riunioni in cloud</span><span class="sxs-lookup"><span data-stu-id="33863-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
