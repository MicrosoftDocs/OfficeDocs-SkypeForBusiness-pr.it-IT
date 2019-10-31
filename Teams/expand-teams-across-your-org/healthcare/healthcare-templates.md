---
title: Guida introduttiva ai modelli di Teams per le organizzazioni del settore sanitario
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Guida introduttiva ai modelli di Teams per le organizzazioni del settore sanitario
ms.openlocfilehash: e19c0403f259f400e784faf928738d36df66d618
ms.sourcegitcommit: ced9b584eeceff7ca0109cba5823c7c3ddbd092e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886439"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Guida introduttiva ai modelli di Teams per le organizzazioni del settore sanitario

I modelli di Microsoft teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni sanitarie, i modelli possono essere particolarmente potenti, poiché offrono agli utenti una struttura orientata a migliorare efficacemente i team. I modelli consentono inoltre agli amministratori di distribuire Team coerenti tra le rispettive organizzazioni. Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione sanitaria.

Attualmente offriamo due modelli di Healthcare di prima parte che puoi sfruttare per una varietà di situazioni. Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](../../get-started-with-teams-templates.md)di team.

## <a name="ward-template"></a>Modello di Ward

Il modello Ward è concepito per la comunicazione e la collaborazione all'interno di un reparto, un pod o un dipartimento. Il modello può essere usato per facilitare la gestione dei pazienti, oltre che per le esigenze operative di un reparto. Ad esempio, gli annunci di Ward possono essere pubblicati nel canale *annunci* e i turni possono essere gestiti in *personale*. Se stai cercando di semplificare le operazioni di Ward, questo modello è adatto a te.

|Tipo di modello di base |baseTemplateId |Canali del modello previsto|
|:--- |:---|:---|
|Assistenza sanitaria-Ward | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annunci\* <br> Huddles\* <br> Arrotonda\* <br> Personale\* <br> Formazione\* |
|     | |         |

\*Preferiti automaticamente

## <a name="hospital-template"></a>Modello di ospedale

Il modello Hospital è pensato per la comunicazione e la collaborazione tra più rioni, baccelli e reparti all'interno di un ospedale. Sono inclusi in questo modello diversi canali operativi, tra cui *annunci*, *custodia*e *farmacia*, ma forniamo anche uno script sotto il quale estende il modello con un'ampia varietà di servizi aggiuntivi o canali incentrati sulle specialità a cui è possibile aggiungere, eliminare o modificare i propri gusti. Ad esempio, se si ha un reparto di *endocrinologia* , ma non è necessario un canale per l' *Oftalmologia*, lo script può essere adattato per includere un canale di *endocrinologia* e rimuovere il canale di *Oftalmologia* . Per evitare la saturazione delle notifiche, è consigliabile che questi canali con modelli di specialità o di rione non siano preferiti automaticamente. Gli utenti in genere hanno favorito tutti i canali che trovano rilevanti.

|Tipo di modello di base |baseTemplateId |Canali del modello previsto|
|:--- |:---|:---|
|Healthcare-Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annunci\* <br> Conformità\* <br> Custodia <br> Risorse umane <br> Farmacia |
| | |  |

\*Preferiti automaticamente 

## <a name="care-coordination-template"></a>Modello di coordinamento cura

Il modello di coordinamento delle cure ha lo scopo di facilitare la comunicazione all'interno di un team di assistenza paziente, con alcuni esempi tra cui team interdisciplinari e multidisciplinari. L'applicazione per i pazienti proprietari è precaricata in questo modello e si trova nel canale generale. Con l'applicazione patients, è possibile curare elenchi di pazienti e i relativi valori associati e elementi vitali, rendendoli utili per l'arrotondamento e gli scenari di gestione dei pazienti. 

|Tipo di modello di base |baseTemplateId |Canali del modello previsto|
|:--- |:---|:---|
|Coordinamento assistenza sanitaria | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareCareCoordination')`   | Revisione post-trattamento\* <br> Pianificazione\* <br> Formazione\* |
| | |  |

\*Preferiti automaticamente 

## <a name="how-to-use-first-party-templates"></a>Come usare i modelli di First Party

Per usare questi modelli, è sufficiente cambiare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" a TemplateIDs sopra.  Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph su come [creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda generale.

### <a name="example-hospital-template-extension-script"></a>Esempio: script estensione modello ospedaliero

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
              "displayName": "Women’s Health",
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

## <a name="related-topics"></a>Argomenti correlati

[Introduzione ai modelli di Teams](../../get-started-with-teams-templates.md)

[Guida introduttiva a Teams per le organizzazioni del settore sanitario](teams-in-hc.md)
