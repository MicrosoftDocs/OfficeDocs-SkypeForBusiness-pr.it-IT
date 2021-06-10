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
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598465"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="a9882-103">Usare la tecnologia NDI® in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a9882-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="a9882-104">La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per la connessione di dispositivi multimediali , ad esempio una fotocamera da studio e un mixer.</span><span class="sxs-lookup"><span data-stu-id="a9882-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="a9882-105">Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="a9882-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="a9882-106">La tecnologia NDI® è diventata una soluzione di settore standard per la produzione di contenuti live per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.</span><span class="sxs-lookup"><span data-stu-id="a9882-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="a9882-107">Skype aggiunto in precedenza ® funzionalità di Skype NDI alla fine del 2018.</span><span class="sxs-lookup"><span data-stu-id="a9882-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="a9882-108">Microsoft Teams questa funzionalità per migliorare l'esperienza della riunione.</span><span class="sxs-lookup"><span data-stu-id="a9882-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="a9882-109">La tecnologia NDI® è limitata a una rete locale e deve essere considerata solo una parte del flusso di lavoro di produzione, non una soluzione broadcast.</span><span class="sxs-lookup"><span data-stu-id="a9882-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="a9882-110">Attivare la tecnologia NDI®</span><span class="sxs-lookup"><span data-stu-id="a9882-110">Turn on NDI® technology</span></span>

<span data-ttu-id="a9882-111">La tecnologia NDI® richiede due passaggi per essere attivata per un utente.</span><span class="sxs-lookup"><span data-stu-id="a9882-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="a9882-112">L'amministratore del tenant deve abilitare la proprietà 'AllowNDIStreaming' in CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="a9882-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="a9882-113">Dopo aver popolato questa modifica, l'utente finale deve attivare la tecnologia NDI® per il proprio client specifico da  >  **Impostazioni Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="a9882-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="a9882-114">Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione è in fase di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="a9882-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="a9882-115">Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno rilasciare dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="a9882-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="a9882-116">L'immagine seguente mostra il messaggio banner visualizzato da un utente in una Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="a9882-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![striscione ® tecnologia NDI che viene visualizzato in una Teams riunione.](media/NDI-disclosure.png)

<span data-ttu-id="a9882-118">Il banner contiene un collegamento [all'informativa sulla privacy Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="a9882-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="a9882-119">NDI® viene attivato solo per sessione.</span><span class="sxs-lookup"><span data-stu-id="a9882-119">NDI® is activated per session only.</span></span> <span data-ttu-id="a9882-120">All'accesso successivo, l'utente deve attivarlo prima di usare NDI®.</span><span class="sxs-lookup"><span data-stu-id="a9882-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="a9882-121">Impostazioni locali e tipi di utente supportati</span><span class="sxs-lookup"><span data-stu-id="a9882-121">Supported locales and user types</span></span>

<span data-ttu-id="a9882-122">La ® NDI è supportata in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="a9882-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="a9882-123">Gli utenti seguenti sono inclusi in uno stream di tecnologia NDI®, ma non tutti gli utenti possono accedere al flusso della tecnologia NDI®:</span><span class="sxs-lookup"><span data-stu-id="a9882-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="a9882-124">In-tenant: supporto completo, fornito in base a ring/tenantId/userId (controllato dai criteri riunioni)</span><span class="sxs-lookup"><span data-stu-id="a9882-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="a9882-125">Federato: nessun accesso al flusso (anche se ha la tecnologia NDI® su)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a9882-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="a9882-126">Premium - nessun accesso al flusso</span><span class="sxs-lookup"><span data-stu-id="a9882-126">Premium - no stream access</span></span>
- <span data-ttu-id="a9882-127">Anonimo: nessun accesso al flusso</span><span class="sxs-lookup"><span data-stu-id="a9882-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="a9882-128">Guest: nessun accesso in streaming</span><span class="sxs-lookup"><span data-stu-id="a9882-128">Guest – no stream access</span></span>  

<span data-ttu-id="a9882-129"><sup>1</sup> I dispositivi hanno un'® NDI attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9882-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="a9882-130">Se un partecipante alla riunione usa un dispositivo con tecnologia NDI®, dovrà attivare la tecnologia NDI® NDI.</span><span class="sxs-lookup"><span data-stu-id="a9882-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
