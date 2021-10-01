---
title: Usare i modelli di team per il settore sanitario
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Informazioni su come gestire e usare i modelli del team sanitario nell'interfaccia di amministrazione di Teams e con Microsoft Graph per creare rapidamente e facilmente team per l'organizzazione sanitaria.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 78269b393c384af82e48284e3ffefe8785013975
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046002"
---
# <a name="use-healthcare-team-templates"></a>Usare i modelli di team per il settore sanitario

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni sanitarie, i modelli di team possono essere particolarmente efficaci, perché consentono di distribuire rapidamente team coerenti all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi su come usare in modo efficace Teams.

Teams include modelli progettati specificamente per le organizzazioni sanitarie. Usare questi modelli predefiniti per creare rapidamente team in cui il personale possa comunicare e collaborare alle esigenze operative o di assistenza ai pazienti. In questo articolo verranno presentati i modelli di Teams e verrà consigliato come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Gestire i modelli di team nell’interfaccia di amministrazione di Teams](#manage-team-templates-in-the-teams-admin-center): visualizzare i modelli di team e applicare i criteri di modelli per controllare quali modelli possono essere usati in Teams dal personale per la creazione di team. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](../../templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'interfaccia di amministrazione di Teams.](../../get-started-with-teams-templates-in-the-admin-console.md)

Attualmente sono disponibili i modelli di team sanitari predefiniti seguenti. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a modelli **Teams**  >  **team.**
### <a name="patient-care"></a>Assistenza ai pazienti

 Questo modello è destinato alla comunicazione e alla collaborazione all'interno di un reparto, un dispensario o un dipartimento. È possibile usare questo modello per facilitare la gestione dei pazienti e le esigenze operative di un rione. Ad esempio, pubblicare annunci di rione nel *canale Annunci* e gestire i turni nel *canale Personale.*

| Tipo di modello |TemplateId| Proprietà del modello |
| ------------------ |---|----------------------------------------------------- |
| Assistenza ai pazienti |`healthcareWard` | Canali:<ul><li>Generale</li><li>Annunci<ul><li>Bollettini&sup1;</li></ul></li><li>Riunioni informali<ul><li>Elenchi (elenco pazienti)&sup1;</li></ul></li><li>Arrotondamenti<ul><li>Ispezione&sup1;</li></ul></li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi</li><li>Attività</li><li>Approvazioni</li><li>Turni</li><li>Bollettini</li><li>Revisione</li></ul>|
||||

&sup1; App aggiunta al canale come scheda
### <a name="hospital"></a>Ospedale

Questo modello mira a semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso per essere personalizzato.

| Tipo di modello |TemplateId | Proprietà del modello |
| ------------------|-- |----------------------------------------------------- |
|Ospedale|`healthcareHospital`|Canali: <ul><li>Generale<ul><li>Elenchi&sup1;</li></ul></li><li>Announcements<ul><li>Bollettini&sup1;</li></ul></li><li>Conformità</li><ul><li>Ispezione&sup1;</li></ul></li><li>Pulizie</li><li>Risorse umane<ul><li>Idee&sup1;</li></ul></li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Attività</li><li>Elenchi</li><li>Approvazioni</li><li>Turni</li><li>Bollettini</li><li>Revisione</li><li>Idee</li></ul>|
||||

&sup1; App aggiunta al canale come scheda
## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Gli sviluppatori possono usare Microsoft Graph per creare team dai modelli di team predefiniti. Per altre informazioni sull'uso dei modelli di team con Microsoft Graph, vedere [Introduzione ai modelli di team con Microsoft Graph](../../get-started-with-teams-templates.md), [Panoramica dell'API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) e [Tipo di risorsa teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Ecco i modelli predefiniti del team sanitario.
### <a name="ward"></a>Reparto

Il modello di reparto è destinato alla comunicazione e alla collaborazione all'interno di un reparto, un dispensario o un dipartimento. Il modello può essere usato per agevolare la gestione dei pazienti e le esigenze operative di un reparto. Ad esempio, gli annunci di reparto possono essere pubblicati nel canale *Annunci* e i turni possono essere gestiti in *Personale*. Questo modello è utile per semplificare l’operatività di reparto.

|Tipo di modello |TemplateId |Canali del modello|
|:--- |:---|:---|
|Settore sanitario - Reparto | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Generale<br>Annunci&sup2; <br> Riunioni informali&sup2; <br> Giri&sup2; <br> Personale&sup2; <br> Formazione&sup2; |
|     | |         |

&sup2; Canali preferiti automaticamente

### <a name="hospital"></a>Ospedale

Il modello ospedale mira a semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Questo modello include diversi canali operativi, ad esempio *Annunci,* *Custodiale* e *Farmacia.* Microsoft fornisce anche uno script che è possibile usare per estendere il modello con altri reparti o canali specializzati. È possibile modificarlo in base alle proprie esigenze.

Ad esempio, se si ha un reparto di *endocrinologia,* ma non è necessario un canale per *Oftalimologia,* lo script può essere adattato in modo da includere un canale *endocrinologico* e rimuovere il canale *oftalmologia.* Per evitare la saturazione delle notifiche, è consigliabile non aggiungere automaticamente ai Preferiti questi canali incentrati su specializzazioni o reparti. Gli utenti in genere aggiungono ai Preferiti i canali che trovano pertinenti.

|Tipo di modello |TemplateId |Canali del modello|
|:--- |:---|:---|
|Settore sanitario - Ospedale | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Generale<br>Annunci&sup2; <br> Conformità&sup2; <br> Pulizie <br> Risorse umane <br> Farmacia |
| | |  |

&sup2; Canali preferiti automaticamente

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Come usare i modelli di team con Microsoft Graph

Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti. Per altre informazioni su come distribuire i modelli di team, vedere l'articolo Microsoft Graph su come [creare un team.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella **scheda** Generale.

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

### <a name="related-articles"></a>Articoli correlati

- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Introduzione ai modelli di team con Microsoft Graph](../../get-started-with-teams-templates.md)
- [Guida introduttiva a Teams per le organizzazioni del settore sanitario](teams-in-hc.md)