---
title: Monitorare e migliorare la qualità delle chiamate per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Usa le impostazioni QoS (Quality of Service) e quindi Call Analytics e Call Quality Dashboard in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 107bbf867c410a556e02d76eb991cf5f04730efa
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46587633"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorare e migliorare la qualità delle chiamate per Microsoft Teams

Questo articolo presenta tre strumenti chiave che è possibile usare per monitorare, risolvere i problemi, gestire e migliorare la qualità delle chiamate in Microsoft Teams. 

- **Call Quality Dashboard (CQD):** per analizzare tendenze o problemi a livello di organizzazione, migliora le prestazioni

- **Analisi delle chiamate:** per analizzare la qualità delle chiamate e delle riunioni per singoli utenti

- **QoS (Quality of Service):** per assegnare priorità al traffico di rete importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorare e risolvere i problemi relativi alla qualità delle chiamate
Userai Call **Analytics** per utente e **Call Quality Dashboard** per trovare e risolvere i problemi di qualità delle chiamate che si verificano durante l'operazione in corso. In questo modo è possibile migliorare le prestazioni in tutta la rete. Entrambi questi strumenti si tratta dell'interfaccia di amministrazione di Teams.

 - **Call Analytics** mostra informazioni dettagliate su dispositivi, reti e connettività relative a specifiche chiamate e riunioni  ***per*** ogni utente in Teams. L'amministratore di Teams e gli agenti helpdesk useranno queste informazioni per risolvere i problemi di qualità delle chiamate e di connessione in una chiamata specifica. Per ulteriori informazioni, leggi [Configurare l'analisi delle chiamate](set-up-call-analytics.md) e usare Call Analytics per risolvere i problemi di bassa qualità delle [chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Call Quality Dashboard (CQD)** offre una visualizzazione ***a*** livello di rete della qualità delle chiamate in tutta l'organizzazione. Usare le informazioni di CQD per identificare e risolvere i problemi. Prima di [tutto, configura CQD.](turning-on-and-using-call-quality-dashboard.md) Leggere quindi [Gestire la qualità delle chiamate e delle riunioni in Teams.](quality-of-experience-review-guide.md)

 Call Analytics e CQD vengono eseguiti in parallelo e possono essere usati in modo indipendente o insieme. Ad esempio, se un esperto del supporto per le comunicazioni stabilisce che ha bisogno di ulteriore aiuto per risolvere il problema di chiamata di un utente, la chiamata viene inoltrata a un tecnico del supporto per le comunicazioni, che ha accesso ad altre informazioni sulla chiamata. A sua volta, il tecnico del supporto delle comunicazioni avvisa un tecnico di rete su un possibile problema relativo al sito che ha notato nei dati analitici delle chiamate. Il tecnico di rete verifica CQD per verificare se un problema generale relativo al sito potrebbe essere una causa del problema di chiamata dell'utente.


## <a name="prioritize-important-network-traffic-using-qos"></a>Assegnare priorità al traffico di rete importante con QoS
Quando gli utenti iniziano a usare Teams per le chiamate e le riunioni, possono sentire la rottura della voce di un chiamante o il taglio di una chiamata o di una riunione. Il video condiviso può bloccarsi o pixelarsi o non riuscire del tutto. Ciò è dovuto ai pacchetti IP che rappresentano il traffico voce e video che riscontrano congestione di rete e che non arrivano affatto dalla sequenza. In questo caso, o per impedire che si verifichi prima di tutto, usare **la qualità del servizio (QoS, Quality of Service).** 

Con QoS, l'utente assegna priorità al traffico di rete con ritardi sensibili (ad esempio, flussi vocali o video), consentendo di "tagliare in linea" di fronte al traffico meno sensibile (come il download di una nuova app, in cui un secondo aggiuntivo da scaricare non è un problema). La QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale utilizzando oggetti Criteri di gruppo di Windows e una funzionalità di routing denominata Elenchi di controllo dell'accesso basato su porta, che indica alla rete di fornire alla rete la propria larghezza di banda di rete dedicata per voce, video e condivisione dello schermo.

Idealmente, implementerai la QoS nella rete interna mentre ti prepari all'implementazione di Teams, ma puoi farlo in qualsiasi momento. Se si è abbastanza piccoli, la QoS potrebbe non essere necessaria.

Quando si è pronti, leggere [Implementare la qualità del servizio (QoS) in Microsoft Teams.](QoS-in-Teams.md)

Per usare QoS per gestire il traffico delle riunioni, leggere Impostare come si vuole gestire il traffico multimediale in tempo reale [per le riunioni di Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurare CQD](turning-on-and-using-call-quality-dashboard.md)

[Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

