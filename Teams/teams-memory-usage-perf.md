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
# <a name="how-microsoft-teams-uses-memory"></a>Come viene usata la memoria in Microsoft Teams

Alcuni Microsoft Teams hanno domande su come Teams memoria. Questo articolo descrive come viene usata la memoria da Teams e perché l'applicazione desktop Teams e l'app Web Teams non impediscono l'esecuzione ottimale di altre app e carichi di lavoro nello stesso computer. Teams è progettato per usare la moderna tecnologia Web. A questo scopo, il client Teams desktop è stato sviluppato su Electron, che usa Chromium per il rendering. Questo è lo stesso motore di rendering dietro molti dei browser più diffusi di oggi, tra cui Edge e Chrome.

## <a name="how-teams-works"></a>Come Teams funzionamento

Teams progettato su Electron consente uno sviluppo più rapido e mantiene anche la parità tra le versioni Teams in diversi sistemi operativi (Windows, Mac e Linux). Questa parità è possibile perché Electron e Chromium una base di codice simile in tutte le versioni. Un altro vantaggio di questa architettura è che esiste un profilo di utilizzo della memoria simile tra l'app Web Teams e la versione desktop. Sia l'app Web che le versioni desktop usano la memoria in modo simile a come verrebbe utilizzata da un browser. Altre informazioni su Electron sono disponibili [sul loro sito Web.](https://electronjs.org/)

Per [altre Chromium, vedere](https://www.chromium.org/developers/memory-usage-backgrounder) Uso della memoria e Concetti chiave in Chrome [Memory.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)

L'immagine seguente mostra gli utilizzi affiancati della memoria dell'app desktop Teams per Windows e dell'app Web Teams (in questo esempio, in esecuzione in Google Chrome).

![Teams memoria per l'app desktop e l'app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilizzo della memoria in Teams

È importante comprendere  il comportamento previsto di Teams quando si tratta di memoria di sistema e conoscere i sintomi di problemi di memoria di sistema davvero problematici.

### <a name="expected-memory-usage-by-teams"></a>Utilizzo previsto della memoria per Teams

Se si esegue l'app desktop Teams o l'app Web Teams, Chromium rileva la quantità di memoria di sistema disponibile e ne usa una quantità sufficiente per ottimizzare l'esperienza di rendering. Quando altre app o servizi richiedono memoria di sistema, Chromium memoria a tali processi. Chromium sintonizzi l Teams di memoria su base continuativa per ottimizzare Teams prestazioni senza influire sugli altri dati attualmente in esecuzione.

In questo modo, carichi Chromium carichi di lavoro simili possono usare quantità variabili di memoria, a seconda della quantità di memoria di sistema disponibile.

Il grafico seguente illustra l'utilizzo della memoria Teams in quattro sistemi separati, ognuno con quantità di memoria diverse disponibili. Ognuno dei sistemi sta elaborando carichi di lavoro simili (stesse app aperte ed in esecuzione).

![Teams utilizzo della memoria in sistemi diversi](media/teams-memory-usage.png)

Quando i computer hanno più memoria, Teams la memoria. Nei sistemi in cui la memoria è scarsa, Teams utilizzerà meno.

### <a name="symptoms-of-system-memory-issues"></a>Sintomi di problemi di memoria di sistema

Se nel computer sono visualizzati uno o più dei sintomi seguenti, potrebbe verificarsi un grave problema di memoria di sistema:

- Utilizzo elevato della memoria quando più applicazioni di grandi dimensioni vengono eseguite contemporaneamente.
- Rallentamento delle prestazioni del sistema o delle applicazioni sospese.
- Utilizzo della memoria di sistema complessivo sostenuto del 90% o superiore in tutte le app. Con questa quantità di utilizzo della memoria, Teams la memoria dovrebbe essere tornata ad altre app e carichi di lavoro. Un utilizzo sostenuto della memoria del 90% potrebbe significare che Teams memoria non viene tornata al sistema, il che indica un problema.

Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anomalo.

![Teams di utilizzo della memoria in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Teams di utilizzo della memoria in Gestione attività](media/teams-memory-high-mem-process-list2.png)
