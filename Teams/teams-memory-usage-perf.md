---
title: Come viene usata la memoria in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Informazioni sull'utilizzo della memoria di sistema di Microsoft Teams e sul motivo per cui l'utilizzo della memoria è lo stesso tra l'applicazione desktop e l'applicazione Web.
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
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="da397-103">Come viene usata la memoria in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da397-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="da397-104">Alcuni utenti di Microsoft Teams hanno domande sul modo in cui Teams usa la memoria.</span><span class="sxs-lookup"><span data-stu-id="da397-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="da397-105">Questo articolo descrive come viene usata la memoria da Teams e perché l'applicazione desktop (app) di Teams e l'app Web di Teams non impediscono ad altre app e carichi di lavoro nello stesso computer di avere una quantità di memoria sufficiente per essere eseguita in modo ottimale.</span><span class="sxs-lookup"><span data-stu-id="da397-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="da397-106">Teams è progettato per usare la tecnologia Web moderna.</span><span class="sxs-lookup"><span data-stu-id="da397-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="da397-107">Per raggiungere questo obiettivo, il client desktop di Teams è stato sviluppato su Electron, che usa Chromium per il rendering.</span><span class="sxs-lookup"><span data-stu-id="da397-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="da397-108">Si tratta dello stesso motore di rendering dietro molti dei browser più diffusi, tra cui Microsoft Edge e Chrome.</span><span class="sxs-lookup"><span data-stu-id="da397-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="da397-109">Funzionamento di Teams</span><span class="sxs-lookup"><span data-stu-id="da397-109">How Teams works</span></span>

<span data-ttu-id="da397-110">Teams progettato su Electron consente uno sviluppo più rapido e mantiene la parità tra le versioni di Teams in sistemi operativi diversi (Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="da397-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="da397-111">Questa parità è possibile perché Electron e Chromium mantengono una base di codice simile in tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="da397-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="da397-112">Un altro vantaggio di questa architettura è che esiste un profilo di utilizzo della memoria simile tra l'app Web di Teams e la versione desktop.</span><span class="sxs-lookup"><span data-stu-id="da397-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="da397-113">Sia l'app Web che la versione desktop usano la memoria in modo simile a come verrebbe utilizzata da un browser.</span><span class="sxs-lookup"><span data-stu-id="da397-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="da397-114">Altre informazioni su Electron sono disponibili [sul loro sito Web.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="da397-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="da397-115">Per altre informazioni, vedere Utilizzo della memoria [Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) e [concetti chiave nella memoria Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)</span><span class="sxs-lookup"><span data-stu-id="da397-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="da397-116">L'immagine seguente mostra utilizzi affiancati della memoria dell'app desktop Teams per Windows e dell'app Web di Teams (in questo esempio in esecuzione in Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="da397-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Utilizzo della memoria di Teams per l'app desktop e l'app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="da397-118">Utilizzo della memoria in Teams</span><span class="sxs-lookup"><span data-stu-id="da397-118">Memory usage in Teams</span></span>

<span data-ttu-id="da397-119">È importante comprendere  il comportamento previsto di Teams per quanto riguarda la memoria di sistema e conoscere i sintomi di problemi realmente problematici della memoria di sistema.</span><span class="sxs-lookup"><span data-stu-id="da397-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="da397-120">Uso della memoria previsto da Teams</span><span class="sxs-lookup"><span data-stu-id="da397-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="da397-121">Che si esega l'app desktop di Teams o l'app Web di Teams, Chromium rileva la quantità di memoria di sistema disponibile e usa una quantità sufficiente di tale memoria per ottimizzare l'esperienza di rendering.</span><span class="sxs-lookup"><span data-stu-id="da397-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="da397-122">Quando altre app o servizi richiedono memoria di sistema, Chromium cede memoria a questi processi.</span><span class="sxs-lookup"><span data-stu-id="da397-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="da397-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span><span class="sxs-lookup"><span data-stu-id="da397-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="da397-124">In questo modo, carichi di lavoro di Chromium simili possono utilizzare quantità variabili di memoria, a seconda della quantità di memoria di sistema disponibile.</span><span class="sxs-lookup"><span data-stu-id="da397-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="da397-125">Il grafico seguente illustra l'utilizzo della memoria da parte di Teams in quattro sistemi separati, ognuno con quantità diverse di memoria disponibili.</span><span class="sxs-lookup"><span data-stu-id="da397-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="da397-126">Ognuno dei sistemi elabora carichi di lavoro simili , ovvero le stesse app aperte ed in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="da397-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Utilizzo della memoria di Teams in sistemi diversi](media/teams-memory-usage.png)

<span data-ttu-id="da397-128">Quando i computer hanno più memoria, Teams userà tale memoria.</span><span class="sxs-lookup"><span data-stu-id="da397-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="da397-129">Nei sistemi in cui la memoria è importante, Teams userà meno.</span><span class="sxs-lookup"><span data-stu-id="da397-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="da397-130">Sintomi dei problemi di memoria del sistema</span><span class="sxs-lookup"><span data-stu-id="da397-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="da397-131">Se si verificano uno o più dei sintomi seguenti nel computer, potrebbe verificarsi un problema grave relativo alla memoria del sistema:</span><span class="sxs-lookup"><span data-stu-id="da397-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="da397-132">Utilizzo di memoria elevata quando più applicazioni di grandi dimensioni vengono eseguite contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="da397-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="da397-133">Prestazioni di sistema lente o applicazioni sospese.</span><span class="sxs-lookup"><span data-stu-id="da397-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="da397-134">Un utilizzo generale della memoria di sistema sostenuto del 90% o superiore in tutte le app.</span><span class="sxs-lookup"><span data-stu-id="da397-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="da397-135">Con questa quantità di utilizzo della memoria, Teams dovrebbe fornire memoria ad altre app e carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="da397-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="da397-136">L'uso della memoria sostenuta del 90% potrebbe significare che Teams non sta tornerà alla memoria del sistema, il che indica un problema.</span><span class="sxs-lookup"><span data-stu-id="da397-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="da397-137">Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anomale.</span><span class="sxs-lookup"><span data-stu-id="da397-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Visualizzazione Utilizzo memoria di Teams in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Diagramma di utilizzo della memoria di Teams in Gestione attività](media/teams-memory-high-mem-process-list2.png)
