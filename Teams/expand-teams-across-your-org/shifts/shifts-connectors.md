---
title: Turni connettori
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sui connettori Turni e su come usarli per connettere Turni al sistema di gestione della forza lavoro.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192487"
---
# <a name="shifts-connectors"></a>Turni connettori

## <a name="overview"></a>Panoramica

I connettori turni consentono di integrare Turni, lo strumento di gestione della pianificazione in Microsoft Teams, con il sistema WFM (Workforce Management). Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni nel sistema WFM dall'interno dei turni.

La connessione del sistema WFM a Teams consente alla forza lavoro in prima linea di gestire le pianificazioni in modo più efficace e semplifica i processi quotidiani per aumentare l'impegno e la produttività. I dipendenti in prima linea hanno un'unica posizione in cui pianificare, comunicare e collaborare per lavorare, ovunque e su qualsiasi dispositivo.

Sono disponibili connettori Shifts gestiti e open source. Questo articolo offre una panoramica dei connettori Turni e del loro funzionamento.

## <a name="how-shifts-connectors-work"></a>Funzionamento dei connettori Shifts

I connettori sincronizzano i dati della pianificazione tra il sistema WFM e i turni, portando le pianificazioni dell'organizzazione in Teams. I turni sono i turni in cui i dipendenti in prima linea si impegnano per soddisfare le loro esigenze di programmazione. Il sistema WFM è il sistema di record per le regole aziendali, la conformità e l'intelligence.

I flussi di dati tramite il connettore in entrambi i modi assicurano che le pianificazioni siano sempre aggiornate. Le pianificazioni nel sistema WFM vengono sincronizzate con turni. Inoltre, le modifiche apportate alle pianificazioni in Turni vengono sincronizzate di nuovo con il sistema WFM in tempo reale. Come sistema di record, tutte le regole business vengono applicate dal sistema WFM prima che i dati vengano salvati in Turni.

## <a name="managed-shifts-connectors"></a>Connettori Managed Shifts

I connettori Managed Shifts sono connettori sviluppati in collaborazione con i partner. I connettori gestiti sono ospitati e gestiti da noi o dai nostri partner. Con i connettori gestiti è necessaria solo una configurazione minima.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connettore Reflexis Shifts per Microsoft Teams

Il connettore Reflexis Shifts per Microsoft Teams è ospitato e gestito da Zebra. Con questo connettore è possibile integrare Turni con il sistema Reflexis WFM per gestire le pianificazioni e mantenerle aggiornate.

I lavoratori in prima linea hanno accesso alla loro pianificazione in Turni in Teams e le loro richieste vengono sincronizzate da Turni a Reflexis Workforce Scheduler (RWS). Lo stato delle richieste e dei turni creati in RWS viene sincronizzato con turni in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot che mostra l'elenco dei turni in un dispositivo mobile e una pianificazione in Reflexis" lightbox="../../media/shifts-connector-reflexis.png":::

I responsabili in prima linea possono:

- Pubblicare turni e pianificazioni in Reflexis e visualizzarli in Turni.
- Modificare i turni sia in Reflexis che in Shifts.
- Creare, gestire e assegnare turni aperti sia in Reflexis che in Turni.
- Visualizzare e approvare le richieste di pianificazione dei lavoratori sia in Reflexis che nei turni.

I lavoratori in prima linea possono:

- Visualizzare i turni e le pianificazioni del proprio team in Turni.
- Richiedere un periodo di riposo, aprire turni e scambiare e offrire turni nei turni.

Per altre informazioni, vedere https://connect.zebra.com/microsoft-connectors .

## <a name="open-source-shifts-connectors"></a>Connettori Shifts open-source

I connettori Shifts open-source sono integrazioni guidate dalla community create su [SHIFTs Graph API](/graph/api/resources/shift). Sono disponibili i connettori open source seguenti:

- Kronos-to-Teams WFC locale
- Connettore JDA-to-Teams Shifts (per Blue Yonder versione 2017-2020.2)

Ogni connettore include istruzioni dettagliate per la distribuzione e la configurazione. Includono script di distribuzione di Azure Resource Manager (ARM) che consentono di ospitare tutti i servizi necessari in Microsoft Azure. Il codice sorgente e gli script di distribuzione sono disponibili per il download in [GitHub repository.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) È possibile eseguire la distribuzione così come è oppure personalizzarla o estenderla in base alle proprie esigenze.

Per altre informazioni, vedere [Connettori turni](/microsoftteams/platform/samples/shifts-wfm-connectors)pronti per la produzione.

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
