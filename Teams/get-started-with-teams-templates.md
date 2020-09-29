---
title: Iniziare a usare i modelli di teams usando Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare i modelli di teams in Microsoft Graph per creare spazi di collaborazione con canali per diversi argomenti e per preinstallare app per la fornitura di contenuti e servizi.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee4ab53318766b8daaeea225f8c039e32c8c4241
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294602"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Iniziare a usare i modelli di teams usando Microsoft Graph

> [!NOTE]
> I modelli di teams attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni di modello.

I modelli di teams sono definizioni predefinite della struttura di un team progettate attorno a un progetto o una necessità aziendale. È possibile [creare un modello personalizzato nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md). Con Microsoft Graph si usano i modelli predefiniti. Puoi usare i modelli teams per creare rapidamente spazi di collaborazione avanzati con canali per diversi argomenti e per preinstallare app per il pull in contenuti e servizi mission-critical. I modelli teams offrono una struttura del team predefinita che consente di creare facilmente team coerenti nell'organizzazione.

In questo articolo vengono illustrate le proprietà che è possibile definire nei modelli, quali tipi di modello di base sono e come è possibile usare alcuni esempi di richieste per creare un team da un modello.

Questo articolo è per te se sei:

- Responsabile per la pianificazione, la distribuzione e la gestione di più team in tutta l'organizzazione<br>
- Uno sviluppatore che vuole creare a livello di codice un team con canali e app predefiniti

## <a name="teams-template-capabilities"></a>Funzionalità del modello Teams

La maggior parte delle proprietà di un team è inclusa e supportata dai modelli. Tuttavia, esistono alcune proprietà e funzionalità che non sono attualmente supportate. La tabella seguente fornisce un breve riepilogo degli elementi inclusi e dei modelli di team non inclusi.

| **Proprietà del team supportate dai modelli di Teams** | **Proprietà del team non ancora supportate dai modelli di Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello di base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni canale |
| Visibilità del team (pubblico o privato) | Connettori |
| Impostazioni del team (ad esempio, membro, Guest, @ menzioni) | File e contenuti |
| Canale di auto-Preferiti | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Aggiungeremo altre funzionalità modello nelle versioni future di Microsoft teams, quindi controlla le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Informazioni sui tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per settori specifici. Questi modelli di base contengono spesso app proprietarie che non sono disponibili nello Store. I modelli di base, inoltre, contengono spesso proprietà del team che non sono ancora supportate individualmente nei modelli di teams. Informazioni su come usare i [modelli di team in Microsoft Graph](get-started-with-teams-templates.md).

Una volta definito un tipo di modello di base, è possibile estendere o sostituire questi modelli speciali con altre proprietà che si desidera specificare. Alcuni tipi di modello di base contengono proprietà che non è possibile eseguire l'override.

Per impostazione predefinita, il modello di base è impostato su **standard**, che non contiene altre app proprietarie o proprietà speciali. Di seguito è riportato l'elenco corrente dei tipi di modello di base disponibili.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Nessuna app e proprietà aggiuntive |
| Istruzione<br>Team di classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Applicazioni<ul><li>Blocco appunti di OneNote per la classe (aggiunto alla scheda **generale** ) </li><li>App assegnazioni (aggiunta alla scheda **generale** )</li></ul> Proprietà del team:<ul><li>Visibilità del team impostata su **HiddenMembership** (non è possibile eseguire l'override)</li></ul> |
| Istruzione<br>Team del personale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Applicazioni<ul><li>Blocco appunti del personale di OneNote (aggiunto alla scheda **generale** )</li></ul> |
|Istruzione<br>Team PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Applicazioni<ul><li>Blocco appunti di OneNote PLC (aggiunto alla scheda **generale** )</ul></li>|
| Negozio<br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canali<ul><li>Cambio di consegna</li><li>Apprendimento</li></ul>Proprietà del team<ul><li>Visibilità del team impostata su pubblico</li></ul>Autorizzazioni per i membri<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul> |
| Negozio<br>Collaborazione con i Manager | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canali<ul><li>Cambio di consegna</li><li>Apprendimento</li></ul>Proprietà del team:<ul><li>Visibilità del team impostata su privato</li></ul>Autorizzazioni per i membri:<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul>|
| Assistenza sanitaria<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canali <ul><li>Annunci\*</li><li>Huddles\*</li><li>Arrotonda</li><li>Personale\*</li><li>Formazione\*</li></ul>\*Canali preferiti automaticamente |
|Assistenza sanitaria<br>Ospedale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canali<ul><li>Annunci\*</li><li>Conformità\*</li><li>Custodia</li><li>Risorse umane</li></li><li>Farmacia</li></ul>\*Canale con il favorito automatico|
|||

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai modelli di teams nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Crea team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in anteprima)
- [Nuovo team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formazione per amministratori per Microsoft Teams](itadmin-readiness.md)