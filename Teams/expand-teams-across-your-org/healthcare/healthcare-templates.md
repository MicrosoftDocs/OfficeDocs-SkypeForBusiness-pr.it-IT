---
title: Modelli per le organizzazioni sanitarie
author: serdarsoysal
ms.author: serdars
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
description: Usare i modelli di Microsoft Teams con Microsoft Graph per creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c2e10efbff98150b120d1c026d4d810629333f2
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790408"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="2ede6-103">Introduzione ai modelli di Teams per le organizzazioni sanitarie</span><span class="sxs-lookup"><span data-stu-id="2ede6-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="2ede6-104">I modelli di Microsoft Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="2ede6-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2ede6-105">Per le organizzazioni sanitarie, i modelli possono essere particolarmente potenti perché forniscono una struttura che gli utenti possano orientarsi nell'uso efficace di Teams.</span><span class="sxs-lookup"><span data-stu-id="2ede6-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="2ede6-106">I modelli consentono inoltre agli amministratori di distribuire team coerenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ede6-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="2ede6-107">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team nell'intera organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="2ede6-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="2ede6-108">Attualmente sono disponibili due modelli sanitari di prima scelta da usare per diverse situazioni.</span><span class="sxs-lookup"><span data-stu-id="2ede6-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="2ede6-109">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="2ede6-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="2ede6-110">Modello Di modelli</span><span class="sxs-lookup"><span data-stu-id="2ede6-110">Ward template</span></span>

<span data-ttu-id="2ede6-111">Il modello modello è pensato per essere utilizzato per le comunicazioni e la collaborazione all'interno di un pod o di un dipartimento.</span><span class="sxs-lookup"><span data-stu-id="2ede6-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="2ede6-112">Il modello può essere usato per facilitare la gestione dei pazienti, nonché per le esigenze operative di una organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ede6-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="2ede6-113">Ad esempio, gli annunci di annunci possono essere pubblicati *nel* canale Annunci e i turni possono essere gestiti in *Staffing.*</span><span class="sxs-lookup"><span data-stu-id="2ede6-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="2ede6-114">Questo modello è utile per semplificare le operazioni di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ede6-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="2ede6-115">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="2ede6-115">Base Template Type</span></span> |<span data-ttu-id="2ede6-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2ede6-116">baseTemplateId</span></span> |<span data-ttu-id="2ede6-117">Canali dei modelli di previsione</span><span class="sxs-lookup"><span data-stu-id="2ede6-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2ede6-118">Sanità - Assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="2ede6-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="2ede6-119">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-119">Announcements\*</span></span> <br> <span data-ttu-id="2ede6-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-120">Huddles\*</span></span> <br> <span data-ttu-id="2ede6-121">Arrotondamenti\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-121">Rounds\*</span></span> <br> <span data-ttu-id="2ede6-122">Personale\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-122">Staffing\*</span></span> <br> <span data-ttu-id="2ede6-123">Formazione\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="2ede6-124">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="2ede6-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="2ede6-125">Modello Ospedale</span><span class="sxs-lookup"><span data-stu-id="2ede6-125">Hospital template</span></span>

<span data-ttu-id="2ede6-126">Il modello ospedale è pensato per comunicare e collaborare tra più reparti, pod e dipartimenti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="2ede6-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="2ede6-127">In questo modello sono inclusi diversi canali operativi, tra cui *Annunci,* Responsabile e Farmacia, ma di seguito viene fornito uno script che estende il modello con diversi canali di reparto o specializzati che è possibile aggiungere, eliminare o modificare in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="2ede6-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="2ede6-128">Ad esempio, se si ha un reparto di *Endocrinology,* ma non è necessario un canale per *Ophthalmology,* lo script può essere adattato per includere un canale *endocrinology* e rimuovere il canale *Ophthalmology.*</span><span class="sxs-lookup"><span data-stu-id="2ede6-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="2ede6-129">È consigliabile non aggiungere automaticamente ai preferiti questi canali specializzati o modellati, per evitare la saturazione delle notifiche.</span><span class="sxs-lookup"><span data-stu-id="2ede6-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="2ede6-130">Gli utenti in genere hanno preferito i canali pertinenti.</span><span class="sxs-lookup"><span data-stu-id="2ede6-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="2ede6-131">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="2ede6-131">Base Template Type</span></span> |<span data-ttu-id="2ede6-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2ede6-132">baseTemplateId</span></span> |<span data-ttu-id="2ede6-133">Canali dei modelli di previsione</span><span class="sxs-lookup"><span data-stu-id="2ede6-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2ede6-134">Sanità - Ospedale</span><span class="sxs-lookup"><span data-stu-id="2ede6-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="2ede6-135">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-135">Announcements\*</span></span> <br> <span data-ttu-id="2ede6-136">Conformità\*</span><span class="sxs-lookup"><span data-stu-id="2ede6-136">Compliance\*</span></span> <br> <span data-ttu-id="2ede6-137">Responsabile</span><span class="sxs-lookup"><span data-stu-id="2ede6-137">Custodial</span></span> <br> <span data-ttu-id="2ede6-138">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2ede6-138">Human Resources</span></span> <br> <span data-ttu-id="2ede6-139">Farmacia</span><span class="sxs-lookup"><span data-stu-id="2ede6-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="2ede6-140">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="2ede6-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="2ede6-141">Come usare i modelli di prima parte</span><span class="sxs-lookup"><span data-stu-id="2ede6-141">How to use first-party templates</span></span>

<span data-ttu-id="2ede6-142">Per usare questi modelli, basta modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID indicati sopra.</span><span class="sxs-lookup"><span data-stu-id="2ede6-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="2ede6-143">Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="2ede6-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="2ede6-144">I canali nel modello verranno creati automaticamente nella scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="2ede6-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="2ede6-145">Esempio: Script di estensione del modello Hospital</span><span class="sxs-lookup"><span data-stu-id="2ede6-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="2ede6-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2ede6-146">Related topics</span></span>

[<span data-ttu-id="2ede6-147">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="2ede6-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="2ede6-148">Guida introduttiva a Teams per le organizzazioni del settore sanitario</span><span class="sxs-lookup"><span data-stu-id="2ede6-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="2ede6-149">Introduzione ai modelli di Teams nella console di amministrazione</span><span class="sxs-lookup"><span data-stu-id="2ede6-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
