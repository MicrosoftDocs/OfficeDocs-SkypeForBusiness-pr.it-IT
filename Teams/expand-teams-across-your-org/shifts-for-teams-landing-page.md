---
title: Turni per Teams
description: Ottenere le indicazioni per l'amministratore necessarie per configurare e gestire turni, lo strumento di gestione della pianificazione, in Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592772"
---
# <a name="shifts-for-teams"></a>Turni per Teams

Turni, lo strumento di gestione della pianificazione in Teams, mantiene la forza lavoro in prima linea connessa e sincronizzata. È progettato per dispositivi mobili per la gestione e le comunicazioni di pianificazioni e comunicazioni veloci ed efficaci. Con i turni, i manager e i lavoratori in prima linea possono gestire facilmente le pianificazioni e tenersi in contatto.

I responsabili possono creare, aggiornare e gestire le pianificazioni dei turni per i loro team. Possono assegnare turni, aggiungere turni aperti e approvare le richieste di pianificazione dei dipendenti. I dipendenti possono visualizzare le pianificazioni del proprio team, impostare la disponibilità, richiedere di scambiare o offrire un turno, richiedere le ore di riposo e l'ora di ingresso e uscita.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Usare le risorse seguenti per configurare e gestire i turni nell'organizzazione.

## <a name="set-up-and-manage-shifts"></a>Configurare e gestire i turni

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Gestire i turni](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Informazioni su come gestire i turni per l'organizzazione.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Gestire i proprietari della pianificazione per la gestione dei turni](shifts/schedule-owner-for-shift-management.md)** Questa caratteristica consente di elevare le autorizzazioni di un membro del team a un proprietario della pianificazione senza rendere il dipendente proprietario del team.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Domande frequenti sui dati relativi ai turni](shifts/shifts-data-faq.md)** Informazioni sulla posizione in cui vengono archiviati i dati di Shifts e su altri argomenti relativi ai dati di Shifts, tra cui conservazione, recupero e crittografia.        |

## <a name="shifts-connectors"></a>Turni connettori

Se si usa un sistema WFM (Workforce Management) di terze parti per la pianificazione, è possibile eseguire l'integrazione direttamente con Turni tramite connettori turni gestiti e tramite API e SDK di Turni Graph con connettori Turni open source. Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni nel sistema WFM dall'interno dei turni.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Panoramica dei connettori turni](shifts/shifts-connectors.md)** Panoramica dei connettori Turni e del loro funzionamento. Informazioni sui connettori gestiti e open source disponibili e sui sistemi WFM supportati.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Connettori Managed Shifts](shifts/shifts-connectors.md#managed-shifts-connectors)** I connettori Managed Shifts, sviluppati in collaborazione con i nostri partner, sono ospitati e gestiti da noi o dai nostri partner. Per altre informazioni, vedere [connettore Microsoft Teams](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) turni per il connettore Blue Yonder e [Reflexis Shifts per](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams) Microsoft Teams.    |
|   | **[Usare la procedura guidata connettore Turni per connettere Turni a Blue Yonder Workforce Management](shifts/shifts-connector-wizard.md)** La procedura guidata connettore Turni nella interfaccia di amministrazione di Microsoft 365 consente di configurare rapidamente una connessione al sistema WFM. Attualmente, la procedura guidata supporta il connettore Teams Turni per Blue Yonder per integrare Turni con Blue Yonder Workforce Management.
|  | **[Usare PowerShell per connettere Turni a Blue Yonder Workforce Management](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Informazioni su come usare PowerShell per configurare una connessione a Blue Yonder Workforce Management tramite il connettore Teams Turni per Blue Yonder.         |
|   | **[Usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management](shifts/shifts-connector-powershell-manage.md)** Ottenere indicazioni su come usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management dopo la configurazione tramite la procedura guidata del connettore Turni o PowerShell.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Connettori Shifts open-source](/microsoftteams/platform/samples/shifts-wfm-connectors)** Informazioni su come usare connettori [open source](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) guidati dalla community per integrare il sistema Kronos o JDA WFM tramite LE API Graph Shifts e SDK.    |

## <a name="shifts-extensions"></a>Estensioni turni

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[SHIFT Graph API Shifts](/graph/api/resources/shift)** Graph API consentono di integrare i dati di Shifts con sistemi WFM (External Workforce Management). Si ha la flessibilità necessaria per creare esperienze di turni personalizzate nel back-end, offrendo agli utenti un'esperienza di front-end Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Turni + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** turni + Power Automate consente di prendere informazioni da Turni e creare flussi di lavoro personalizzati con altre app ed eseguire operazioni su larga scala. Automatizzare i processi chiave con poco o nessun codice. I trigger e i modelli supportano vari scenari, ad esempio l'abilitazione dell'approvazione automatica per le richieste di turno quando non è necessaria l'approvazione di un responsabile. |

## <a name="featured-training"></a>Formazione in primo piano

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Video: Che cos'è Turni?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Video: Creare una pianificazione turni](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Video: Gestire una pianificazione turni](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
