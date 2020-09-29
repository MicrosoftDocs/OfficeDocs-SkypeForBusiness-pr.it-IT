---
title: Modelli per organizzazioni sanitarie
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: USA i modelli di Microsoft teams per creare rapidamente e facilmente teams fornendo un modello predefinito di impostazioni, canali e app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2ef6bd4bf358a90654e7fda643effbfcc34b3c2
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294438"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations-using-microsoft-graph"></a><span data-ttu-id="302d5-103">Introduzione ai modelli di team per organizzazioni sanitarie con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="302d5-103">Get started with Teams templates for Healthcare organizations using Microsoft Graph</span></span>

<span data-ttu-id="302d5-104">I modelli di Microsoft teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="302d5-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="302d5-105">Per le organizzazioni sanitarie, i modelli possono essere particolarmente potenti, poiché consentono agli utenti di essere orientati con l'uso efficace dei team.</span><span class="sxs-lookup"><span data-stu-id="302d5-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="302d5-106">I modelli consentono inoltre agli amministratori di distribuire Team coerenti tra le rispettive organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="302d5-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="302d5-107">Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="302d5-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="302d5-108">Attualmente offriamo due modelli di assistenza sanitaria di prima parte che puoi usare per varie situazioni.</span><span class="sxs-lookup"><span data-stu-id="302d5-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="302d5-109">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](../../get-started-with-teams-templates.md)di team.</span><span class="sxs-lookup"><span data-stu-id="302d5-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="302d5-110">Modello di Ward</span><span class="sxs-lookup"><span data-stu-id="302d5-110">Ward template</span></span>

<span data-ttu-id="302d5-111">Il modello Ward è concepito per la comunicazione e la collaborazione all'interno di un reparto, un pod o un dipartimento.</span><span class="sxs-lookup"><span data-stu-id="302d5-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="302d5-112">Il modello può essere usato per facilitare la gestione dei pazienti, oltre che per le esigenze operative di un reparto.</span><span class="sxs-lookup"><span data-stu-id="302d5-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="302d5-113">Ad esempio, gli annunci di Ward possono essere pubblicati nel canale *annunci* e i turni possono essere gestiti in *personale*.</span><span class="sxs-lookup"><span data-stu-id="302d5-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="302d5-114">Se stai cercando di semplificare le operazioni di Ward, questo modello è adatto a te.</span><span class="sxs-lookup"><span data-stu-id="302d5-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="302d5-115">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="302d5-115">Base Template Type</span></span> |<span data-ttu-id="302d5-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="302d5-116">baseTemplateId</span></span> |<span data-ttu-id="302d5-117">Canali del modello previsto</span><span class="sxs-lookup"><span data-stu-id="302d5-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="302d5-118">Assistenza sanitaria-Ward</span><span class="sxs-lookup"><span data-stu-id="302d5-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="302d5-119">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="302d5-119">Announcements\*</span></span> <br> <span data-ttu-id="302d5-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="302d5-120">Huddles\*</span></span> <br> <span data-ttu-id="302d5-121">Arrotonda\*</span><span class="sxs-lookup"><span data-stu-id="302d5-121">Rounds\*</span></span> <br> <span data-ttu-id="302d5-122">Personale\*</span><span class="sxs-lookup"><span data-stu-id="302d5-122">Staffing\*</span></span> <br> <span data-ttu-id="302d5-123">Formazione\*</span><span class="sxs-lookup"><span data-stu-id="302d5-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="302d5-124">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="302d5-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="302d5-125">Modello di ospedale</span><span class="sxs-lookup"><span data-stu-id="302d5-125">Hospital template</span></span>

<span data-ttu-id="302d5-126">Il modello Hospital è pensato per la comunicazione e la collaborazione tra più rioni, baccelli e reparti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="302d5-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="302d5-127">Sono inclusi in questo modello diversi canali operativi, tra cui *annunci*, *custodia*e *farmacia*, ma forniamo anche uno script sotto il quale estende il modello con un'ampia varietà di canali aggiuntivi di reparto o di specialità che è possibile aggiungere, eliminare o modificare a piacimento.</span><span class="sxs-lookup"><span data-stu-id="302d5-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="302d5-128">Ad esempio, se si ha un reparto di *endocrinologia* , ma non è necessario un canale per l' *Oftalmologia*, lo script può essere adattato per includere un canale di *endocrinologia* e rimuovere il canale di *Oftalmologia* .</span><span class="sxs-lookup"><span data-stu-id="302d5-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="302d5-129">Per evitare la saturazione delle notifiche, è consigliabile che questi canali con modelli di specialità o di rione non siano preferiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="302d5-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="302d5-130">Gli utenti in genere hanno favorito tutti i canali che trovano rilevanti.</span><span class="sxs-lookup"><span data-stu-id="302d5-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="302d5-131">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="302d5-131">Base Template Type</span></span> |<span data-ttu-id="302d5-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="302d5-132">baseTemplateId</span></span> |<span data-ttu-id="302d5-133">Canali del modello previsto</span><span class="sxs-lookup"><span data-stu-id="302d5-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="302d5-134">Healthcare-Hospital</span><span class="sxs-lookup"><span data-stu-id="302d5-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="302d5-135">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="302d5-135">Announcements\*</span></span> <br> <span data-ttu-id="302d5-136">Conformità\*</span><span class="sxs-lookup"><span data-stu-id="302d5-136">Compliance\*</span></span> <br> <span data-ttu-id="302d5-137">Custodia</span><span class="sxs-lookup"><span data-stu-id="302d5-137">Custodial</span></span> <br> <span data-ttu-id="302d5-138">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="302d5-138">Human Resources</span></span> <br> <span data-ttu-id="302d5-139">Farmacia</span><span class="sxs-lookup"><span data-stu-id="302d5-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="302d5-140">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="302d5-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="302d5-141">Come usare i modelli di First-Party</span><span class="sxs-lookup"><span data-stu-id="302d5-141">How to use first-party templates</span></span>

<span data-ttu-id="302d5-142">Per usare questi modelli, è sufficiente modificare la proprietà "template@odata. bind" nel corpo della richiesta da "standard" a TemplateIDs sopra.</span><span class="sxs-lookup"><span data-stu-id="302d5-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="302d5-143">Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph su come [creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="302d5-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="302d5-144">I canali nel modello verranno creati automaticamente nella scheda generale.</span><span class="sxs-lookup"><span data-stu-id="302d5-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="302d5-145">Esempio: script estensione modello ospedaliero</span><span class="sxs-lookup"><span data-stu-id="302d5-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="302d5-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="302d5-146">Related topics</span></span>

[<span data-ttu-id="302d5-147">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="302d5-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="302d5-148">Guida introduttiva a Teams per le organizzazioni del settore sanitario</span><span class="sxs-lookup"><span data-stu-id="302d5-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="302d5-149">Introduzione ai modelli di teams nella console di amministrazione</span><span class="sxs-lookup"><span data-stu-id="302d5-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
