---
title: Introduzione ai modelli di team con Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni sui modelli di team disponibili solo con Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991115"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introduzione ai modelli di team con Microsoft Graph

> [!NOTE]
> I modelli di team attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni dei modelli.

Un modello di team in Microsoft Teams è una definizione della struttura di un team progettata in base a un'esigenza aziendale o a un progetto. Con i modelli di team è possibile creare rapidamente e facilmente spazi di collaborazione con impostazioni, canali e app predefinite. I modelli di team consentono di distribuire team coerenti all'interno dell'organizzazione.

Con Microsoft Graph, si usano i modelli di team predefiniti inclusi in Teams per creare team. In questo articolo verranno trattate le proprietà che è possibile definire nei modelli e i modelli disponibili solo con Microsoft Graph.

Questo articolo è per te se sei:

- Responsabile della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione<br>
- Uno sviluppatore che vuole creare a livello di programmazione un team con canali e app predefiniti

## <a name="team-template-capabilities"></a>Funzionalità dei modelli di team

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli. Esistono però alcune proprietà e funzionalità attualmente non supportate. Ecco un breve riepilogo degli elementi inclusi e di ciò che non è incluso nei modelli di team.

| **Proprietà del team supportate dai modelli di team** | **Proprietà del team non ancora supportate dai modelli di team** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni dei canali |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale preferito automaticamente | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Nelle versioni future di Microsoft Teams verranno aggiunti altri modelli, quindi controllare di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="pre-built-templates"></a>Modelli predefiniti

I modelli di team predefiniti sono modelli creati per settori specifici. Ecco i modelli predefiniti disponibili solo con Microsoft Graph.

| Tipo di modello | TemplateId | Proprietà disponibili con questo modello |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Nessuna app e proprietà aggiuntive |
| Istruzione -<br>Team di classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | App:<ul><li>OneNote Blocco appunti per la classe (aggiunto alla **scheda** Generale) </li><li>App Attività (aggiunta alla **scheda** Generale)</li></ul> Proprietà del team:<ul><li>Visibilità del team impostata **su HiddenMembership** (non può essere sostituita)</li></ul> |
| Istruzione -<br>Team del personale | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | App:<ul><li>OneNote Blocco appunti per personale (aggiunto alla **scheda** Generale)</li></ul> |
|Istruzione -<br>Team PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | App:<ul><li>OneNote Blocco appunti PLC (aggiunto alla **scheda** Generale)</ul></li>|

> [!NOTE]
> Per un elenco dei modelli predefiniti che è possibile usare nel client di Teams e con Microsoft Graph, vedere Introduzione ai modelli di team nell'interfaccia di amministrazione [di Teams.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)
- [Nuovo team](/powershell/module/teams/New-Team?view=teams-ps)
