---
title: Usare NDI in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337015"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="bc1c8-103">Usare la tecnologia NDI® in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc1c8-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="bc1c8-104">La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per la connessione di dispositivi multimediali (ad esempio una fotocamera da studio e un mixer).</span><span class="sxs-lookup"><span data-stu-id="bc1c8-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="bc1c8-105">Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche su un computer locale.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="bc1c8-106">La tecnologia NDI® è diventata una soluzione di settore standard per la produzione di contenuti in tempo reale per i flussi e ha guadagnato una significativa consapevolezza e adozione nel mondo delle trasmissioni professionali.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="bc1c8-107">Skype ha aggiunto in ® funzionalità di out-out NDI a Skype negli ultimi mesi del 2018.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="bc1c8-108">Microsoft Teams usa questa funzionalità per migliorare l'esperienza delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="bc1c8-109">La tecnologia NDI ® è limitata a una rete locale e deve essere considerata solo parte del flusso di lavoro di produzione, non una soluzione di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="bc1c8-110">Attivare la tecnologia NDI®</span><span class="sxs-lookup"><span data-stu-id="bc1c8-110">Turn on NDI® technology</span></span>

<span data-ttu-id="bc1c8-111">La tecnologia NDI® richiede due passaggi per essere attivata per un utente.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="bc1c8-112">L'amministratore del tenant deve abilitare la proprietà "AllowNDIStreaming" in CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="bc1c8-113">Dopo aver popolato la modifica, l'utente finale deve attivare la tecnologia NDI® per il client specifico da  >  **Autorizzazioni impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="bc1c8-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="bc1c8-114">Quando un utente partecipa a una riunione, visualizza un messaggio che lo informa che la riunione è in corso di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="bc1c8-115">Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere presenti nella riunione.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="bc1c8-116">L'immagine seguente mostra il messaggio del banner che un utente vede in una riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![He NDI® technology banner that displays in a Teams meeting.](media/NDI-disclosure.png)

<span data-ttu-id="bc1c8-118">Il banner include un collegamento [all'informativa sulla privacy di Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="bc1c8-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="bc1c8-119">Impostazioni locali e tipi di utente supportati</span><span class="sxs-lookup"><span data-stu-id="bc1c8-119">Supported locales and user types</span></span>

<span data-ttu-id="bc1c8-120">La tecnologia NDI® è supportata in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="bc1c8-121">Gli utenti seguenti sono inclusi in un flusso ® tecnologia NDI®, ma non tutti gli utenti possono accedervi:</span><span class="sxs-lookup"><span data-stu-id="bc1c8-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="bc1c8-122">Supporto completo all'interno del tenant, recapitato in base a ring/tenantId/userId (controllato dai criteri di riunione)</span><span class="sxs-lookup"><span data-stu-id="bc1c8-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="bc1c8-123">Federato : nessun accesso al flusso (anche se la tecnologia NDI® è on)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bc1c8-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="bc1c8-124">Premium - nessun accesso in streaming</span><span class="sxs-lookup"><span data-stu-id="bc1c8-124">Premium - no stream access</span></span>
- <span data-ttu-id="bc1c8-125">Anonimo: nessun accesso al flusso</span><span class="sxs-lookup"><span data-stu-id="bc1c8-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="bc1c8-126">Guest : nessun accesso in flusso</span><span class="sxs-lookup"><span data-stu-id="bc1c8-126">Guest – no stream access</span></span>  

<span data-ttu-id="bc1c8-127"><sup>1</sup> I dispositivi dispongono di ® tecnologia NDI attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bc1c8-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="bc1c8-128">Se un partecipante alla riunione usa un dispositivo con la tecnologia NDI®, dovrà attivare la tecnologia NDI®></span><span class="sxs-lookup"><span data-stu-id="bc1c8-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
