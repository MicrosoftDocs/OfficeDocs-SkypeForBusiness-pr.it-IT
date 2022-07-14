---
title: Monitorare e migliorare la qualità delle chiamate per Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Usare le impostazioni QoS (Quality of Service) e quindi Call Analytics e Call Quality Dashboard in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793243"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorare e migliorare la qualità delle chiamate per Microsoft Teams

Questo articolo introduce tre strumenti chiave che è possibile usare per monitorare, risolvere i problemi, gestire e migliorare la qualità delle chiamate in Microsoft Teams. 

- **Call Quality Dashboard (CQD):** per analizzare le tendenze o i problemi a livello di organizzazione, migliorare le prestazioni

- **Analisi delle chiamate**: per analizzare la qualità delle chiamate e delle riunioni per i singoli utenti

- **QoS (Quality of Service):** per assegnare priorità al traffico di rete importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorare e risolvere i problemi relativi alla qualità delle chiamate
Userai **l'analisi delle chiamate** per utente e **call quality dashboard** per trovare e risolvere i problemi di qualità delle chiamate che si verificano durante il funzionamento in corso. In questo modo puoi migliorare le prestazioni in tutta la rete. Entrambi questi strumenti si trovano nell'interfaccia di amministrazione di Teams.

 - **L'analisi delle** chiamate mostra informazioni dettagliate su dispositivi, reti e connettività relative a  **_chiamate e riunioni specifiche_** per ogni utente in Teams. L'amministratore di Teams e gli agenti helpdesk useranno queste informazioni per risolvere i problemi di qualità delle chiamate e di connessione in una chiamata specifica. Per ulteriori informazioni, leggi [Configurare l'analisi delle chiamate](set-up-call-analytics.md) e [Usare Call Analytics per risolvere i problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **Call Quality Dashboard (CQD)** offre una **_visualizzazione a livello di rete_** della qualità delle chiamate nell'intera organizzazione. Usare le informazioni di Call Quality Dashboard per identificare e risolvere i problemi. Prima di tutto, [configurare Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md). Leggere quindi [Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md).

 Call Analytics e Call Analytics vengono eseguiti in parallelo e possono essere usati in modo indipendente o insieme. Ad esempio, se uno specialista del supporto per le comunicazioni ritiene che abbia bisogno di ulteriore assistenza per risolvere il problema di chiamata di un utente, inoltra la chiamata a un tecnico del supporto per le comunicazioni, che ha accesso a informazioni aggiuntive sulla chiamata. A sua volta, il tecnico del supporto per le comunicazioni segnala a un tecnico di rete un possibile problema correlato al sito rilevato nell'analisi delle chiamate. Il tecnico di rete controlla CQD per vedere se un problema generale relativo al sito potrebbe essere una causa del problema di chiamata dell'utente.


## <a name="prioritize-important-network-traffic-using-qos"></a>Assegnare la priorità al traffico di rete importante utilizzando la QoS
Quando gli utenti iniziano a usare Teams per chiamate e riunioni, potrebbero riscontrare la rottura o il taglio di una chiamata o di una riunione da parte di un chiamante. I video condivisi possono bloccarsi o pixelare o non riuscire del tutto. Ciò è dovuto ai pacchetti IP che rappresentano il traffico voce e video che rileva una congestione di rete e che esce dalla sequenza o non arriva affatto. In questo caso (o per impedire che si verifichi in primo luogo), usare **QoS (Quality of Service).** 

Con la QoS, è possibile classificare in ordine di priorità il traffico di rete sensibile al ritardo (ad esempio, flussi vocali o video), consentendogli di "tagliare in riga" davanti al traffico meno sensibile (come il download di una nuova app, in cui un secondo in più da scaricare non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale utilizzando Windows Criteri di gruppo Objects e una funzionalità di routing denominata Port-based Controllo di accesso Lists, che indica alla rete di fornire alla rete la propria larghezza di banda di rete dedicata per la condivisione di audio, video e schermo.

Idealmente, è possibile implementare la QoS nella rete interna mentre si prepara l'implementazione di Teams, ma è possibile farlo in qualsiasi momento. Se sei abbastanza piccolo, potresti non aver bisogno di QoS.

Quando sei pronto, leggi Implementare la [qualità del servizio (QoS) in Microsoft Teams](QoS-in-Teams.md).

Per usare la QoS per gestire il traffico delle riunioni, leggere [Impostare la modalità di gestione del traffico multimediale in tempo reale per le riunioni di Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurare Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md)

[Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
