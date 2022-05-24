---
title: Modelli di team per piccole e medie imprese creati con Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Usare Microsoft Teams modelli predefiniti predefiniti predefiniti di Microsoft Graph per creare team per piccole e medie imprese in modo semplice e rapido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5317b989bd7fe77f34743b6554cd356c226c2fa8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646305"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelli di team predefiniti di Microsoft Graph per piccole e medie imprese

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le piccole e medie imprese, i modelli possono essere particolarmente potenti, perché consentono di distribuire rapidamente Teams all'interno dell'organizzazione. I modelli consentono anche agli utenti di orientarsi nell'uso efficace di Teams. Questo articolo è rivolto agli utenti responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione.

Attualmente sono disponibili tre modelli predefiniti per piccole e medie imprese che è possibile usare in diverse situazioni. Tutti i modelli creano team *privati* . Dopo aver creato i team ed essere pronti per l'implementazione nell'organizzazione, è possibile impostare la privacy su *A livello di organizzazione* o *Pubblico*, in base alle esigenze.

Per altre informazioni sui modelli di team in generale, vedere [Attività iniziali con i modelli di team che usano Microsoft Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide modello

Il modello Company-Wide è pensato per la comunicazione e la collaborazione per l'intera azienda. È possibile usare il canale Generale per gli annunci a livello aziendale, le notizie del settore o i post dei dirigenti. Il canale Risorse umane è il luogo ideale per consolidare tutte le attività correlate alle risorse umane, come post di lavoro, onboarding di nuovi dipendenti, formazione e sviluppo. Il canale Fun Stuff offre una piattaforma social per tutti i post casuali e divertenti.

| Tipo di modello  | TemplateId | Proprietà del modello |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>A livello aziendale | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canali <ul><li>Generale\*</li><li>Risorse umane\*</li><li>Cose divertenti\*</li></ul><br> App<ul><li>Portale aziendale (sito Web aggiunto al canale **Risorse umane**) </li> </UL><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> |

*Canali preferiti automaticamente 

Per creare il team Company-Wide prendendo le impostazioni predefinite dal modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di team, vedere l'articolo di Microsoft Graph [sulla creazione di un team](/graph/api/team-post?view=graph-rest-beta).

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

Il modello Team dirigenziale è ideale per creare un team che i dirigenti aziendali possono comunicare e collaborare su iniziative aziendali come priorità annuali, budget fiscali, iniziative strategiche e clienti principali. Questo modello include un canale *privato* per invitare utenti selezionati per argomenti specifici.

| Tipo di modello  | TemplateId | Proprietà del modello |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Team dei dirigenti | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canali <ul><li>Generale\*</li><li>Privato \*</li></ul> App<ul><li>OneNote (aggiunto al canale **Privato**)</li> <li>Planner (aggiunto al canale **Privato** ) </li></ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> | 

*Canali preferiti automaticamente<br>

Per creare il team dirigenti prendendo le impostazioni predefinite dal modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di team, vedere l'articolo di Microsoft Graph [sulla creazione di un team](/graph/api/team-post?view=graph-rest-beta).

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

Il modello Team di reparto può essere usato per creare un team per singoli reparti o progetti. Il modello del team Finance è ideale per tutti i post, gli annunci, la collaborazione e la comunicazione quotidiana all'interno dei membri del team Finance e dei membri del team dirigenziario in base alle esigenze. Il modello include un canale *privato* per invitare utenti selezionati per argomenti specifici.

È inoltre disponibile lo script seguente per il team finance che può essere usato per estendere il modello ad altri reparti o progetti specifici aggiungendo, eliminando o modificando a proprio piacimento. Ad esempio, se si ha un reparto *Marketing* , lo script può essere adattato rinominando il team da *Finanza* a *Marketing* per creare un nuovo team di marketing

| Tipo di modello | TemplateId | Proprietà del modello |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanze  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canali <ul><li>Generale\*</li><li>Privato \*</li></ul><br> App<ul><li>OneNote (aggiunto al canale **Privato**)</li> <li>Planner (aggiunto al canale **Privato** ) </li> </ul><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> | 

*Canali preferiti automaticamente

Per creare il team Finance utilizzando le impostazioni predefinite dal modello predefinito, fornire la rappresentazione JSON dell'oggetto team nel corpo della richiesta. Per altre informazioni su come distribuire i modelli di team, vedere l'articolo di Microsoft Graph [sulla creazione di un team](/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Esempio: Script di estensione modello Team finanziario

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

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
- [Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)
