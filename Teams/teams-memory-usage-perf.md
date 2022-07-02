---
title: Come viene usata la memoria in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Informazioni sull'utilizzo della memoria di sistema di Microsoft Teams e sul motivo per cui l'utilizzo della memoria è lo stesso tra l'applicazione desktop e l'applicazione Web.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 0d55caf2a1642b28ccc63e3be1cf3eccc69bb260
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605675"
---
# <a name="how-microsoft-teams-uses-memory"></a>Come viene usata la memoria in Microsoft Teams

Alcuni utenti di Microsoft Teams hanno domande su come Teams usa la memoria. Questo articolo descrive come viene usata la memoria da Teams e perché l'applicazione desktop di Teams (app) e l'app Web di Teams non impediscono ad altre app e carichi di lavoro nello stesso computer di avere memoria sufficiente per funzionare in modo ottimale. Teams è progettato per usare la moderna tecnologia Web. A questo scopo, il client desktop di Teams è stato sviluppato su Electron, che utilizza Chromium per il rendering. Questo è lo stesso motore di rendering dietro molti dei browser più popolari di oggi, tra cui Edge e Chrome.

## <a name="how-teams-works"></a>Come funziona Teams

Teams progettato su Electron consente uno sviluppo più rapido e mantiene la parità tra le versioni di Teams in diversi sistemi operativi (Windows, Mac e Linux). Questa parità è possibile perché Electron e Chromium mantenere una base di codice simile in tutte le versioni. Un altro vantaggio di questa architettura è che esiste un profilo di utilizzo della memoria simile tra l'app Web di Teams e la versione desktop. Sia l'app Web che le versioni desktop usano la memoria in modo simile a come viene usata da un browser. Ulteriori informazioni su Electron sono disponibili sul [loro sito Web](https://electronjs.org/).

Per altre informazioni, vedi Chromium concetti relativi [all'utilizzo della memoria](https://www.chromium.org/developers/memory-usage-backgrounder) e alle [chiavi nella memoria Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md).

L'immagine seguente mostra l'utilizzo affiancato della memoria dell'app desktop Teams per Windows e dell'app Web teams (in questo esempio, in esecuzione in Google Chrome).

![Utilizzo della memoria di Teams per l'app desktop e l'app Web.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilizzo della memoria in Teams

È importante comprendere il comportamento *previsto* di Teams quando si tratta di memoria di sistema e conoscere i sintomi di problemi di memoria di sistema veramente problematici.

### <a name="expected-memory-usage-by-teams"></a>Utilizzo di memoria previsto da parte di Teams

Sia che tu stia eseguendo l'app desktop Teams o l'app Web di Teams, Chromium rileva la quantità di memoria di sistema disponibile e utilizza una quantità sufficiente di memoria per ottimizzare l'esperienza di rendering. Quando altri servizi o app richiedono memoria di sistema, Chromium scarica memoria da tali processi. Chromium l'utilizzo della memoria di Teams su base continuativa per ottimizzare le prestazioni di Teams senza influire su altri elementi in esecuzione.

In questo modo, carichi di lavoro Chromium simili possono utilizzare quantità variabili di memoria, a seconda della quantità di memoria di sistema disponibile.

Il grafico seguente illustra l'utilizzo della memoria da parte di Teams su quattro sistemi separati, ognuno con quantità di memoria diverse disponibili. Ognuno dei sistemi sta elaborando carichi di lavoro simili (stesse app aperte ed in esecuzione).

![Utilizzo della memoria di Teams in sistemi diversi.](media/teams-memory-usage.png)

Quando i computer hanno più memoria, Teams userà tale memoria. Nei sistemi in cui la memoria è scarsa, Teams userà meno.

### <a name="symptoms-of-system-memory-issues"></a>Sintomi dei problemi di memoria del sistema

Se nel computer sono presenti uno o più dei sintomi seguenti, è possibile che si sia verificato un grave problema di memoria di sistema:

- Uso di memoria elevata quando più applicazioni di grandi dimensioni sono in esecuzione contemporaneamente.
- Prestazioni del sistema lente o applicazioni in sospeso.
- Utilizzo complessivo prolungato della memoria di sistema del 90% o superiore in tutte le app. Con questa quantità di utilizzo della memoria, Teams dovrebbe restituire memoria ad altre app e carichi di lavoro. Un utilizzo prolungato della memoria del 90% potrebbe significare che Teams non sta resti comunicando memoria al sistema, il che indica un problema.

Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anormalmente elevato.

![Visualizzazione utilizzo memoria di Teams in Gestione attività.](media/teams-memory-high-mem-process-list.png)

![Grafico sull'utilizzo della memoria di Teams in Gestione attività.](media/teams-memory-high-mem-process-list2.png)
