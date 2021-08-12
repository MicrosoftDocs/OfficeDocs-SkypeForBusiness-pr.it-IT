---
title: Monitorare e ottimizzare la qualità delle chiamate per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Usa le impostazioni QoS (Quality of Service) e quindi Analisi delle chiamate e Dashboard qualità chiamata in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286265"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorare e ottimizzare la qualità delle chiamate per Microsoft Teams

In questo articolo vengono presentati tre strumenti chiave che è possibile utilizzare per monitorare, risolvere i problemi, gestire e migliorare la qualità delle chiamate in Microsoft Teams. 

- **Call Quality Dashboard (CQD):** per analizzare le tendenze o i problemi a livello di organizzazione, migliorare le prestazioni

- **Analisi delle chiamate:** per analizzare la qualità delle chiamate e delle riunioni per i singoli utenti

- **Qualità del servizio (QoS):** per definire le priorità del traffico di rete importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorare e risolvere i problemi relativi alla qualità delle chiamate
Userai l'analisi  delle chiamate per utente e il **dashboard** qualità delle chiamate per trovare e risolvere i problemi di qualità delle chiamate che si verificano durante il funzionamento in corso. In questo modo è possibile migliorare le prestazioni in tutta la rete. Entrambi questi strumenti si Teams'interfaccia di amministrazione.

 - **L'analisi** delle chiamate mostra informazioni dettagliate sui dispositivi, le reti e la connettività correlati a chiamate e riunioni specifiche **_per_** ogni utente in Teams. Teams amministratori e helpdesk utilizzeranno queste informazioni per risolvere i problemi di qualità delle chiamate e di connessione in una chiamata specifica. Per ulteriori informazioni, vedere [Configurare l'analisi delle chiamate](set-up-call-analytics.md) e Usare Analisi chiamate per risolvere i problemi relativi alla qualità delle chiamate di qualità [scarsa.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Call Quality Dashboard (CQD)** offre una visione **_a_** livello di rete della qualità delle chiamate all'interno dell'organizzazione. Usare le informazioni CQD per identificare e risolvere i problemi. Prima di [tutto, configurare CQD](turning-on-and-using-call-quality-dashboard.md). Leggere quindi [Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md).

 L'analisi delle chiamate e il CQD vengono eseguiti in parallelo e possono essere usati in modo indipendente o insieme. Ad esempio, se uno specialista del supporto per le comunicazioni determina di avere bisogno di ulteriore assistenza per la risoluzione del problema di chiamata di un utente, la chiamata viene inoltrata a un tecnico del supporto per le comunicazioni, che ha accesso a ulteriori informazioni sulla chiamata. A sua volta, il tecnico del supporto delle comunicazioni avvisa un tecnico di rete di un possibile problema relativo al sito rilevato nell'analisi delle chiamate. Il tecnico di rete controlla CQD per verificare se un problema generale relativo al sito potrebbe essere una causa del problema di chiamata dell'utente.


## <a name="prioritize-important-network-traffic-using-qos"></a>Assegnare priorità al traffico di rete importante tramite QoS
Quando gli utenti iniziano a Teams per le chiamate e le riunioni, possono verificarsi problemi di interruzione o interruzione della voce di un chiamante o di una chiamata o di una riunione. Il video condiviso può bloccarsi o pixelare o non riuscire del tutto. Ciò è dovuto ai pacchetti IP che rappresentano il traffico vocale e video che incontra la congestione della rete e arrivano fuori sequenza o non affatto. In questo caso o per evitare che ciò accada in primo luogo, utilizzare **QoS (Quality of Service).** 

Con QoS, definisci la priorità del traffico di rete sensibile al ritardo (ad esempio, flussi vocali o video), consentendo di "tagliare in linea" davanti al traffico meno sensibile (ad esempio, scaricare una nuova app, dove un secondo in più per il download non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale utilizzando oggetti Criteri di gruppo di Windows e una funzionalità di routing denominata Elenchi di controllo di accesso basati su porta, che indica alla rete di fornire alla rete la condivisione vocale, video e dello schermo della propria larghezza di banda di rete dedicata.

Idealmente, è possibile implementare QoS nella rete interna e prepararsi per l'implementazione Teams, ma è possibile farlo in qualsiasi momento. Se si è abbastanza piccoli, potrebbe non essere necessario QoS.

Quando si è pronti, leggere Implementare la qualità [del servizio (QoS) in Microsoft Teams](QoS-in-Teams.md).

Per utilizzare QoS per gestire il traffico delle riunioni, leggere Impostare la modalità di gestione del traffico multimediale in tempo reale per Teams [riunioni.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurare CQD](turning-on-and-using-call-quality-dashboard.md)

[Gestire la qualità delle chiamate e delle riunioni in Teams](quality-of-experience-review-guide.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)