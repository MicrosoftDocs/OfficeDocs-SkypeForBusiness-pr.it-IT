---
title: Monitorare e migliorare la qualità delle chiamate per Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Usare le impostazioni QoS (Quality of Service) e quindi chiamare Analytics e Call Quality dashboard in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085945"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorare e migliorare la qualità delle chiamate per Microsoft Teams

Questo articolo introduce tre strumenti chiave che è possibile usare per monitorare, risolvere i problemi, gestire e migliorare la qualità delle chiamate in Microsoft teams. 

- **Call Quality Dashboard (Call Quality Dashboard)**: per analizzare le tendenze o i problemi a livello di organizzazione, migliorare le prestazioni delle unità

- **Analisi delle chiamate**: per analizzare la qualità delle chiamate e delle riunioni per singoli utenti

- **Qualità del servizio (QoS)**: per assegnare priorità al traffico di rete importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorare e risolvere i problemi di qualità delle chiamate
Userai **analisi delle chiamate** per utente e **dashboard qualità chiamata** per trovare e risolvere i problemi di qualità delle chiamate che vengono risolti durante l'operazione in corso. In questo modo è possibile migliorare le prestazioni della rete. Entrambi questi strumenti si trovano nell'interfaccia di amministrazione di teams.

 - L' **analisi delle chiamate** consente di visualizzare informazioni dettagliate sui dispositivi, le reti e la connettività relativi a ***chiamate e riunioni specifiche*** per ogni utente in teams. Gli agenti di amministrazione e helpdesk di teams useranno queste informazioni per risolvere i problemi di connessione e qualità delle chiamate in una chiamata specifica. Per altre informazioni, vedere [configurare l'analisi delle chiamate](set-up-call-analytics.md) e [usare la chiamata analitica per la risoluzione dei problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **Call Quality Dashboard (Call Quality Dashboard)** offre una ***visualizzazione a livello di rete*** della qualità delle chiamate nell'organizzazione. Usare le informazioni di Call Quality dashboard per identificare e risolvere i problemi. Prima di tutto, [Configura Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md). Leggere quindi [gestire la qualità delle chiamate e delle riunioni in teams](quality-of-experience-review-guide.md).

 Chiama Analytics e Call Quality dashboard eseguiti in parallelo e possono essere usati in modo indipendente o insieme. Ad esempio, se uno specialista del supporto delle comunicazioni determina che hanno bisogno di ulteriore assistenza per la risoluzione dei problemi di chiamata di un utente, escalano la chiamata a un tecnico del supporto delle comunicazioni, che ha accesso ad altre informazioni sulla chiamata. A sua volta, l'ingegnere del supporto delle comunicazioni avvisa un ingegnere di rete di un possibile problema correlato al sito notato nell'analisi delle chiamate. L'ingegnere della rete controlla Call Quality dashboard per verificare se un problema complessivo relativo al sito potrebbe essere una causa che contribuisce al problema di chiamata dell'utente.


## <a name="prioritize-important-network-traffic-using-qos"></a>Assegnare priorità al traffico di rete importante tramite QoS
Quando gli utenti iniziano a usare team per le chiamate e le riunioni, possono verificare che la voce di un chiamante si rompa o tagli dentro e fuori una chiamata o una riunione. Il video condiviso può bloccare o pixelare o non completamente. Ciò è dovuto ai pacchetti IP che rappresentano il traffico vocale e video che incontrano la congestione della rete e che arrivano fuori sequenza o per niente. In caso affermativo (o per impedirne l'avvenuto inizio), usare la **qualità del servizio (QoS)**. 

Con QoS, è possibile assegnare priorità al traffico di rete sensibile al ritardo, ad esempio i flussi vocali o video, in modo da "tagliare in linea" di fronte al traffico meno sensibile (come scaricare una nuova app, in cui un altro secondo da scaricare non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale usando gli oggetti Criteri di gruppo di Windows e una caratteristica di routing denominata elenchi di controllo di accesso basati su porta, che indica alla rete di dare voce, video e schermo per condividere la propria larghezza di banda di rete dedicata.

In teoria, è possibile implementare QoS nella rete interna mentre si preparano a distribuire Team, ma lo si può fare in qualsiasi momento. Se si è abbastanza piccoli, potrebbe non essere necessario QoS.

Quando si è pronti, leggere [implementare la qualità del servizio (QoS) in Microsoft teams](QoS-in-Teams.md).

Per usare QoS per gestire il traffico delle riunioni, leggere [il modo in cui si vuole gestire il traffico multimediale in tempo reale per le riunioni di Team](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurare Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md)

[Gestire la qualità delle chiamate e delle riunioni in teams](quality-of-experience-review-guide.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

