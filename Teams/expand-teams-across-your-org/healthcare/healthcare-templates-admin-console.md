---
title: Creare un team usando i modelli di Teams per il settore sanitario
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usare i modelli di Microsoft Teams nell’interfaccia di amministrazione o con Microsoft Graph per creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260308"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Creare un team usando i modelli di Teams per il settore sanitario

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni del settore sanitario, i modelli possono essere particolarmente efficaci perché offrono agli utenti una struttura di orientamento sull'uso efficace di Teams. In più, i modelli consentono agli amministratori di implementare team coerenti all'interno dell'organizzazione. Questo articolo è per i responsabili dedicati alla pianificazione, all'implementazione e alla gestione di più team nell'organizzazione del settore sanitario.

Scegliere un metodo per creare team con i modelli di Teams per il settore sanitario:

| Chi | Metodo da usare: |
| ---- | --------- |
| Amministratori e professionisti IT | [Usare l'interfaccia di amministrazione di Teams](#use-the-teams-templates-in-the-teams-admin-center) per creare team basati sui modelli di Teams per il settore sanitario.|
| Sviluppatori e integratori di sistemi | [Usare Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) per creare team basati sui modelli di Teams per il settore sanitario. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usare i modelli di Teams nell’interfaccia di amministrazione di Teams

Gli amministratori di Microsoft Teams possono usare l'interfaccia di amministrazione per creare team con i modelli di Teams. Attualmente sono disponibili due modelli del produttore per il settore sanitario da usare in diverse situazioni. Per scoprire di più sui modelli dei team in generale, vedere [Introduzione ai modelli di Teams nell’interfaccia di amministrazione](../../get-started-with-teams-templates-in-the-admin-console.md).

### <a name="collaborate-on-patient-care"></a>Collaborare all'assistenza sanitaria

 Semplificare le comunicazioni e la collaborazione nell'assistenza sanitaria all'interno di un reparto, un dispensario o un dipartimento. Il modello può essere usato per agevolare la gestione dei pazienti e le esigenze operative di un reparto.

| Tipologia di modello base |baseTemplateId| Proprietà del modello base |
| ------------------ |---|----------------------------------------------------- |
| Collaborare all'assistenza sanitaria |`healthcareWard` | Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi</li></ul>|
||||

### <a name="hospital"></a>Ospedale

Semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso automaticamente in modo da includere specializzazioni, ad hoc.

| Tipologia di modello base |baseTemplateId | Proprietà del modello base |
| ------------------|-- |----------------------------------------------------- |
|Ospedale|`healthcareHospital`|Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Gli sviluppatori possono usare Microsoft Graph per creare team con i modelli di Teams. Attualmente sono disponibili due modelli del produttore per il settore sanitario da usare in diverse situazioni. Per scoprire di più sui modelli dei team in generale, vedere [Introduzione ai modelli di Teams](../../get-started-with-teams-templates.md). Per informazioni sui modelli di Teams e su Microsoft Graph, vedere la [panoramica sull'API Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) e [tipo di risorsa teamsTemplate](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="ward-template"></a>Modello di reparto

Il modello di reparto è destinato alla comunicazione e alla collaborazione all'interno di un reparto, un dispensario o un dipartimento. Il modello può essere usato per agevolare la gestione dei pazienti oltre alle esigenze operative di un reparto. Ad esempio, gli annunci di reparto possono essere pubblicati nel canale *Annunci* e i turni possono essere gestiti in *Personale*. Questo modello è utile per semplificare l’operatività di reparto.

|Tipologia di modello base |baseTemplateId |Canali del modello di base|
|:--- |:---|:---|
|Settore sanitario - Reparto | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annunci\* <br> Briefing\* <br> Giri di visite\* <br> Personale\* <br> Formazione\* |
|     | |         |

\* Aggiunto automaticamente ai Preferiti

### <a name="hospital-template"></a>Modello ospedale

Il modello ospedale mira a semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Questo modello è incluso in diversi canali operativi, tra cui *Annunci*, *Pulizie* e *Farmacia*, ma di seguito viene fornito uno script che estende il modello con un'ampia varietà di altri canali incentrati su reparti o specializzazioni che è possibile aggiungere, eliminare o modificare in base alle proprie esigenze. Ad esempio, se si ha un dipartimento di *Endocrinologia*, ma non è necessario un canale per *Oftalmologia*, lo script può essere adattato in modo da includere un canale *Endocrinologia* e rimuovere il canale *Oftalmologia*. Per evitare la saturazione delle notifiche, è consigliabile non aggiungere automaticamente ai Preferiti questi canali incentrati su specializzazioni o reparti. Gli utenti in genere aggiungono ai Preferiti i canali che trovano pertinenti.

|Tipologia di modello base |baseTemplateId |Canali del modello di base|
|:--- |:---|:---|
|Settore sanitario - Ospedale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annunci\* <br> Conformità\* <br> Pulizie <br> Risorse umane <br> Farmacia |
| | |  |

\* Aggiunto automaticamente ai Preferiti 

### <a name="how-to-use-first-party-templates"></a>Come usare i modelli del produttore

Per usare questi modelli, è sufficiente modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti.  Per altre informazioni su come implementare i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda Generale.

#### <a name="example-hospital-template-extension-script"></a>Esempio: script di estensione del modello ospedale

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a>Argomenti correlati

[Introduzione ai modelli di Teams](../../get-started-with-teams-templates.md)

[Guida introduttiva a Teams per le organizzazioni del settore sanitario](teams-in-hc.md)
