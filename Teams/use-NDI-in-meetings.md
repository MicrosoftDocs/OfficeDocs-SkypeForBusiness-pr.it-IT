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
description: Informazioni su come usare NDI in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308169"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="756b2-103">Usare la tecnologia® NDI in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="756b2-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="756b2-104">La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per connettere dispositivi multimediali, ad esempio una videocamera e un mixer di studio.</span><span class="sxs-lookup"><span data-stu-id="756b2-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="756b2-105">Invece di usare le connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="756b2-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="756b2-106">La tecnologia NDI® è diventata una soluzione industriale standard per la produzione di contenuti dinamici per flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.</span><span class="sxs-lookup"><span data-stu-id="756b2-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="756b2-107">Skype ha aggiunto in precedenza la funzionalità®-out di NDI a Skype alla fine di 2018.</span><span class="sxs-lookup"><span data-stu-id="756b2-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="756b2-108">Microsoft teams USA questa funzionalità per migliorare l'esperienza di riunione.</span><span class="sxs-lookup"><span data-stu-id="756b2-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="756b2-109">La tecnologia NDI® è limitata a una rete locale e deve essere considerata solo una parte del flusso di lavoro di produzione e non una soluzione broadcast.</span><span class="sxs-lookup"><span data-stu-id="756b2-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="756b2-110">Attivare la tecnologia® NDI</span><span class="sxs-lookup"><span data-stu-id="756b2-110">Turn on NDI® technology</span></span>

<span data-ttu-id="756b2-111">La tecnologia NDI® richiede che vengano attivati due passaggi per un utente.</span><span class="sxs-lookup"><span data-stu-id="756b2-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="756b2-112">L'amministratore del tenant deve abilitare la proprietà "AllowNDIStreaming" in CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="756b2-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="756b2-113">Dopo aver popolato questa modifica, l'utente finale deve attivare la tecnologia NDI® per il suo specifico client dalle autorizzazioni per **le impostazioni**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="756b2-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="756b2-114">Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione viene trasmessa.</span><span class="sxs-lookup"><span data-stu-id="756b2-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="756b2-115">Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere abbandonati alla riunione.</span><span class="sxs-lookup"><span data-stu-id="756b2-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="756b2-116">L'immagine seguente mostra il messaggio di banner visualizzato da un utente in una riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="756b2-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Immagine del banner della tecnologia® NDI che viene visualizzato in una riunione teams.](media/NDI-disclosure.png)

<span data-ttu-id="756b2-118">Il banner contiene un collegamento ai [criteri di privacy Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="756b2-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="756b2-119">Impostazioni locali e tipi di utente supportati</span><span class="sxs-lookup"><span data-stu-id="756b2-119">Supported locales and user types</span></span>

<span data-ttu-id="756b2-120">La tecnologia NDI® è supportata in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="756b2-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="756b2-121">Gli utenti seguenti sono inclusi in un flusso di tecnologia® NDI, ma non tutti gli utenti possono accedere al flusso di tecnologia NDI®:</span><span class="sxs-lookup"><span data-stu-id="756b2-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="756b2-122">In-tenant-supporto completo, distribuito in base a Ring/ID tenant/userId (controllato da criteri riunioni)</span><span class="sxs-lookup"><span data-stu-id="756b2-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="756b2-123">Federati: nessun accesso allo stream (anche se hanno la tecnologia NDI®)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="756b2-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="756b2-124">Freemium-nessun accesso allo stream</span><span class="sxs-lookup"><span data-stu-id="756b2-124">Freemium - no stream access</span></span>
- <span data-ttu-id="756b2-125">Anonimo-Nessun accesso allo stream</span><span class="sxs-lookup"><span data-stu-id="756b2-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="756b2-126">Guest: nessun accesso allo stream</span><span class="sxs-lookup"><span data-stu-id="756b2-126">Guest – no stream access</span></span>  

<span data-ttu-id="756b2-127"><sup>1</sup> i dispositivi hanno un'impostazione di tecnologia NDI® attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="756b2-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="756b2-128">Se un partecipante alla riunione usa un dispositivo con NDI® Technology off, dovrà attivare NDI® tecnologia.</span><span class="sxs-lookup"><span data-stu-id="756b2-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
