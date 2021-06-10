---
title: Come viene usata la memoria in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Informazioni sull Microsoft Teams di memoria di sistema e sul motivo per cui l'utilizzo della memoria è lo stesso tra l'applicazione desktop e l'applicazione Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878720"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="8ce70-103">Come viene usata la memoria in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ce70-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="8ce70-104">Alcuni Microsoft Teams hanno domande su come Teams memoria.</span><span class="sxs-lookup"><span data-stu-id="8ce70-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="8ce70-105">Questo articolo descrive come viene usata la memoria da Teams e perché l'applicazione desktop Teams e l'app Web Teams non impediscono l'esecuzione ottimale di altre app e carichi di lavoro nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="8ce70-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="8ce70-106">Teams è progettato per usare la moderna tecnologia Web.</span><span class="sxs-lookup"><span data-stu-id="8ce70-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="8ce70-107">A questo scopo, il client Teams desktop è stato sviluppato su Electron, che usa Chromium per il rendering.</span><span class="sxs-lookup"><span data-stu-id="8ce70-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="8ce70-108">Questo è lo stesso motore di rendering dietro molti dei browser più diffusi di oggi, tra cui Edge e Chrome.</span><span class="sxs-lookup"><span data-stu-id="8ce70-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="8ce70-109">Come Teams funzionamento</span><span class="sxs-lookup"><span data-stu-id="8ce70-109">How Teams works</span></span>

<span data-ttu-id="8ce70-110">Teams progettato su Electron consente uno sviluppo più rapido e mantiene anche la parità tra le versioni Teams in diversi sistemi operativi (Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="8ce70-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="8ce70-111">Questa parità è possibile perché Electron e Chromium una base di codice simile in tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="8ce70-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="8ce70-112">Un altro vantaggio di questa architettura è che esiste un profilo di utilizzo della memoria simile tra l'app Web Teams e la versione desktop.</span><span class="sxs-lookup"><span data-stu-id="8ce70-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="8ce70-113">Sia l'app Web che le versioni desktop usano la memoria in modo simile a come verrebbe utilizzata da un browser.</span><span class="sxs-lookup"><span data-stu-id="8ce70-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="8ce70-114">Altre informazioni su Electron sono disponibili [sul loro sito Web.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="8ce70-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="8ce70-115">Per [altre Chromium, vedere](https://www.chromium.org/developers/memory-usage-backgrounder) Uso della memoria e Concetti chiave in Chrome [Memory.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)</span><span class="sxs-lookup"><span data-stu-id="8ce70-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="8ce70-116">L'immagine seguente mostra gli utilizzi affiancati della memoria dell'app desktop Teams per Windows e dell'app Web Teams (in questo esempio, in esecuzione in Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="8ce70-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams memoria per l'app desktop e l'app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="8ce70-118">Utilizzo della memoria in Teams</span><span class="sxs-lookup"><span data-stu-id="8ce70-118">Memory usage in Teams</span></span>

<span data-ttu-id="8ce70-119">È importante comprendere  il comportamento previsto di Teams quando si tratta di memoria di sistema e conoscere i sintomi di problemi di memoria di sistema davvero problematici.</span><span class="sxs-lookup"><span data-stu-id="8ce70-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="8ce70-120">Utilizzo previsto della memoria per Teams</span><span class="sxs-lookup"><span data-stu-id="8ce70-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="8ce70-121">Se si esegue l'app desktop Teams o l'app Web Teams, Chromium rileva la quantità di memoria di sistema disponibile e ne usa una quantità sufficiente per ottimizzare l'esperienza di rendering.</span><span class="sxs-lookup"><span data-stu-id="8ce70-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="8ce70-122">Quando altre app o servizi richiedono memoria di sistema, Chromium memoria a tali processi.</span><span class="sxs-lookup"><span data-stu-id="8ce70-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="8ce70-123">Chromium sintonizzi l Teams di memoria su base continuativa per ottimizzare Teams prestazioni senza influire sugli altri dati attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8ce70-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="8ce70-124">In questo modo, carichi Chromium carichi di lavoro simili possono usare quantità variabili di memoria, a seconda della quantità di memoria di sistema disponibile.</span><span class="sxs-lookup"><span data-stu-id="8ce70-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="8ce70-125">Il grafico seguente illustra l'utilizzo della memoria Teams in quattro sistemi separati, ognuno con quantità di memoria diverse disponibili.</span><span class="sxs-lookup"><span data-stu-id="8ce70-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="8ce70-126">Ognuno dei sistemi sta elaborando carichi di lavoro simili (stesse app aperte ed in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="8ce70-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Teams utilizzo della memoria in sistemi diversi](media/teams-memory-usage.png)

<span data-ttu-id="8ce70-128">Quando i computer hanno più memoria, Teams la memoria.</span><span class="sxs-lookup"><span data-stu-id="8ce70-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="8ce70-129">Nei sistemi in cui la memoria è scarsa, Teams utilizzerà meno.</span><span class="sxs-lookup"><span data-stu-id="8ce70-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="8ce70-130">Sintomi di problemi di memoria di sistema</span><span class="sxs-lookup"><span data-stu-id="8ce70-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="8ce70-131">Se nel computer sono visualizzati uno o più dei sintomi seguenti, potrebbe verificarsi un grave problema di memoria di sistema:</span><span class="sxs-lookup"><span data-stu-id="8ce70-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="8ce70-132">Utilizzo elevato della memoria quando più applicazioni di grandi dimensioni vengono eseguite contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8ce70-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="8ce70-133">Rallentamento delle prestazioni del sistema o delle applicazioni sospese.</span><span class="sxs-lookup"><span data-stu-id="8ce70-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="8ce70-134">Utilizzo della memoria di sistema complessivo sostenuto del 90% o superiore in tutte le app.</span><span class="sxs-lookup"><span data-stu-id="8ce70-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="8ce70-135">Con questa quantità di utilizzo della memoria, Teams la memoria dovrebbe essere tornata ad altre app e carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ce70-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="8ce70-136">Un utilizzo sostenuto della memoria del 90% potrebbe significare che Teams memoria non viene tornata al sistema, il che indica un problema.</span><span class="sxs-lookup"><span data-stu-id="8ce70-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="8ce70-137">Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anomalo.</span><span class="sxs-lookup"><span data-stu-id="8ce70-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Teams di utilizzo della memoria in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Teams di utilizzo della memoria in Gestione attività](media/teams-memory-high-mem-process-list2.png)
