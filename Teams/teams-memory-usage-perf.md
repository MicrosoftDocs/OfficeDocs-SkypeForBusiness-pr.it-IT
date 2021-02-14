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
# <a name="how-microsoft-teams-uses-memory"></a>Come viene usata la memoria in Microsoft Teams

Alcuni utenti di Microsoft Teams hanno domande sul modo in cui Teams usa la memoria. Questo articolo descrive come viene usata la memoria da Teams e perché l'applicazione desktop (app) di Teams e l'app Web di Teams non impediscono ad altre app e carichi di lavoro nello stesso computer di avere una quantità di memoria sufficiente per essere eseguita in modo ottimale. Teams è progettato per usare la tecnologia Web moderna. Per raggiungere questo obiettivo, il client desktop di Teams è stato sviluppato su Electron, che usa Chromium per il rendering. Si tratta dello stesso motore di rendering dietro molti dei browser più diffusi, tra cui Microsoft Edge e Chrome.

## <a name="how-teams-works"></a>Funzionamento di Teams

Teams progettato su Electron consente uno sviluppo più rapido e mantiene la parità tra le versioni di Teams in sistemi operativi diversi (Windows, Mac e Linux). Questa parità è possibile perché Electron e Chromium mantengono una base di codice simile in tutte le versioni. Un altro vantaggio di questa architettura è che esiste un profilo di utilizzo della memoria simile tra l'app Web di Teams e la versione desktop. Sia l'app Web che la versione desktop usano la memoria in modo simile a come verrebbe utilizzata da un browser. Altre informazioni su Electron sono disponibili [sul loro sito Web.](https://electronjs.org/)

Per altre informazioni, vedere Utilizzo della memoria [Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) e [concetti chiave nella memoria Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)

L'immagine seguente mostra utilizzi affiancati della memoria dell'app desktop Teams per Windows e dell'app Web di Teams (in questo esempio in esecuzione in Google Chrome).

![Utilizzo della memoria di Teams per l'app desktop e l'app Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Utilizzo della memoria in Teams

È importante comprendere  il comportamento previsto di Teams per quanto riguarda la memoria di sistema e conoscere i sintomi di problemi realmente problematici della memoria di sistema.

### <a name="expected-memory-usage-by-teams"></a>Uso della memoria previsto da Teams

Che si esega l'app desktop di Teams o l'app Web di Teams, Chromium rileva la quantità di memoria di sistema disponibile e usa una quantità sufficiente di tale memoria per ottimizzare l'esperienza di rendering. Quando altre app o servizi richiedono memoria di sistema, Chromium cede memoria a questi processi. Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.

In questo modo, carichi di lavoro di Chromium simili possono utilizzare quantità variabili di memoria, a seconda della quantità di memoria di sistema disponibile.

Il grafico seguente illustra l'utilizzo della memoria da parte di Teams in quattro sistemi separati, ognuno con quantità diverse di memoria disponibili. Ognuno dei sistemi elabora carichi di lavoro simili , ovvero le stesse app aperte ed in esecuzione.

![Utilizzo della memoria di Teams in sistemi diversi](media/teams-memory-usage.png)

Quando i computer hanno più memoria, Teams userà tale memoria. Nei sistemi in cui la memoria è importante, Teams userà meno.

### <a name="symptoms-of-system-memory-issues"></a>Sintomi dei problemi di memoria del sistema

Se si verificano uno o più dei sintomi seguenti nel computer, potrebbe verificarsi un problema grave relativo alla memoria del sistema:

- Utilizzo di memoria elevata quando più applicazioni di grandi dimensioni vengono eseguite contemporaneamente.
- Prestazioni di sistema lente o applicazioni sospese.
- Un utilizzo generale della memoria di sistema sostenuto del 90% o superiore in tutte le app. Con questa quantità di utilizzo della memoria, Teams dovrebbe fornire memoria ad altre app e carichi di lavoro. L'uso della memoria sostenuta del 90% potrebbe significare che Teams non sta tornerà alla memoria del sistema, il che indica un problema.

Le immagini seguenti mostrano esempi di visualizzazioni in Gestione attività quando l'utilizzo della memoria di sistema è anomale.

![Visualizzazione Utilizzo memoria di Teams in Gestione attività](media/teams-memory-high-mem-process-list.png)

![Diagramma di utilizzo della memoria di Teams in Gestione attività](media/teams-memory-high-mem-process-list2.png)
