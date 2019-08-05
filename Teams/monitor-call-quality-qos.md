---
title: Implementare QoS e monitorare le analisi delle chiamate in Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: Usare le impostazioni QoS (Quality of Service) e quindi chiamare Analytics e Call Quality dashboard in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181246"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementare QoS e monitorare la qualità delle chiamate in Microsoft Teams

## <a name="get-started"></a>Per iniziare

Man mano che gli utenti iniziano a usare team per effettuare chiamate e organizzare riunioni, possono verificare che la voce di un chiamante si rompa o tagli dentro e fuori una chiamata o una riunione. Il video condiviso può bloccare o pixelare o non completamente. Ciò è dovuto ai pacchetti IP che rappresentano il traffico vocale e video che incontrano la congestione della rete e che arrivano fuori sequenza o per niente. Esistono diversi modi per identificare questi problemi quando emergono e ne impediscono il ritorno, soprattutto la qualità del servizio (QoS).

La **qualità del servizio (QoS)** è un modo per consentire il traffico di rete in tempo reale (come i flussi di voce o video) che è sensibile ai ritardi di rete per "tagliare in linea" davanti al traffico meno sensibile (come scaricare una nuova app, in cui è possibile scaricare un secondo extra non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale usando gli oggetti Criteri di gruppo di Windows e una caratteristica di routing denominata elenchi di controllo di accesso basati su porta, che consente quindi alla rete di fornire ai flussi di condivisione di voce, video e schermo le proprie parti dedicate di larghezza di banda della rete.

 Per il momento, dobbiamo solo dire che è molto simile all'invio di una lettera tramite posta elettronica: se si invia il tasso di prenotazione viene visualizzato molto presto e questo è abbastanza buono, se si invia prima classe diventa molto più veloce e se si invia la posta prioritaria , arriva entro due giorni. Naturalmente, le reti corrono più velocemente della posta, ma è comunque vero che la velocità è fondamentale per alcune applicazioni e non è così critica per gli altri. Questo argomento è intrinsecamente dettagliato e difficile da comprendere all'inizio, ma fa una grande differenza nell'esperienza utente, quindi vale la pena investire tempo ed energia in anticipo. Leggere [implementare la qualità del servizio (QoS) in Microsoft teams](QoS-in-Teams.md) per una discussione più dettagliata.

In teoria, è possibile implementare QoS nella rete interna durante la configurazione dei team, ma se si è abbastanza piccoli può essere facoltativo. In questo modo, il traffico vocale e video sensibile al ritardo viene assegnato prima di tutto al traffico. Questa priorità viene eseguita su tutti i [dispositivi client](QoS-in-Teams-clients.md), nell'interfaccia di [amministrazione di Microsoft teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), nonché sugli switch e i router della rete.

Per trovare e risolvere i problemi che si verificano durante l'operazione in corso, vengono usati i [**comandi per le chiamate e**](difference-between-call-analytics-and-call-quality-dashboard.md) per la qualità delle chiamate.  

**Chiamata analitica** Mostra informazioni dettagliate sui dispositivi, le reti e la connettività relativi a ***chiamate e riunioni specifiche*** per ogni utente in un account Microsoft teams o Skype for business. Se si è un amministratore di Office 365, è possibile usare la funzione di analisi delle chiamate per risolvere i problemi di connessione e la qualità delle chiamate con una chiamata specifica. Questo può aiutare a identificare ed eliminare i problemi.

**Call Quality Dashboard (Call Quality Dashboard)** è progettato per aiutare gli amministratori e gli ingegneri di rete a ottimizzare la propria ***rete***, non analizzare e risolvere i problemi di una singola chiamata. Call Quality dashboard sposta lo stato attiva da utenti specifici per esaminare le informazioni aggregate per un'intera organizzazione. Questo può anche aiutare a identificare ed eliminare i problemi.

## <a name="related-topics"></a>Argomenti correlati

[Implementare la qualità del servizio (QoS) in Microsoft Teams](QoS-in-Teams.md)

[Video: panoramica sulla qualità delle chiamate](https://aka.ms/teams-quality)

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Attivazione e utilizzo di Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md)

[Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso nel Dashboard Qualità della chiamata](stream-classification-in-call-quality-dashboard.md)