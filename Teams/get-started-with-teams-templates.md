---
title: Introduzione ai modelli di Teams con Microsoft Graph
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
description: Informazioni su come usare i modelli di Teams in Microsoft Graph per creare spazi di collaborazione con canali per diversi argomenti e preinstallare app per fornire contenuti e servizi.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772197"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Introduzione ai modelli di Teams con Microsoft Graph

> [!NOTE]
> I modelli di Teams attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni dei modelli.

I modelli di Teams sono definizioni predefinite della struttura di un team progettata in base a esigenze o progetti aziendali. È possibile [creare un modello personalizzato nella console di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md) Con Microsoft Graph si usano i modelli predefiniti. È possibile usare i modelli di Teams per creare rapidamente spazi di collaborazione con canali per diversi argomenti e preinstallare app per inserire contenuti e servizi cruciali. I modelli di Teams offrono una struttura di team predefinita che consente di creare facilmente team coerenti nell'organizzazione.

In questo articolo verranno illustrate le proprietà che possono essere definite nei modelli, quali sono i tipi di modello di base e come è possibile usare alcune richieste di esempio per creare un team da un modello.

Questo articolo contiene le informazioni seguenti:

- Responsabile della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione<br>
- Uno sviluppatore che vuole creare a livello di programmazione un team con canali e app predefiniti

## <a name="teams-template-capabilities"></a>Funzionalità dei modelli di Teams

La maggior parte delle proprietà in un team è inclusa e supportata dai modelli. Alcune proprietà e caratteristiche, tuttavia, non sono attualmente supportate. La tabella seguente contiene un breve riepilogo delle funzionalità incluse e di ciò che non è incluso nei modelli di Teams.

| **Proprietà del team supportate dai modelli di Teams** | **Proprietà del team non ancora supportate dai modelli di Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello di base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni del canale |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale preferito automaticamente | |
| App installata | |
| Schede bloccate | |

> [!NOTE]
> Aggiungeremo altre funzionalità di modello nelle versioni future di Microsoft Teams, quindi controlla di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Che cosa sono i tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per settori specifici. Questi modelli di base contengono spesso app proprietarie che non sono disponibili nello Store. Inoltre, i modelli di base spesso contengono proprietà del team non ancora supportate singolarmente nei modelli di Teams. Informazioni su come usare i modelli [di team in Microsoft Graph.](get-started-with-teams-templates.md)

Dopo aver definito un tipo di modello di base, è possibile estendere o sostituire questi modelli speciali con altre proprietà da specificare. Alcuni tipi di modello di base contengono proprietà che non è possibile modificare.

Per impostazione predefinita, il modello di base è impostato su **Standard,** che non contiene altre app proprietarie o proprietà speciali. Di seguito è riportato l'elenco corrente dei tipi di modello di base disponibili.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Non ci sono altre app e proprietà |
| Education -<br>Team di classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | App:<ul><li>Blocco appunti di OneNote per la classe (aggiunto **alla scheda** Generale) </li><li>App Attività (aggiunta alla **scheda** Generale)</li></ul> Proprietà del team:<ul><li>Visibilità del team impostata **su Membri nascosti** (non può essere sostituita)</li></ul> |
| Education -<br>Team del personale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | App:<ul><li>Blocco appunti di OneNote per personale degli altri membri (aggiunto **alla scheda** Generale)</li></ul> |
|Education -<br>Team PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | App:<ul><li>Blocco appunti PLC di OneNote (aggiunto alla **scheda** Generale)</ul></li>|
| Vendita al dettaglio -<br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canali:<ul><li>Maiusc handoff</li><li>Apprendimento</li></ul>Proprietà del team<ul><li>Visibilità del team impostata su Pubblico</li></ul>Autorizzazioni per i membri<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul> |
| Vendita al dettaglio -<br>Collaborazione con i manager | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canali:<ul><li>Apprendimento</li><li>Operazioni</li></ul>Proprietà del team:<ul><li>Visibilità del team impostata su Privato</li></ul>Autorizzazioni per i membri:<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul>|
| Sanità -<br>Snodato |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canali: <ul><li>Annunci\*</li><li>Huddles\*</li><li>Arrotondamenti</li><li>Personale\*</li><li>Formazione\*</li></ul>\*Canali preferiti automaticamente |
|Sanità -<br>Ospedale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canali:<ul><li>Annunci\*</li><li>Conformità\*</li><li>Responsabile</li><li>Risorse umane</li></li><li>Farmacia</li></ul>\*Canale preferito automaticamente|
|||


Usare i modelli seguenti per creare team sia nel client di Teams che in Microsoft Graph.


| Tipo di modello di base | baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo campioni</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li> |
| Gestire un progetto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gestire un evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e PR</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat per i dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li></ul>|
|Organizzare l'help desk| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborare all'assistenza pazienti| `healthcareWard `| Canali:<ul><li>Generale</li><li>Annunci</li><li>Huddles</li><li>Arrotondamenti</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li>|
| Collaborare in caso di emergenza o evento globale |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Lavoro remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Reclami dei clienti</li><li>Kudos</li><li>Aggiornamento della dirigenzia</li></ul>App: <ul><li>Complimento</li><li>Wiki</li><li>Sito Web</li></ul>|
|Collaborare all'interno di una filiale bancaria| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canali: <ul><li>Generale<li>Annunci</li><li>Huddles</li><li>Riunioni con i clienti</li><li>Snodato</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestito</li><li>Reclami dei clienti</li><li>Kudos</li><li>Cose divertenti</li><li>Conformità</li></ul>|
|Coordinare la risposta a un incidente| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Ripristino</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Programmazione</li></ul>|
|Ospedale| `healthcareHospita`l |Canali: <ul><li>Generale<li>Annunci</li><li>Conformità</li><li>Responsabile</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li></ul>|
|Organizzare uno store| `retailStore` |Canali: <ul><li>Generale<li>Maiusc handoff</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.`<br>`template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Riga 2</li><li>Riga 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li></ul>|
|Vendita al dettaglio - collaborazione con i manager| `retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

Per [altre informazioni, vedere Introduzione ai modelli di Teams nell'interfaccia](get-started-with-teams-templates-in-the-admin-console.md) di amministrazione.

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai modelli di Teams nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in anteprima)
- [Nuovo team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formazione per gli amministratori per Microsoft Teams](itadmin-readiness.md)