---
title: Come Microsoft teams USA la memoria
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6dcbe03851b8dbb31cd0bd6f1b580913d4dc683d
ms.sourcegitcommit: f017e38095098d4d28c71241dddac53538be79d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "41506913"
---
# <a name="how-microsoft-teams-uses-memory"></a>Come Microsoft teams USA la memoria

Alcuni utenti di Microsoft Teams hanno domande su come teams USA la memoria. Questo articolo descrive la modalità di utilizzo della memoria da parte dei team e il motivo per cui l'applicazione desktop Teams (app) e l'app Web teams non impediscono ad altre app e carichi di lavoro nello stesso computer di avere memoria sufficiente per l'esecuzione ottimale. Teams è progettato per usare la moderna tecnologia Web. A questo scopo, il client desktop teams è stato sviluppato in Electron, che usa il cromo per il rendering. Questo è lo stesso motore di rendering dietro molti dei browser più diffusi di oggi, tra cui Edge e Chrome.

## <a name="how-teams-works"></a>Funzionamento di Teams

I team progettati su Electron permettono uno sviluppo più rapido e mantiene anche la parità tra le versioni dei team in diversi sistemi operativi (Windows, Mac e Linux). Questa parità è possibile perché Electron e Chromium mantengono una base di codice simile in tutte le versioni. Un altro vantaggio di questa architettura è un simile profilo di utilizzo della memoria tra l'app Web teams e la versione desktop. Sia l'app Web che le versioni desktop usano la memoria in modo simile a come lo userebbe un browser. Altre informazioni su Electron sono disponibili nel [sito Web](https://electronjs.org/).

Per altre informazioni, Vedi [uso della memoria cromo](https://www.chromium.org/developers/memory-usage-backgrounder) e [concetti chiave nella memoria di Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .

L'immagine seguente mostra l'utilizzo di memoria affiancata dell'app desktop teams per Windows e dell'app Web Teams (in questo esempio, in corso in Google Chrome).

![App desktop teams e uso della memoria delle app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso della memoria in teams

È importante comprendere il comportamento *previsto* dei team quando si tratta di memoria di sistema e conoscere i sintomi dei problemi di memoria di sistema veramente problematici.

### <a name="expected-memory-usage-by-teams"></a>Utilizzo della memoria previsto da teams

Sia che si stia eseguendo l'app desktop teams o l'app Web teams, Chromium rileva la quantità di memoria di sistema disponibile e ne utilizza abbastanza per ottimizzare l'esperienza di rendering. Quando altre app o servizi richiedono memoria di sistema, Chromium restituisce memoria a questi processi. Chromium sintonizza l'uso della memoria in modo continuo per ottimizzare le prestazioni dei team senza influire su altre operazioni attualmente in esecuzione.

In questo modo, i carichi di lavoro di cromo simili possono usare quantità diverse di memoria, a seconda della quantità di memoria di sistema disponibile.

Il grafico seguente descrive l'utilizzo della memoria da parte di Team su quattro sistemi distinti, ognuno con una quantità di memoria diversa disponibile. Ognuno dei sistemi sta elaborando carichi di lavoro simili (le stesse app sono aperte e in esecuzione).

![Uso della memoria in teams in diversi sistemi](media/teams-memory-usage.png)

Quando i computer hanno più memoria, i team useranno la memoria. Nei sistemi in cui la memoria è scarsa, le squadre useranno meno. 

### <a name="symptoms-of-system-memory-issues"></a>Sintomi dei problemi di memoria di sistema

Se nel computer sono presenti uno o più dei sintomi seguenti, è possibile che venga visualizzato un problema di memoria di sistema grave:

- Uso di memoria elevata quando si esegue contemporaneamente più applicazioni di grandi dimensioni.
- Rallentamento delle prestazioni del sistema o delle applicazioni sospese.
- Utilizzo complessivo della memoria di sistema globale di 90% o superiore in tutte le app. Con questa quantità di utilizzo della memoria, i team dovrebbero restituire memoria ad altre app e carichi di lavoro. L'utilizzo di memoria sostenuta di 90% potrebbe significare che i team non restituiscono memoria al sistema, che indica un problema.

Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anormalmente elevato.

![Visualizzazione utilizzo memoria teams in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Grafico utilizzo memoria teams in Gestione attività](media/teams-memory-high-mem-process-list2.png)
