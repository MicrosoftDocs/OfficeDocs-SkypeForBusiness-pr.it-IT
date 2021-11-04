---
title: Monitorare e migliorare la qualità delle chiamate per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 86c1982e358f725d8965d8b6b5c4d43a01066584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60783151"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorare e migliorare la qualità delle chiamate per Microsoft Teams

Questo articolo presenta tre strumenti chiave che è possibile usare per monitorare, risolvere i problemi, gestire e migliorare la qualità delle chiamate Microsoft Teams. 

- **Call Quality Dashboard (CQD):** per analizzare le tendenze o i problemi a livello di organizzazione, è possibile migliorare le prestazioni

- **Analisi delle chiamate:** per analizzare la qualità delle chiamate e delle riunioni per i singoli utenti

- **Quality of Service (QoS):** per assegnare priorità al traffico di rete importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorare e risolvere i problemi relativi alla qualità delle chiamate
Userai l'analisi  delle chiamate per utente e il **dashboard** qualità chiamata per trovare e risolvere i problemi di qualità delle chiamate che si verificano durante il funzionamento in corso. In questo modo è possibile migliorare le prestazioni in tutta la rete. Entrambi questi strumenti sono disponibili nell'Teams di amministrazione.

 - **L'analisi** delle chiamate mostra informazioni dettagliate sui **** dispositivi, le reti e la connettività relativi a chiamate e riunioni specifiche per ogni utente in Teams. Teams di amministrazione e helpdesk useranno queste informazioni per risolvere i problemi di qualità delle chiamate e di connessione in una chiamata specifica. Per altre informazioni, vedere [Configurare l'analisi delle chiamate](set-up-call-analytics.md) e Usare Call Analytics per risolvere i problemi relativi alla scarsa qualità delle [chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Call Quality Dashboard (CQD)** offre una visualizzazione a livello di **_rete_** della qualità delle chiamate in tutta l'organizzazione. Usare le informazioni CQD per identificare e risolvere i problemi. Prima di [tutto, configurare CQD](turning-on-and-using-call-quality-dashboard.md). Leggere quindi [Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md).

 L'analisi delle chiamate e il CQD vengono eseguiti in parallelo e possono essere usati in modo indipendente o insieme. Ad esempio, se uno specialista del supporto delle comunicazioni determina che ha bisogno di ulteriore assistenza per la risoluzione del problema di chiamata di un utente, la chiamata viene inoltrata a un tecnico del supporto per le comunicazioni, che ha accesso ad altre informazioni sulla chiamata. A sua volta, il tecnico del supporto delle comunicazioni avvisa un tecnico di rete su un possibile problema relativo al sito che ha notato nell'analisi delle chiamate. Il tecnico di rete controlla CQD per verificare se un problema generale relativo al sito potrebbe essere una causa del problema di chiamata dell'utente.


## <a name="prioritize-important-network-traffic-using-qos"></a>Assegnare priorità al traffico di rete importante con QoS
Quando gli utenti iniziano a usare Teams per le chiamate e le riunioni, potrebbero verificarsi problemi di interruzione della voce del chiamante o interruzione di una chiamata o di una riunione. Il video condiviso può bloccarsi o pixelare o non riuscire del tutto. Questo è dovuto ai pacchetti IP che rappresentano il traffico vocale e video che incontrano congestione di rete e che arrivano fuori sequenza o non affatto. In questo caso o per evitare che ciò accada in primo luogo, usare **QoS (Quality of Service).** 

Con QoS, è possibile assegnare priorità al traffico di rete con ritardo sensibile( ad esempio, flussi vocali o video), consentendo di "tagliare in linea" davanti al traffico meno sensibile (ad esempio scaricare una nuova app, dove un secondo in più per il download non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale usando oggetti Criteri di gruppo di Windows e una funzionalità di routing denominata Elenchi di controllo di accesso basati su porta, che indica alla rete di fornire alla rete la propria larghezza di banda dedicata per la condivisione di video, video e vocali.

Idealmente, è possibile implementare QoS nella rete interna e prepararsi per la Teams, ma è possibile farlo in qualsiasi momento. Se si è abbastanza piccoli, potrebbe non essere necessario QoS.

Quando si è pronti, leggere Implementare la qualità [del servizio (QoS) in Microsoft Teams](QoS-in-Teams.md).

Per usare QoS per gestire il traffico delle riunioni, vedere Impostare la modalità di gestione del traffico multimediale in tempo reale per Teams [riunioni.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurare CQD](turning-on-and-using-call-quality-dashboard.md)

[Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
