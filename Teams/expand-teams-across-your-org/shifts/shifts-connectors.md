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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592891"
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

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Connettore Turni per Blue Yonder
<a name="blue_yonder"> </a>

Il connettore Teams Turni per Blue Yonder è un'offerta di prima parte ospitata e gestita da Microsoft. Con questo connettore è possibile integrare Turni con Blue Yonder Workforce Management (Blue Yonder WFM) versioni 2020.3, 2021.1 o 2021.2 per gestire le pianificazioni e mantenerle aggiornate.  

> [!NOTE]
> Se si ha Blue Yonder WFM versione 2020.3 o 2021.1, applicare la patch 2020.3.0.4 o 2021.1.0.3. Questa patch risolve un problema per cui gli utenti ottengono un messaggio di errore persistente in Turni. Risolve anche un problema che impedisce agli utenti di aggiornare la disponibilità in Turni.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Screenshot che mostra una richiesta di scambio in Turni in un dispositivo mobile, la richiesta di approvazione in Teams sul desktop e una pianificazione in Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

I responsabili in prima linea possono:

- Pubblicare turni e pianificazioni in Blue Yonder WFM e visualizzarli in Turni.
- Creare, gestire e assegnare turni aperti in Blue Yonder WFM e visualizzarli in Turni.
- Assegnare turni aperti creati in Blue Yonder WFM in Turni.
- Creare, modificare ed eliminare un periodo di riposo in Blue Yonder WFM e visualizzarlo in Turni.
- Visualizzare e approvare le richieste di pianificazione dei lavoratori sia in Blue Yonder WFM che nei turni.
- Impostare e aggiornare la disponibilità dei lavoratori in Blue Yonder WFM e visualizzare in Turni.

I lavoratori in prima linea possono:

- Visualizzare i turni e le pianificazioni del proprio team in Turni.
- Richiedere un periodo di riposo, aprire turni e scambiare turni in turni.
- Impostare la disponibilità in Turni.

Le azioni seguenti non sono attualmente supportate:

- Aggiungere, modificare, eliminare, salvare o pubblicare turni in turni.
- Aggiungere, modificare, eliminare, salvare o pubblicare un periodo di riposo in Turni.
- Aggiungere, modificare, eliminare, salvare o pubblicare turni aperti in Turni.

Quando un manager o un operaio in prima linea prova a eseguire una di queste azioni in Turni, riceverà un messaggio per insod che l'azione non è supportata.

#### <a name="example-scenario"></a>Scenario di esempio

Eden, un manager, pubblica una pianificazione in Blue Yonder WFM, che viene sincronizzata con Turni Teams tramite il connettore. Alex, un membro del personale, riceve una notifica Teams sul suo dispositivo mobile e visualizza la pianificazione e i turni assegnati.

Alex deve prendersi un po' di tempo libero e richiede un giorno di riposo con Turni. La richiesta viene inviata a Blue Yonder WFM tramite il connettore in tempo reale. Blue Yonder WFM assicura che la richiesta sia conforme alle regole di business e la richiesta viene creata. Eden vede e approva la richiesta in Blue Yonder WFM e l'approvazione viene sincronizzata con Teams. (Eden può anche vedere e approvare la richiesta in Turni). Alex viene avvisato in Teams che la sua richiesta è stata approvata e visualizza la pianificazione aggiornata.

Alex vuole scambiare un turno con un collega. In Turni, Alex visualizza un elenco di tutti i turni idonei per uno scambio in base alle regole aziendali in Blue Yonder WFM. Alex sceglie un turno attualmente assegnato a Gena. Gena viene avvisato in Teams sul dispositivo mobile e accetta la richiesta di scambio. Eden vede e approva la richiesta in Turni e l'approvazione viene sincronizzata con Blue Yonder WFM. (Eden può anche vedere e approvare la richiesta in Blue Yonder WFM). Alex e Gena vengono avvisati in Teams e visualizzano le pianificazioni aggiornate.

#### <a name="set-up-a-connection"></a>Configurare una connessione

L'integrazione di Turni con Blue Yonder WFM con il connettore richiede solo pochi passaggi. È possibile usare la procedura guidata connettore Turni nella interfaccia di amministrazione di Microsoft 365 per configurare rapidamente una connessione. La procedura guidata configura il connettore in base alle impostazioni selezionate e crea la connessione. Se si preferisce usare PowerShell, sono disponibili anche script di PowerShell che è possibile usare per la connessione.

Per istruzioni dettagliate, vedere:

- [Usare la procedura guidata connettore Turni per connettere Turni a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usare PowerShell per connettere Turni a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Dopo aver configurato una connessione, è possibile usare PowerShell per aggiornare e modificare le impostazioni di connessione in qualsiasi momento, in base alle esigenze. Per quanto riguarda il connettore stesso, non è necessario preoccuparsi di aggiornamenti o manutenzione. Ci occupiamo di questo.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connettore Reflexis Shifts per Microsoft Teams

Il connettore Reflexis Shifts per Microsoft Teams è ospitato e gestito da Zebra. Con questo connettore è possibile integrare Turni con il sistema Reflexis WFM per gestire le pianificazioni e mantenerle aggiornate.

I lavoratori in prima linea hanno accesso alla loro pianificazione in Turni in Teams e le loro richieste vengono sincronizzate da Turni a Reflexis Workforce Scheduler (RWS). Lo stato delle richieste e dei turni creati in RWS viene sincronizzato con turni in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot che mostra l'elenco dei turni in un dispositivo mobile e una pianificazione in Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

I responsabili in prima linea possono:

- Pubblicare turni e pianificazioni in Reflexis e visualizzarli in Turni.
- Modificare i turni sia in Reflexis che in Shifts.
- Creare, gestire e assegnare turni aperti sia in Reflexis che in Turni.
- Visualizzare e approvare le richieste di pianificazione dei lavoratori sia in Reflexis che nei turni.

I lavoratori in prima linea possono:

- Visualizzare i turni e le pianificazioni del proprio team in Turni.
- Richiedere un periodo di riposo, aprire turni e scambiare e offrire turni nei turni.

Per altre informazioni, vedere https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Connettori Shifts open-source

I connettori Turni open-source sono integrazioni guidate dalla community, create su [SHIFTs Graph API](/graph/api/resources/shift). Sono disponibili i connettori open source seguenti:

- Kronos-to-Teams WFC locale
- Connettore JDA-to-Teams Shifts (per Blue Yonder versione 2017-2020.2)

Ogni connettore include istruzioni dettagliate per la distribuzione e la configurazione. Includono script di distribuzione di Azure Resource Manager (ARM) che consentono di ospitare tutti i servizi necessari in Microsoft Azure. Il codice sorgente e gli script di distribuzione sono disponibili per il download in GitHub [repository](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). È possibile eseguire la distribuzione così come è oppure personalizzarla o estenderla in base alle proprie esigenze.

Per altre informazioni, vedere [Connettori turni pronti per la produzione](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
