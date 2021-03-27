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
ms.openlocfilehash: 9c808e4ae4e27e48c14c45711ef80ffd1c812125
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383970"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="ec170-103">Criteri di registrazione degli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec170-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="ec170-104">Sono disponibili diverse opzioni per registrare un evento live di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec170-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="ec170-105">Le opzioni di registrazione vengono impostate usando i criteri di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ec170-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="ec170-106">Questo articolo descrive le varie impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ec170-106">This article describes the various settings.</span></span>

<span data-ttu-id="ec170-107">Le opzioni di registrazione vengono impostate usando il comando di PowerShell [Set-CsTeamsMeetingBroadcastPolicy.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ec170-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="ec170-108">Comportamenti di pianificazione e opzioni</span><span class="sxs-lookup"><span data-stu-id="ec170-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="ec170-109">Durante la pianificazione di una registrazione di un evento live sono disponibili due opzioni per l'organizzatore:</span><span class="sxs-lookup"><span data-stu-id="ec170-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="ec170-110">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="ec170-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="ec170-111">File di registrazione: fornisce un file di registrazione che i produttori e i relatori possono scaricare al termine dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ec170-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="ec170-112">Registrazione disponibile per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="ec170-112">Recording available for attendees</span></span>

  - <span data-ttu-id="ec170-113">DVR: un videoregistratore digitale (DVR) consente ai partecipanti di riavvolgere e mettere in pausa durante l'evento</span><span class="sxs-lookup"><span data-stu-id="ec170-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="ec170-114">VOD: un video su richiesta (VOD) consente ai partecipanti di guardare al termine dell'evento</span><span class="sxs-lookup"><span data-stu-id="ec170-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="ec170-115">Impostazione dei criteri di registrazione broadcast</span><span class="sxs-lookup"><span data-stu-id="ec170-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="ec170-116">Nell'ambito dei criteri di trasmissione, è possibile attivare o disattivare la registrazione per un evento live.</span><span class="sxs-lookup"><span data-stu-id="ec170-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="ec170-117">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="ec170-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="ec170-118">Registrazione disponibile per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="ec170-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="ec170-119">Registra sempre</span><span class="sxs-lookup"><span data-stu-id="ec170-119">Always record</span></span>               | <span data-ttu-id="ec170-120">Disabilitato e selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-120">Disabled and selected</span></span>                                | <span data-ttu-id="ec170-121">Abilitato e selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-121">Enabled and selected</span></span>         |
| <span data-ttu-id="ec170-122">L'organizzatore può registrare o meno</span><span class="sxs-lookup"><span data-stu-id="ec170-122">Organizer can record or not</span></span> | <span data-ttu-id="ec170-123">Abilitato e selezionato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="ec170-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="ec170-124">Abilitato e selezionato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="ec170-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="ec170-125">Non registrare mai</span><span class="sxs-lookup"><span data-stu-id="ec170-125">Never record</span></span>               | <span data-ttu-id="ec170-126">Disabilitato e non selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-126">Disabled and not selected</span></span>                            | <span data-ttu-id="ec170-127">Abilitato e non selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-127">Enabled and not selected</span></span>      |

<span data-ttu-id="ec170-128">Quando il criterio è impostato su **Registra sempre**, nella pagina dei criteri sono disponibili le opzioni selezionate seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec170-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="ec170-129">![Impostazioni dei criteri per gli eventi live](../media/live-event-recording-policy.png "Screenshot dell'impostazione dei criteri per gli eventi live nell'interfaccia di amministrazione di Microsoft Teams.")</span><span class="sxs-lookup"><span data-stu-id="ec170-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="ec170-130">Comportamento di archiviazione e persistenza</span><span class="sxs-lookup"><span data-stu-id="ec170-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="ec170-131">Opzione</span><span class="sxs-lookup"><span data-stu-id="ec170-131">Option</span></span>                                       | <span data-ttu-id="ec170-132">Stato</span><span class="sxs-lookup"><span data-stu-id="ec170-132">State</span></span>   | <span data-ttu-id="ec170-133">DVR</span><span class="sxs-lookup"><span data-stu-id="ec170-133">DVR</span></span>                                                   | <span data-ttu-id="ec170-134">VOD</span><span class="sxs-lookup"><span data-stu-id="ec170-134">VOD</span></span>                                                     | <span data-ttu-id="ec170-135">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ec170-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="ec170-136">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="ec170-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="ec170-137">Selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-137">Selected</span></span>     | <span data-ttu-id="ec170-138">DVR è disponibile e l'asset di Azure Media Services (AMS) è archiviato per 180 giorni</span><span class="sxs-lookup"><span data-stu-id="ec170-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="ec170-139">Il partecipante può accedere e guardare l'evento</span><span class="sxs-lookup"><span data-stu-id="ec170-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="ec170-140">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-140">Not Selected</span></span> | <span data-ttu-id="ec170-141">DVR è disponibile e la risorsa AMS viene archiviata per 180 giorni</span><span class="sxs-lookup"><span data-stu-id="ec170-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="ec170-142">Il partecipante non ottiene l'accesso all'evento al termine</span><span class="sxs-lookup"><span data-stu-id="ec170-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="ec170-143">Disabilitato (non selezionato)</span><span class="sxs-lookup"><span data-stu-id="ec170-143">Disabled (Not selected)</span></span>|<span data-ttu-id="ec170-144">DVR è disponibile e la risorsa AMS viene eliminata dopo l'evento</span><span class="sxs-lookup"><span data-stu-id="ec170-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="ec170-145">Il partecipante non ottiene l'accesso all'evento al termine</span><span class="sxs-lookup"><span data-stu-id="ec170-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="ec170-146">Registrazione disponibile per produttori e relatori</span><span class="sxs-lookup"><span data-stu-id="ec170-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="ec170-147">Selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="ec170-148">Viene creato e archiviato un MP4</span><span class="sxs-lookup"><span data-stu-id="ec170-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="ec170-149">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="ec170-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="ec170-150">Non viene creato alcun file</span><span class="sxs-lookup"><span data-stu-id="ec170-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="ec170-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ec170-151">Related topics</span></span>

- [<span data-ttu-id="ec170-152">Cosa sono gli eventi live di Teams?</span><span class="sxs-lookup"><span data-stu-id="ec170-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ec170-153">Pianificare gli eventi live di Teams</span><span class="sxs-lookup"><span data-stu-id="ec170-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ec170-154">Configurare le impostazioni degli eventi live in Teams</span><span class="sxs-lookup"><span data-stu-id="ec170-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="ec170-155">Registrazione delle riunioni nel cloud di Teams</span><span class="sxs-lookup"><span data-stu-id="ec170-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)