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
ms.openlocfilehash: a4759bc010367e6531a557e2a5ff951d1b613505
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598359"
---
# <a name="shifts-connectors"></a>Turni connettori

## <a name="overview"></a>Panoramica

I connettori Turni consentono di integrare Turni, lo strumento di gestione pianificare in Microsoft Teams, con il sistema di gestione della forza lavoro (WFM). Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni nel sistema WFM dall'interno di Turni.

La connessione del sistema WFM a Teams consente alla forza lavoro in prima linea di gestire le pianificazioni in modo più efficiente e semplifica i processi quotidiani per un maggiore coinvolgimento e produttività. I dipendenti in prima linea hanno un'unica posizione in cui pianificare, comunicare e collaborare per portare a termine il lavoro, ovunque e su qualsiasi dispositivo.

Questo articolo offre una panoramica dei connettori Turni e del loro funzionamento.

## <a name="how-shifts-connectors-work"></a>Funzionamento dei connettori Turni

I connettori sincronizzano pianificare dati tra il sistema WFM e Turni, trasformando le pianificazioni dell'organizzazione in Teams. Turni è il campo in cui i dipendenti in prima linea si impegnano per le loro esigenze di pianificazione. Il sistema WFM è il sistema di registrazione per regole aziendali, conformità e intelligence.

I dati fluiscono attraverso il connettore in entrambi i modi per garantire che le pianificazioni siano sempre aggiornate. Le pianificazioni nel sistema WFM vengono sincronizzate con Turni. Inoltre, le modifiche apportate alle pianificazioni in Turni vengono sincronizzate nuovamente con il sistema WFM in tempo reale. Come sistema di record, tutte le regole aziendali vengono applicate dal sistema WFM prima che i dati vengano salvati in Turni.

## <a name="managed-shifts-connectors"></a>Connettori Di turni gestiti

I connettori Managed Shifts sono connettori sviluppati in collaborazione con i partner. I connettori gestiti sono ospitati e gestiti da Microsoft o dai partner. Con i connettori gestiti, è necessaria solo una configurazione minima.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>connettore turni Microsoft Teams per la yonder blu
<a name="blue_yonder"> </a>

Il connettore Teams Turni per Blue Yonder è un'offerta di prima parte ospitata e gestita da Microsoft. Con questo connettore, è possibile integrare Turni con le versioni Blue Yonder Workforce Management (Blue Yonder WFM) 2020.3, 2021.1 o 2021.2 per gestire le pianificazioni e mantenerle aggiornate.  

> [!NOTE]
> Se si ha Blue Yonder WFM versione 2020.3 o 2021.1, applicare la patch 2020.3.0.4 o 2021.1.0.3. Questa patch risolve un problema per cui gli utenti ricevono un messaggio di errore persistente in Turni. Risolve anche un problema che impedisce agli utenti di aggiornare la loro disponibilità in Turni.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Screenshot che mostra una richiesta di scambio in Turni in un dispositivo mobile, richiedere l'approvazione in Teams sul desktop e un pianificare in WFM Blue Yonder." lightbox="../../media/shifts-connector-blue-yonder.png":::

I responsabili della prima linea possono:

- Pubblicare turni e pianificazioni in Blue Yonder WFM e visualizzarli in Turni.
- Creare, gestire e assegnare turni aperti in WFM Blue Yonder e visualizzarli in Turni.
- Assegnare turni aperti creati in WFM Blue Yonder in Turni.
- Creare, modificare ed eliminare permessi in WFM Blue Yonder e visualizzare in Turni.
- Visualizzare e approvare le richieste di pianificare dei lavoratori sia in Blue Yonder WFM che in Turni.
- Impostare e aggiornare la disponibilità dei lavoratori in WFM Blue Yonder e visualizzare in Turni.

Gli operatori in prima linea possono:

- Visualizzare i turni e le pianificazioni personali e del team in Turni.
- Richiedere permessi, aprire turni e scambiare turni in Turni.
- Impostare la disponibilità in Turni.

Le azioni seguenti non sono attualmente supportate:

- Aggiungere, modificare, eliminare, salvare o pubblicare turni in Turni.
- Aggiungere, modificare, eliminare, salvare o pubblicare permessi in Turni.
- Aggiungere, modificare, eliminare, salvare o pubblicare turni aperti in Turni.

