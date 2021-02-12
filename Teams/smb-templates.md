---
title: Modelli di Teams per piccole e medie imprese creati con Microsoft Graph
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
description: Usare i modelli predefiniti di Microsoft Teams incorporati in Microsoft Graph per creare in modo semplice e rapido team per le piccole e medie imprese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294552"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelli di Teams creati in Microsoft Graph per piccole e medie imprese

I modelli di Microsoft Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.

Per le piccole e medie imprese, i modelli possono essere particolarmente potenti perché consentono agli amministratori di distribuire rapidamente Teams nell'intera organizzazione. I modelli aiutano anche a orientare gli utenti e a iniziare a usare Teams in modo efficace. Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione.

Attualmente sono disponibili tre modelli di mb di prima scelta che è possibile usare per diverse situazioni. Tutti i modelli creeranno *team* privati. Dopo aver creato Teams e quando si è pronti per l'implementazione nella propria organizzazione, è possibile impostare la privacy su A livello di organizzazione o *Pubblico,* in base alle esigenze.  Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di Teams.](get-started-with-teams-templates.md)

## <a name="company-wide-template"></a>Company-Wide modello
Il Company-Wide è pensato per le comunicazioni e la collaborazione rilevanti per l'intera azienda. È possibile usare il canale Generale per annunci a livello aziendale, notizie di settore o post della dirigenziale. Il canale Risorse umane è il luogo ideale per consolidare tutte le attività correlate alle risorse umane, come post di lavoro, onboarding di nuovi dipendenti, formazione e sviluppo. Il canale Fun Stuff offre una piattaforma social per tutti i post casuali e divertenti.

| Tipo di modello di base  | baseTemplateId | Proprietà disponibili in questo modello di base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>A livello aziendale | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canali <ul><li>Generale\*</li><li>Risorse umane\*</li><li>Cose divertenti\*</li></ul><br> App<ul><li>Portale aziendale (sito Web aggiunto al **canale Risorse** umane) </li> </UL><br>Proprietà del team <ul><li>Visibilità del team impostata su Privato</li></ul> |

*Canali preferiti automaticamente 

Per creare il team Company-Wide di lavoro usando le impostazioni predefinite dal modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph [sulla creazione di un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

## <a name="executive-team-template"></a>Modello Team di dirigenti

Il modello Team di dirigenti è ideale per creare un team in cui i dirigenti aziendali possano comunicare e collaborare alle iniziative aziendali come le priorità annuali, i budget fiscali, le iniziative strategiche e i principali clienti. Questo modello viene fornito con un *canale* privato per invitare utenti selezionati per argomenti specifici.

| Tipo di modello di base  | baseTemplateId | Proprietà disponibili in questo modello di base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Team dirigenti | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canali <ul><li>Generale\*</li><li>Privato \*</li></ul> App<ul><li>OneNote (aggiunto al **canale** privato)</li> <li>Planner (aggiunto al **canale** privato) </li></ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Privato</li></ul> | 

*Canali preferiti automaticamente<br>

Per creare il team Dirigenti usando le impostazioni predefinite del modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph [sulla creazione di un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

Il modello Team di reparto può essere usato per creare un team per singoli reparti o per progetti. Il modello del team Finanze è ideale per tutti i post, gli annunci, la collaborazione e le comunicazioni quotidiane all'interno dei membri del team Finance e dei membri del team di dirigenti, in base alle esigenze. Il modello viene fornito con un *canale* privato per invitare utenti selezionati per argomenti specifici. Lo script seguente viene fornito anche per il team finanze, che può essere usato per estendere il modello ad altri reparti o a progetti specifici aggiungendo, eliminando o modificando come si desidera. Ad esempio, se  si ha un reparto Marketing, lo script può  essere adattato rinominando il team da Finanze a *Marketing* per creare un nuovo team marketing

| Tipo di modello di base | baseTemplateId | Proprietà disponibili in questo modello di base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanze  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canali <ul><li>Generale\*</li><li>Privato \*</li></ul><br> App<ul><li>OneNote (aggiunto al **canale** privato)</li> <li>Planner (aggiunto al **canale** privato) </li> </ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Privato</li></ul> | 

*Canali preferiti automaticamente

Per creare il team Finanze usando le impostazioni predefinite del modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph [sulla creazione di un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

### <a name="example-finance-team-template-extension-script"></a>Esempio: script di estensione del modello Team finanziario

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

- [Introduzione ai modelli di Teams nella console di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Introduzione ai modelli di Teams](get-started-with-teams-templates.md)
- [Creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in anteprima)

