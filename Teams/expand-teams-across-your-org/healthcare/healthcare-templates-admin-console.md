---
title: Creare un team usando i modelli sanitari di Teams
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
description: Usare i modelli di Microsoft Teams nell'interfaccia di amministrazione o con Microsoft Graph per creare in modo semplice e rapido i team, fornendo un modello predefinito di impostazioni, canali e app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260308"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Creare un team usando i modelli sanitari di Teams

I modelli di Microsoft Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.

Per le organizzazioni sanitarie, i modelli possono essere particolarmente potenti perché forniscono una struttura che gli utenti possano orientarsi nell'uso efficace di Teams. I modelli consentono inoltre agli amministratori di distribuire team coerenti all'interno dell'organizzazione. Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team nell'intera organizzazione sanitaria.

Scegliere un metodo per creare team con i modelli sanitari di Teams:

| Chi | Metodo da usare: |
| ---- | --------- |
| Amministratori e professionisti IT | [Usare l'interfaccia di amministrazione di Teams](#use-the-teams-templates-in-the-teams-admin-center) per creare team basati sui modelli di Teams sanitari.|
| Sviluppatori e system di integrazione | [Usare Microsoft Graph per](#use-the-teams-templates-with-the-microsoft-graph) creare team basati sui modelli di Teams sanitari. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usare i modelli di Teams nell'interfaccia di amministrazione di Teams

Gli amministratori di Microsoft Teams possono usare l'interfaccia di amministrazione di Teams per creare team con i modelli di Teams. Attualmente sono disponibili due modelli sanitari di prima scelta da usare per diverse situazioni. Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams nell'interfaccia di amministrazione.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Collaborare all'assistenza pazienti

 Semplificare la comunicazione e la collaborazione sanitaria all'interno di un pod o di un dipartimento. Il modello può essere usato per facilitare la gestione dei pazienti e le esigenze operative di una azienda.

| Tipo di modello di base |baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------ |---|----------------------------------------------------- |
| Collaborare all'assistenza pazienti |`healthcareWard` | Canali:<ul><li>Generale</li><li>Annunci</li><li>Huddles</li><li>Arrotondamenti</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi</li></ul>|
||||

### <a name="hospital"></a>Ospedale

Semplificare la comunicazione e la collaborazione tra più reparti, pod e dipartimenti all'interno di un ospedale. Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso per includere specializzazioni, ad hoc.

| Tipo di modello di base |baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------|-- |----------------------------------------------------- |
|Ospedale|`healthcareHospital`|Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Responsabile</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Gli sviluppatori possono usare Microsoft Graph per creare team con i modelli di Teams. Attualmente sono disponibili due modelli sanitari di prima scelta da usare per diverse situazioni. Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di Teams.](../../get-started-with-teams-templates.md) Per informazioni sui modelli di Teams e su Microsoft Graph, vedere la panoramica [dell'API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) di Microsoft Teams e il tipo [di risorsa teamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)

### <a name="ward-template"></a>Modello Di modelli

Il modello modello è pensato per essere utilizzato per le comunicazioni e la collaborazione all'interno di un progetto, un pod o un reparto. Il modello può essere usato per facilitare la gestione dei pazienti, nonché per le esigenze operative di una organizzazione. Ad esempio, gli annunci di annunci possono essere pubblicati *nel* canale Annunci e i turni possono essere gestiti in *Staffing.* Questo modello è utile per semplificare le operazioni di ricerca.

|Tipo di modello base |baseTemplateId |Canali dei modelli di previsione|
|:--- |:---|:---|
|Sanità - Assistenza sanitaria | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annunci\* <br> Huddles\* <br> Arrotondamenti\* <br> Personale\* <br> Formazione\* |
|     | |         |

\* Preferiti automaticamente

### <a name="hospital-template"></a>Modello Ospedale

Il modello ospedale è pensato per comunicare e collaborare tra più reparti, pod e dipartimenti all'interno di un ospedale. In questo modello sono inclusi diversi canali operativi, tra cui *Annunci,* Responsabile e Farmacia, ma di seguito viene fornito uno script che estende il modello con diversi canali di reparto o specializzati che è possibile aggiungere, eliminare o modificare in base alle proprie esigenze. Ad esempio, se si ha un reparto di *Endocrinology,* ma non è necessario un canale per *Ophthalmology,* lo script può essere adattato per includere un canale *endocrinology* e rimuovere il canale *Ophthalmology.* È consigliabile non aggiungere automaticamente ai preferiti questi canali specializzati o modellati, per evitare la saturazione delle notifiche. Gli utenti in genere hanno preferito i canali pertinenti.

|Tipo di modello base |baseTemplateId |Canali dei modelli di previsione|
|:--- |:---|:---|
|Sanità - Ospedale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annunci\* <br> Conformità\* <br> Responsabile <br> Risorse umane <br> Farmacia |
| | |  |

\* Preferiti automaticamente 

### <a name="how-to-use-first-party-templates"></a>Come usare i modelli di prima parte

Per usare questi modelli, basta modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID riportati sopra.  Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda Generale.

#### <a name="example-hospital-template-extension-script"></a>Esempio: Script di estensione del modello Hospital

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
