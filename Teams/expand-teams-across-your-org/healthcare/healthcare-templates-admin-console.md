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
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Informazioni su come gestire e usare i modelli del team sanitario nell'interfaccia di amministrazione di Teams e con Microsoft Graph per creare rapidamente e facilmente team per l'organizzazione sanitaria.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778966"
---
# <a name="use-healthcare-team-templates"></a>Usare i modelli di team per il settore sanitario

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni sanitarie, i modelli di team possono essere particolarmente efficaci, perché consentono di distribuire rapidamente team coerenti all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi su come usare in modo efficace Teams.

Teams include modelli progettati specificamente per le organizzazioni sanitarie. Usare questi modelli predefiniti per creare rapidamente team in cui il personale possa comunicare e collaborare alle esigenze operative o di assistenza ai pazienti. In questo articolo verranno presentati i modelli di Teams e verrà consigliato come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](../../templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'Teams di amministrazione.](../../get-started-with-teams-templates-in-the-admin-console.md)

Attualmente sono disponibili i modelli di team sanitari predefiniti seguenti. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a modelli **Teams**  >  **team.**

### <a name="patient-care"></a>Patient Care

Semplificare le comunicazioni e la collaborazione nell'assistenza sanitaria all'interno di un reparto, un dispensario o un dipartimento. Utilizzare questo modello per facilitare la gestione dei pazienti e le esigenze operative di un rione. Ad esempio, pubblicare annunci di rione nel *canale Annunci* e gestire i turni nel *canale Personale.*

>[!div class="mx-tdBreakAll"]
>| Tipo di modello |TemplateId| Proprietà del modello |
>| ------------------ |---|----------------------------------------------------- |
>| Patient Care |`healthcareWard` | Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Approvazioni</li><li>Bollettini</li><li>Revisione</li><li>Elenchi</li><li>Turni</li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|

### <a name="hospital"></a>Ospedale

Semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso per essere personalizzato.

>[!div class="mx-tdBreakAll"]
>| Tipo di modello |TemplateId | Proprietà del modello |
>| ------------------|-- |----------------------------------------------------- |
>|Ospedale|`healthcareHospital`|Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li></li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul>  App: <ul><li>Approvazioni</li><li>Bollettini</li><li>Idee per i dipendenti</li><li>Ispezione</li><li>Elenchi</li><li>Turni</li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

Ecco i modelli predefiniti del team sanitario.

### <a name="patient-care"></a>Patient Care

Questo modello è destinato alla comunicazione e alla collaborazione all'interno di un reparto, un dispensario o un dipartimento. Utilizzare questo modello per facilitare la gestione dei pazienti e le esigenze operative di un rione. Ad esempio, gli annunci di reparto possono essere pubblicati nel canale *Annunci* e i turni possono essere gestiti in *Personale*. Questo modello è utile per semplificare l’operatività di reparto.

>[!div class="mx-tdBreakAll"]
>|Tipo di modello |TemplateId |Canali del modello|
>|:--- |:---|:---|
>|Settore sanitario - Reparto | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | Generale<br>Annunci&sup2; <br> Riunioni informali&sup2; <br> Giri&sup2; <br> Personale&sup2; <br> Formazione&sup2; |

&sup2; Canali preferiti automaticamente

### <a name="hospital"></a>Ospedale

Questo modello mira a semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale. Include diversi canali operativi, ad esempio *Annunci*, *Custode* e *Farmacia*. È anche disponibile uno script che è possibile usare per estendere il modello con più reparti o canali specializzati. È possibile modificarlo in base alle proprie esigenze.

Ad esempio, se si dispone di un reparto *di endocrinologia* , ma non è necessario un canale per *l'oftalmologia*, è possibile adattare lo script per includere un canale *di endocrinologia* e rimuovere il canale *oftalmologia* . Per evitare la saturazione delle notifiche, è consigliabile non aggiungere automaticamente ai Preferiti questi canali incentrati su specializzazioni o reparti. Gli utenti in genere aggiungono ai Preferiti i canali che trovano pertinenti.

>[!div class="mx-tdBreakAll"]
>|Tipo di modello |TemplateId |Canali del modello|
>|:--- |:---|:---|
>|Settore sanitario - Ospedale | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | Generale<br>Annunci&sup2; <br> Conformità&sup2; <br> Pulizie <br> Risorse umane <br> Farmacia |

&sup2; Canali preferiti automaticamente

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Come usare i modelli di team con Microsoft Graph

Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti. Per altre informazioni su come distribuire i modelli di team, vedere l'articolo microsoft Graph su come [creare un team.](/graph/api/team-post?view=graph-rest-beta)

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
- [Guida introduttiva a Teams per le organizzazioni del settore sanitario](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)