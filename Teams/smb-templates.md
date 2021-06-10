---
title: Teams modelli per piccole e medie imprese creati con Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Usare Microsoft Teams predefiniti predefiniti di Microsoft Graph creare rapidamente e facilmente team per piccole e medie imprese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116994"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Teams modelli predefiniti di Microsoft Graph per le piccole e medie imprese

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le piccole e medie imprese, i modelli possono essere particolarmente efficaci, perché consentono agli amministratori di distribuire rapidamente Teams all'interno dell'organizzazione. I modelli aiutano anche a orientare gli utenti e a iniziare a usare Teams efficace. Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione.

Attualmente sono disponibili tre modelli SMB di prima parte che è possibile sfruttare per un'ampia gamma di situazioni. Tutti i modelli creeranno *Teams.* Dopo aver creato il Teams e essere pronti per l'implementazione nell'organizzazione, è possibile impostare la privacy su *A* livello di organizzazione o *Pubblico,* in base alle esigenze. Per scoprire di più sui modelli dei team in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide modello
Il modello Company-Wide è destinato alla comunicazione e alla collaborazione rilevanti per l'intera azienda. È possibile usare il canale Generale per annunci aziendali, notizie di settore o post esecutivi. Il canale Risorse umane è un'ottima posizione per consolidare tutte le attività correlate alle risorse umane, come post di lavoro, onboarding di nuovi dipendenti, formazione e sviluppo. Il canale Cose divertenti offre una piattaforma social per tutti i post casuali e divertenti.

| Tipologia di modello base  | baseTemplateId | Proprietà del modello base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>A livello aziendale | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canali <ul><li>Generale\*</li><li>Risorse umane\*</li><li>Cose divertenti\*</li></ul><br> App<ul><li>Portale aziendale (sito Web aggiunto al **canale Risorse** umane) </li> </UL><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> |

*Canali preferiti automaticamente 

Per creare il team Company-Wide predefinito dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Richiesta 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>Modello Team per dirigenti

Il modello Executive Team è ideale per creare un team in cui i dirigenti aziendali possano comunicare e collaborare a iniziative aziendali come priorità annuali, budget fiscali, iniziative strategiche e clienti principali. Questo modello viene fornito con un *canale privato* per invitare utenti selezionati per argomenti specifici.

| Tipologia di modello base  | baseTemplateId | Proprietà del modello base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Team dirigenti | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canali <ul><li>Generale\*</li><li>Privato \*</li></ul> App<ul><li>OneNote (aggiunto al **canale** privato)</li> <li>Planner (aggiunto al **canale** privato) </li></ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> | 

*Canali preferiti automaticamente<br>

Per creare il team dirigenti prendendo le impostazioni predefinite dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Richiesta 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Modello Team di reparto

Il modello team reparto può essere usato per creare un team per singoli reparti o per progetti. Il modello di team Finance è ideale per tutti i post, gli annunci e la collaborazione e la comunicazione giornaliera all'interno dei membri del team Finance e dei membri del team di dirigenti, se appropriato. Il modello viene fornito con un *canale privato* per invitare utenti selezionati per argomenti specifici. Forniamo anche lo script seguente per il team Finanziario che può essere usato per estendere il modello ad altri reparti o progetti specifici aggiungendo, eliminando o modificando a proprio piacimento. Ad esempio, se si ha un reparto *Marketing,* lo script può essere adattato rinominando il team da *Finanze* a *Marketing* per creare un nuovo team di marketing

| Tipologia di modello base | baseTemplateId | Proprietà del modello base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanze  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canali <ul><li>Generale\*</li><li>Privato \*</li></ul><br> App<ul><li>OneNote (aggiunto al **canale** privato)</li> <li>Planner (aggiunto al **canale** privato) </li> </ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> | 

*Canali preferiti automaticamente

Per creare il team Finance prendendo le impostazioni predefinite dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Richiesta 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>Esempio: script di estensione del modello Finance Team

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai modelli Teams nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Introduzione ai modelli di Teams](get-started-with-teams-templates.md)
- [Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)