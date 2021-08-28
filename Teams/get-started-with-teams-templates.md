---
title: Introduzione ai modelli di team con Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare i modelli di team in Microsoft Graph creare spazi di collaborazione con canali per diversi argomenti e app di preinstallazione per fornire contenuti e servizi.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8005d17debce7a0187ac8411a8054071c754566
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599741"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introduzione ai modelli di team con Microsoft Graph

> [!NOTE]
> I modelli di team attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni dei modelli.

I modelli di team sono definizioni predefinite della struttura di un team progettate in base a un'esigenza aziendale o a un progetto. È possibile [creare un modello personalizzato nella console di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md) Con Microsoft Graph, si usano i modelli predefiniti. È possibile usare i modelli di team per creare rapidamente spazi di collaborazione avanzati con canali per diversi argomenti e app di preinstallazione per inserire contenuti e servizi mission-critical. I modelli di team offrono una struttura predefinita del team che consente di creare facilmente team coerenti in tutta l'organizzazione.

In questo articolo verranno illustrate le proprietà che è possibile definire nei modelli, quali sono i tipi di modello di base e come è possibile usare alcune richieste di esempio per creare un team da un modello.

Questo articolo è per te se sei:

- Responsabile della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione<br>
- Uno sviluppatore che vuole creare a livello di programmazione un team con canali e app predefiniti

## <a name="team-template-capabilities"></a>Funzionalità dei modelli di team

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli. Esistono però alcune proprietà e funzionalità attualmente non supportate. La tabella seguente fornisce un breve riepilogo degli elementi inclusi e di ciò che non è incluso nei modelli di team.

| **Proprietà del team supportate dai modelli di team** | **Proprietà del team non ancora supportate dai modelli di team** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipologia di modello base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni dei canali |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale preferito automaticamente | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Nelle versioni future di Microsoft Teams verranno aggiunti altri modelli, quindi controllare di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Che cosa sono i tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per specifici settori. Questi modelli di base spesso contengono app proprietarie non disponibili nello Store. Inoltre, i modelli di base spesso contengono proprietà del team non ancora supportate singolarmente nei modelli di team. Informazioni su come usare i modelli [di team in Microsoft Graph.](get-started-with-teams-templates.md)

Dopo aver definito un tipo di modello di base, è possibile estendere o eseguire l'override di questi modelli speciali con proprietà aggiuntive che si desidera specificare. Alcuni tipi di modello di base contengono proprietà che non possono essere sostituite.

Per impostazione predefinita, il modello di base è impostato su **Standard,** che non contiene altre app proprietarie o proprietà speciali. Di seguito è riportato l'elenco corrente dei tipi di modello di base disponibili.

| Tipologia di modello base | baseTemplateId | Proprietà del modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Nessuna app e proprietà aggiuntive |
| Istruzione -<br>Team di classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | App:<ul><li>OneNote Blocco appunti per la classe (aggiunto alla **scheda** Generale) </li><li>App Attività (aggiunta alla **scheda** Generale)</li></ul> Proprietà del team:<ul><li>Visibilità del team impostata **su HiddenMembership** (non può essere sostituita)</li></ul> |
| Istruzione -<br>Team del personale | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | App:<ul><li>OneNote Blocco appunti per personale (aggiunto alla **scheda** Generale)</li></ul> |
|Istruzione -<br>Team PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | App:<ul><li>OneNote Blocco appunti PLC (aggiunto alla **scheda** Generale)</ul></li>|
| Retail -<br>Store | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | Canali:<ul><li>Passaggio di consegne del turno</li><li>Apprendimento</li></ul>Proprietà del team<ul><li>Visibilità del team impostata su Public</li></ul>Autorizzazioni dei membri<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul> |
| Retail -<br>Collaborazione con i manager | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | Canali:<ul><li>Apprendimento</li><li>Operazioni</li></ul>Proprietà del team:<ul><li>Visibilità del team impostata su Private</li></ul>Autorizzazioni per i membri:<ul><li>Impedire ai membri di creare, aggiornare o rimuovere canali</li><li>Impedire ai membri di aggiungere o rimuovere app</li><li>Impedire ai membri di creare, aggiornare o rimuovere connettori</li></ul>|
| Sanità -<br>Rione |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |Canali: <ul><li>Annunci\*</li><li>Briefing\*</li><li>Giri di visite</li><li>Personale\*</li><li>Formazione\*</li></ul>\*Canali aggiunti automaticamente ai preferiti |
|Sanità -<br>Ospedale | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |Canali:<ul><li>Annunci\*</li><li>Conformità\*</li><li>Pulizie</li><li>Risorse umane</li></li><li>Farmacia</li></ul>\*Canale preferito automaticamente|
|||


Usare i modelli seguenti per creare team sia nel client Teams che in Microsoft Graph.


| Tipologia di modello base | baseTemplateId | Proprietà del modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo Champions</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li> |
| Gestire un progetto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gestire un evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e pubbliche relazioni</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat dei dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li></ul>|
|Organizzare l'help desk| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborare all'assistenza sanitaria| `healthcareWard `| Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li>|
| Collaborare alla crisi globale o all'evento |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Lavorare in remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Aggiornamento per dirigenti</li></ul>App: <ul><li>Complimenti</li><li>Wiki</li><li>Sito Web</li></ul>|
|Collaborare all'interno di una filiale bancaria| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Coaching</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>|
|Coordinare la risposta agli eventi imprevisti| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Ripristino</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Ospedale| `healthcareHospita`l |Canali: <ul><li>Generale<li>Annunci</li><li>Conformità</li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li></ul>|
|Organizzare un negozio| `retailStore` |Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.`<br>`template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Riga 2</li><li>Riga 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li></ul>|
|Vendita al dettaglio: collaborazione tra responsabili| `retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

Per [altre informazioni, vedere Introduzione ai modelli di team nell'interfaccia](get-started-with-teams-templates-in-the-admin-console.md) di amministrazione.

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai modelli di team nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)
- [Nuovo team](/powershell/module/teams/New-Team?view=teams-ps)
- [Formazione per amministratori per Microsoft Teams](itadmin-readiness.md)
