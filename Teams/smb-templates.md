---
title: Modelli di team per le piccole e medie imprese create con Microsoft Graph
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
description: Usare i modelli predefiniti di Microsoft teams incorporati in Microsoft Graph per creare rapidamente e facilmente team per piccole e medie imprese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294552"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelli di teams incorporati in Microsoft Graph per piccole e medie imprese

I modelli di Microsoft teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le piccole e medie imprese, i modelli possono essere particolarmente potenti, in quanto aiutano gli amministratori a distribuire rapidamente team in tutta l'organizzazione. I modelli consentono anche di orientare gli utenti e iniziare a usare teams in modo efficace. Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione.

Attualmente offriamo tre modelli SMB di prima parte che possono essere sfruttati per svariate situazioni. Tutti i modelli creeranno Team *privati* . Dopo aver creato i team e averli pronti per l'implementazione, è possibile impostare la privacy a *livello* di organizzazione o *pubblica*, in base alle esigenze. Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates.md)di team.

## <a name="company-wide-template"></a>Modello a livello aziendale
Il modello a livello aziendale è pensato per la comunicazione e la collaborazione rilevanti per l'intera società. Puoi usare il canale generale per gli annunci a livello aziendale, le notizie del settore o i post esecutivi. Il canale Human Resources è il luogo ideale per consolidare tutte le attività correlate alle risorse umane, ad esempio post di lavoro, nuovi imbarcazione, formazione e sviluppo dei dipendenti. Il canale Fun Stuff offre una piattaforma sociale per tutti i post casuali e divertenti.

| Tipo di modello di base  | baseTemplateId | Proprietà disponibili con questo modello di base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>A livello aziendale | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canali <ul><li>Generale\*</li><li>Risorse umane\*</li><li>Cose divertenti\*</li></ul><br> App<ul><li>Portale aziendale (sito Web aggiunto al canale **risorse umane** ) </li> </UL><br>Proprietà del team <ul><li>Visibilità del team impostata su privato</li></ul> |

* Canali preferiti automaticamente 

Per creare il team a livello aziendale utilizzando le impostazioni predefinite del modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

## <a name="executive-team-template"></a>Modello di team Executive

Il modello Executive Team è ideale per creare un team per i dirigenti aziendali per comunicare e collaborare a iniziative aziendali come le priorità annuali, i bilanci fiscali, le iniziative strategiche e i clienti principali. Questo modello include un canale *privato* per invitare gli utenti selezionati per argomenti specifici.

| Tipo di modello di base  | baseTemplateId | Proprietà disponibili con questo modello di base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Team Executives | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canali <ul><li>Generale\*</li><li>Privato \*</li></ul> App<ul><li>OneNote (aggiunto al canale **privato** )</li> <li>Planner (aggiunto al canale **privato** ) </li></ul><br>Proprietà del team <ul><li>Visibilità del team impostata su privato</li></ul> | 

* Canali preferiti automaticamente<br>

Per creare il team Executives prendendo i valori predefiniti dal modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

## <a name="departmental-team-template"></a>Modello di Team dipartimentale

Il modello del team dipartimentale può essere usato per creare un team per singoli reparti o per progetti. Il modello Finance team è ideale per tutti i post, gli annunci e la collaborazione e la comunicazione quotidiana all'interno dei membri del team finanziario e i membri del team Executive, come appropriato. Il modello include un canale *privato* per invitare gli utenti selezionati per argomenti specifici. Forniamo anche lo script seguente per il team Finance che può essere usato per estendere il modello ad altri reparti o progetti specifici aggiungendo, eliminando o modificando a piacimento. Ad esempio, se si ha un reparto *Marketing* , lo script può essere adattato rinominando il team da *Finance* a *Marketing* per creare un nuovo team di marketing

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Finanze  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canali <ul><li>Generale\*</li><li>Privato \*</li></ul><br> App<ul><li>OneNote (aggiunto al canale **privato** )</li> <li>Planner (aggiunto al canale **privato** ) </li> </ul><br>Proprietà del team <ul><li>Visibilità del team impostata su privato</li></ul> | 

* Canali preferiti automaticamente

Per creare il team finanziario prendendo le impostazioni predefinite dal modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Esempio: script di estensione del modello di Team Finance

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

- [Introduzione ai modelli di teams nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Introduzione ai modelli di Teams](get-started-with-teams-templates.md)
- [Crea team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in anteprima)

