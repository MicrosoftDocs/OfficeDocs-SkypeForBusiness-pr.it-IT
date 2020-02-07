---
title: Come viene usata la memoria in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: In che modo Microsoft teams USA la memoria di sistema e perché l'utilizzo della memoria è lo stesso tra l'applicazione desktop e l'applicazione Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05cbd2f4b6691c873393a7ba711e03aadf70a2f2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836986"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="2de79-103">Come viene usata la memoria in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2de79-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="2de79-104">Alcuni utenti di Microsoft Teams hanno domande su come teams USA la memoria.</span><span class="sxs-lookup"><span data-stu-id="2de79-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="2de79-105">Questo articolo descrive la modalità di utilizzo della memoria da parte dei team e il motivo per cui l'applicazione desktop Teams (app) e l'app Web teams non impediscono ad altre app e carichi di lavoro nello stesso computer di avere memoria sufficiente per l'esecuzione ottimale.</span><span class="sxs-lookup"><span data-stu-id="2de79-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="2de79-106">Teams è progettato per usare la moderna tecnologia Web.</span><span class="sxs-lookup"><span data-stu-id="2de79-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="2de79-107">A questo scopo, il client desktop teams è stato sviluppato in Electron, che usa il cromo per il rendering.</span><span class="sxs-lookup"><span data-stu-id="2de79-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="2de79-108">Questo è lo stesso motore di rendering dietro molti dei browser più diffusi di oggi, tra cui Edge e Chrome.</span><span class="sxs-lookup"><span data-stu-id="2de79-108">This is the same rendering engine behind many of today’s most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="2de79-109">Funzionamento di Teams</span><span class="sxs-lookup"><span data-stu-id="2de79-109">How Teams works</span></span>

<span data-ttu-id="2de79-110">I team progettati su Electron permettono uno sviluppo più rapido e mantiene anche la parità tra le versioni dei team in diversi sistemi operativi (Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="2de79-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="2de79-111">Questa parità è possibile perché Electron e Chromium mantengono una base di codice simile in tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="2de79-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="2de79-112">Un altro vantaggio di questa architettura è un simile profilo di utilizzo della memoria tra l'app Web teams e la versione desktop.</span><span class="sxs-lookup"><span data-stu-id="2de79-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="2de79-113">Sia l'app Web che le versioni desktop usano la memoria in modo simile a come lo userebbe un browser.</span><span class="sxs-lookup"><span data-stu-id="2de79-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="2de79-114">Altre informazioni su Electron sono disponibili nel [sito Web](https://electronjs.org/).</span><span class="sxs-lookup"><span data-stu-id="2de79-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="2de79-115">Per altre informazioni, Vedi [uso della memoria cromo](https://www.chromium.org/developers/memory-usage-backgrounder) e [concetti chiave nella memoria di Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .</span><span class="sxs-lookup"><span data-stu-id="2de79-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="2de79-116">L'immagine seguente mostra l'utilizzo di memoria affiancata dell'app desktop teams per Windows e dell'app Web Teams (in questo esempio, in corso in Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="2de79-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![App desktop teams e uso della memoria delle app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="2de79-118">Uso della memoria in teams</span><span class="sxs-lookup"><span data-stu-id="2de79-118">Memory usage in Teams</span></span>

<span data-ttu-id="2de79-119">È importante comprendere il comportamento *previsto* dei team quando si tratta di memoria di sistema e conoscere i sintomi dei problemi di memoria di sistema veramente problematici.</span><span class="sxs-lookup"><span data-stu-id="2de79-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="2de79-120">Utilizzo della memoria previsto da teams</span><span class="sxs-lookup"><span data-stu-id="2de79-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="2de79-121">Sia che si stia eseguendo l'app desktop teams o l'app Web teams, Chromium rileva la quantità di memoria di sistema disponibile e ne utilizza abbastanza per ottimizzare l'esperienza di rendering.</span><span class="sxs-lookup"><span data-stu-id="2de79-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="2de79-122">Quando altre app o servizi richiedono memoria di sistema, Chromium restituisce memoria a questi processi.</span><span class="sxs-lookup"><span data-stu-id="2de79-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="2de79-123">Chromium sintonizza l'uso della memoria in modo continuo per ottimizzare le prestazioni dei team senza influire su altre operazioni attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2de79-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="2de79-124">In questo modo, i carichi di lavoro di cromo simili possono usare quantità diverse di memoria, a seconda della quantità di memoria di sistema disponibile.</span><span class="sxs-lookup"><span data-stu-id="2de79-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="2de79-125">Il grafico seguente descrive l'utilizzo della memoria da parte di Team su quattro sistemi distinti, ognuno con una quantità di memoria diversa disponibile.</span><span class="sxs-lookup"><span data-stu-id="2de79-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="2de79-126">Ognuno dei sistemi sta elaborando carichi di lavoro simili (le stesse app sono aperte e in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="2de79-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Uso della memoria in teams in diversi sistemi](media/teams-memory-usage.png)

<span data-ttu-id="2de79-128">Quando i computer hanno più memoria, i team useranno la memoria.</span><span class="sxs-lookup"><span data-stu-id="2de79-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="2de79-129">Nei sistemi in cui la memoria è scarsa, le squadre useranno meno.</span><span class="sxs-lookup"><span data-stu-id="2de79-129">In systems where memory is scarce, Teams will use less.</span></span> 

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="2de79-130">Sintomi dei problemi di memoria di sistema</span><span class="sxs-lookup"><span data-stu-id="2de79-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="2de79-131">Se nel computer sono presenti uno o più dei sintomi seguenti, è possibile che venga visualizzato un problema di memoria di sistema grave:</span><span class="sxs-lookup"><span data-stu-id="2de79-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="2de79-132">Uso di memoria elevata quando si esegue contemporaneamente più applicazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2de79-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="2de79-133">Rallentamento delle prestazioni del sistema o delle applicazioni sospese.</span><span class="sxs-lookup"><span data-stu-id="2de79-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="2de79-134">Utilizzo complessivo della memoria di sistema globale di 90% o superiore in tutte le app.</span><span class="sxs-lookup"><span data-stu-id="2de79-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="2de79-135">Con questa quantità di utilizzo della memoria, i team dovrebbero restituire memoria ad altre app e carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2de79-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="2de79-136">L'utilizzo di memoria sostenuta di 90% potrebbe significare che i team non restituiscono memoria al sistema, che indica un problema.</span><span class="sxs-lookup"><span data-stu-id="2de79-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="2de79-137">Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anormalmente elevato.</span><span class="sxs-lookup"><span data-stu-id="2de79-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Visualizzazione utilizzo memoria teams in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Grafico utilizzo memoria teams in Gestione attività](media/teams-memory-high-mem-process-list2.png)
