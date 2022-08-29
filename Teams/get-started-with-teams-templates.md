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
- m365-frontline
description: Informazioni sui modelli di team disponibili solo con Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397237"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introduzione ai modelli di team con Microsoft Graph

> [!NOTE]
> I modelli di team attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni dei modelli.

Un modello di team in Microsoft Teams è una definizione della struttura di un team progettata in base a un'esigenza aziendale o a un progetto. I modelli di team consentono di creare rapidamente e facilmente spazi di collaborazione avanzati con impostazioni, canali e app predefiniti. I modelli di team possono essere utili per distribuire team coerenti all'interno dell'organizzazione.

Con Microsoft Graph, è possibile [creare modelli personalizzati](/graph/api/resources/teamtemplate?view=graph-rest-beta) o usare i modelli di team predefiniti inclusi in Teams per creare team. In questo articolo vengono fornite informazioni sulle proprietà che possono essere definite nei modelli e sui modelli predefiniti disponibili solo con Microsoft Graph.

Questo articolo contiene le informazioni seguenti:

- Responsabile della pianificazione, distribuzione e gestione di più team all'interno dell'organizzazione<br>
- Uno sviluppatore che vuole creare un team a livello di programmazione con canali e app predefiniti

## <a name="team-template-capabilities"></a>Funzionalità dei modelli di team

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli. Tuttavia, alcune proprietà e funzionalità non sono attualmente supportate. Ecco un breve riepilogo delle funzionalità incluse e di ciò che non è incluso nei modelli di team.

| **Proprietà del team supportate dai modelli di team** | **Proprietà del team non ancora supportate dai modelli di team** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni del canale |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio membro, guest, @menzioni) | File e contenuti |
| Canale preferito automaticamente | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Aggiungeremo altre funzionalità di modello nelle versioni future di Microsoft Teams, quindi ricontrollare per le informazioni più aggiornate sulle proprietà supportate.

## <a name="pre-built-templates"></a>Modelli predefiniti

I modelli di team predefiniti sono modelli creati per settori specifici. Ecco i modelli predefiniti disponibili solo con Microsoft Graph.

| Tipo di modello | TemplateId | Proprietà del modello |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Nessuna app e proprietà aggiuntive |
| Istruzione -<br>Team di classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | App:<ul><li>Blocco appunti di OneNote per la classe (aggiunto alla scheda **Generale** ) </li><li>App Attività (aggiunta alla scheda **Generale** )</li></ul> Proprietà del team:<ul><li>Visibilità del team impostata su **HiddenMembership** (non può essere sostituita)</li></ul> |
| Istruzione -<br>Team del personale | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | App:<ul><li>Blocco appunti di OneNote per personale degli utenti (aggiunto alla scheda **Generale** )</li></ul> |
|Istruzione -<br>Team PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | App:<ul><li>Blocco appunti PLC di OneNote (aggiunto alla scheda **Generale** )</ul></li>|

> [!NOTE]
> Per un elenco dei modelli predefiniti che è possibile usare nel client di Teams e con Microsoft Graph, vedere [Introduzione ai modelli di team nell'interfaccia di amministrazione di Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)
- [Nuovo team](/powershell/module/teams/New-Team?view=teams-ps)