Quando un responsabile o un lavoratore in prima linea prova a eseguire una di queste azioni in Turni, riceverà un messaggio per informarlo che l'azione non è supportata.

#### <a name="example-scenario"></a>Scenario di esempio

Eden, un responsabile, pubblica un pianificare in Blue Yonder WFM, sincronizzato con Turni in Teams attraverso il connettore. Pio, membro del personale, riceve una notifica in Teams sul suo dispositivo mobile e visualizza i pianificare e i turni assegnati.

Alex deve prendersi un po' di tempo libero e richiede un giorno libero tramite Turni. La richiesta viene inviata a Blue Yonder WFM attraverso il connettore in tempo reale. Blue Yonder WFM garantisce che la richiesta sia conforme alle regole aziendali e che la richiesta venga creata. Eden vede e approva la richiesta in Blue Yonder WFM e l'approvazione viene sincronizzata con Teams. Eden può anche visualizzare e approvare la richiesta in Turni. Pio riceve una notifica in Teams che la sua richiesta è approvata e visualizza il suo pianificare aggiornato.

Pio vuole scambiare un turno con un collega. In Turni Alex visualizza un elenco di tutti i turni idonei per uno scambio basato sulle regole aziendali in Blue Yonder WFM. Pio sceglie un turno attualmente assegnato a Gena. Gena riceve una notifica in Teams sul dispositivo mobile e accetta la richiesta di scambio. Eden vede e approva la richiesta in Turni e l'approvazione viene sincronizzata con Blue Yonder WFM. (Eden può anche visualizzare e approvare la richiesta in Blue Yonder WFM). Pio e Gena ricevono una notifica in Teams e visualizzano le pianificazioni aggiornate.

#### <a name="set-up-a-connection"></a>Configurare una connessione

L'integrazione di Turni con Blue Yonder WFM con il connettore richiede solo pochi passaggi. È possibile usare la procedura guidata connettore Turni nel interfaccia di amministrazione di Microsoft 365 per configurare rapidamente una connessione. La procedura guidata configura il connettore in base alle impostazioni scelte e crea la connessione. Se si preferisce usare PowerShell, vengono forniti anche script di PowerShell che è possibile usare per connettersi.

Per indicazioni dettagliate, vedere:

- [Usare la procedura guidata connettore Turni per connettere Turni alla gestione della forza lavoro Blue Yonder](shifts-connector-wizard.md)
- [Usare PowerShell per connettere Turni alla gestione della forza lavoro Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)

Dopo aver configurato una connessione, è possibile usare PowerShell per aggiornare e modificare le impostazioni di connessione in qualsiasi momento, in base alle esigenze. Per quanto riguarda il connettore stesso, non è necessario preoccuparsi di aggiornamenti o manutenzione. Ci prendiamo cura di questo.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connettore Reflexis Turni per Microsoft Teams

Il connettore Reflexis Shifts per Microsoft Teams è ospitato e gestito da Zebra. Con questo connettore, è possibile integrare Turni con il sistema Reflexis WFM per gestire le pianificazioni e mantenerle aggiornate.

I dipendenti in prima linea hanno accesso ai loro pianificare in Turni in Teams e le loro richieste vengono sincronizzate da Turni a Reflexis Workforce Scheduler (RWS). Lo stato delle richieste e dei turni creati in RWS viene sincronizzato con Turni in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot che mostra l'elenco dei turni in un dispositivo mobile e un pianificare in Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

I responsabili della prima linea possono:

- Pubblicare turni e pianificazioni in Reflexis e visualizzarli in Turni.
- Modificare i turni sia in Reflexis che in Turni.
- Creare, gestire e assegnare turni aperti sia in Reflexis che in Turni.
- Visualizzare e approvare le richieste di pianificare da parte dei lavoratori sia in Reflexis che in Turni.

Gli operatori in prima linea possono:

- Visualizzare i turni e le pianificazioni personali e del team in Turni.
- Richiedere permessi, aprire turni e scambiare e offrire turni in Turni.

Per ulteriori informazioni, vai a https://connect.zebra.com/microsoft-connectors.

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
