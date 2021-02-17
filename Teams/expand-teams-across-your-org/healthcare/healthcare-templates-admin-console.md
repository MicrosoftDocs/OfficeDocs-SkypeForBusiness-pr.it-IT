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
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="78a04-103">Creare un team usando i modelli sanitari di Teams</span><span class="sxs-lookup"><span data-stu-id="78a04-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="78a04-104">I modelli di Microsoft Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="78a04-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="78a04-105">Per le organizzazioni sanitarie, i modelli possono essere particolarmente potenti perché forniscono una struttura che gli utenti possano orientarsi nell'uso efficace di Teams.</span><span class="sxs-lookup"><span data-stu-id="78a04-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="78a04-106">I modelli consentono inoltre agli amministratori di distribuire team coerenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78a04-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="78a04-107">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team nell'intera organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="78a04-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="78a04-108">Scegliere un metodo per creare team con i modelli sanitari di Teams:</span><span class="sxs-lookup"><span data-stu-id="78a04-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="78a04-109">Chi</span><span class="sxs-lookup"><span data-stu-id="78a04-109">Who</span></span> | <span data-ttu-id="78a04-110">Metodo da usare:</span><span class="sxs-lookup"><span data-stu-id="78a04-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="78a04-111">Amministratori e professionisti IT</span><span class="sxs-lookup"><span data-stu-id="78a04-111">Admins and IT Professionals</span></span> | <span data-ttu-id="78a04-112">[Usare l'interfaccia di amministrazione di Teams](#use-the-teams-templates-in-the-teams-admin-center) per creare team basati sui modelli di Teams sanitari.</span><span class="sxs-lookup"><span data-stu-id="78a04-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="78a04-113">Sviluppatori e system di integrazione</span><span class="sxs-lookup"><span data-stu-id="78a04-113">Developers and systems integrators</span></span> | <span data-ttu-id="78a04-114">[Usare Microsoft Graph per](#use-the-teams-templates-with-the-microsoft-graph) creare team basati sui modelli di Teams sanitari.</span><span class="sxs-lookup"><span data-stu-id="78a04-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="78a04-115">Usare i modelli di Teams nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="78a04-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="78a04-116">Gli amministratori di Microsoft Teams possono usare l'interfaccia di amministrazione di Teams per creare team con i modelli di Teams.</span><span class="sxs-lookup"><span data-stu-id="78a04-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="78a04-117">Attualmente sono disponibili due modelli sanitari di prima scelta da usare per diverse situazioni.</span><span class="sxs-lookup"><span data-stu-id="78a04-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="78a04-118">Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams nell'interfaccia di amministrazione.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="78a04-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="78a04-119">Collaborare all'assistenza pazienti</span><span class="sxs-lookup"><span data-stu-id="78a04-119">Collaborate on patient care</span></span>

 <span data-ttu-id="78a04-120">Semplificare la comunicazione e la collaborazione sanitaria all'interno di un pod o di un dipartimento.</span><span class="sxs-lookup"><span data-stu-id="78a04-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="78a04-121">Il modello può essere usato per facilitare la gestione dei pazienti e le esigenze operative di una azienda.</span><span class="sxs-lookup"><span data-stu-id="78a04-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="78a04-122">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="78a04-122">Base template type</span></span> |<span data-ttu-id="78a04-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="78a04-123">baseTemplateId</span></span>| <span data-ttu-id="78a04-124">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="78a04-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="78a04-125">Collaborare all'assistenza pazienti</span><span class="sxs-lookup"><span data-stu-id="78a04-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="78a04-126">Canali:</span><span class="sxs-lookup"><span data-stu-id="78a04-126">Channels:</span></span><ul><li><span data-ttu-id="78a04-127">Generale</span><span class="sxs-lookup"><span data-stu-id="78a04-127">General</span></span></li><li><span data-ttu-id="78a04-128">Annunci</span><span class="sxs-lookup"><span data-stu-id="78a04-128">Announcements</span></span></li><li><span data-ttu-id="78a04-129">Huddles</span><span class="sxs-lookup"><span data-stu-id="78a04-129">Huddles</span></span></li><li><span data-ttu-id="78a04-130">Arrotondamenti</span><span class="sxs-lookup"><span data-stu-id="78a04-130">Rounds</span></span></li><li><span data-ttu-id="78a04-131">Personale</span><span class="sxs-lookup"><span data-stu-id="78a04-131">Staffing</span></span></li><li><span data-ttu-id="78a04-132">Formazione</span><span class="sxs-lookup"><span data-stu-id="78a04-132">Training</span></span></li></ul> <span data-ttu-id="78a04-133">App:</span><span class="sxs-lookup"><span data-stu-id="78a04-133">Apps:</span></span> <ul><li><span data-ttu-id="78a04-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="78a04-134">Wiki</span></span></li><li><span data-ttu-id="78a04-135">Elenchi</span><span class="sxs-lookup"><span data-stu-id="78a04-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="78a04-136">Ospedale</span><span class="sxs-lookup"><span data-stu-id="78a04-136">Hospital</span></span>

<span data-ttu-id="78a04-137">Semplificare la comunicazione e la collaborazione tra più reparti, pod e dipartimenti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="78a04-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="78a04-138">Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso per includere specializzazioni, ad hoc.</span><span class="sxs-lookup"><span data-stu-id="78a04-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="78a04-139">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="78a04-139">Base template type</span></span> |<span data-ttu-id="78a04-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="78a04-140">baseTemplateId</span></span> | <span data-ttu-id="78a04-141">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="78a04-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="78a04-142">Ospedale</span><span class="sxs-lookup"><span data-stu-id="78a04-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="78a04-143">Canali:</span><span class="sxs-lookup"><span data-stu-id="78a04-143">Channels:</span></span> <ul><li><span data-ttu-id="78a04-144">Generale</span><span class="sxs-lookup"><span data-stu-id="78a04-144">General</span></span></li><li><span data-ttu-id="78a04-145">Annunci</span><span class="sxs-lookup"><span data-stu-id="78a04-145">Announcements</span></span></li><li><span data-ttu-id="78a04-146">Conformità</span><span class="sxs-lookup"><span data-stu-id="78a04-146">Compliance</span></span></li><li><span data-ttu-id="78a04-147">Responsabile</span><span class="sxs-lookup"><span data-stu-id="78a04-147">Custodial</span></span></li><li><span data-ttu-id="78a04-148">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="78a04-148">Human resources</span></span></li><li><span data-ttu-id="78a04-149">Farmacia</span><span class="sxs-lookup"><span data-stu-id="78a04-149">Pharmacy</span></span></li></ul> <span data-ttu-id="78a04-150">App:</span><span class="sxs-lookup"><span data-stu-id="78a04-150">Apps:</span></span> <ul><li><span data-ttu-id="78a04-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="78a04-151">Wiki</span></span></li><li><span data-ttu-id="78a04-152">Elenchi</span><span class="sxs-lookup"><span data-stu-id="78a04-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="78a04-153">Usare i modelli di Teams con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="78a04-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="78a04-154">Gli sviluppatori possono usare Microsoft Graph per creare team con i modelli di Teams.</span><span class="sxs-lookup"><span data-stu-id="78a04-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="78a04-155">Attualmente sono disponibili due modelli sanitari di prima scelta da usare per diverse situazioni.</span><span class="sxs-lookup"><span data-stu-id="78a04-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="78a04-156">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="78a04-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="78a04-157">Per informazioni sui modelli di Teams e su Microsoft Graph, vedere la panoramica [dell'API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) di Microsoft Teams e il tipo [di risorsa teamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="78a04-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="78a04-158">Modello Di modelli</span><span class="sxs-lookup"><span data-stu-id="78a04-158">Ward template</span></span>

<span data-ttu-id="78a04-159">Il modello modello è pensato per essere utilizzato per le comunicazioni e la collaborazione all'interno di un progetto, un pod o un reparto.</span><span class="sxs-lookup"><span data-stu-id="78a04-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="78a04-160">Il modello può essere usato per facilitare la gestione dei pazienti, nonché per le esigenze operative di una organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78a04-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="78a04-161">Ad esempio, gli annunci di annunci possono essere pubblicati *nel* canale Annunci e i turni possono essere gestiti in *Staffing.*</span><span class="sxs-lookup"><span data-stu-id="78a04-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="78a04-162">Questo modello è utile per semplificare le operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="78a04-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="78a04-163">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="78a04-163">Base Template Type</span></span> |<span data-ttu-id="78a04-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="78a04-164">baseTemplateId</span></span> |<span data-ttu-id="78a04-165">Canali dei modelli di previsione</span><span class="sxs-lookup"><span data-stu-id="78a04-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="78a04-166">Sanità - Assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="78a04-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="78a04-167">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="78a04-167">Announcements\*</span></span> <br> <span data-ttu-id="78a04-168">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="78a04-168">Huddles\*</span></span> <br> <span data-ttu-id="78a04-169">Arrotondamenti\*</span><span class="sxs-lookup"><span data-stu-id="78a04-169">Rounds\*</span></span> <br> <span data-ttu-id="78a04-170">Personale\*</span><span class="sxs-lookup"><span data-stu-id="78a04-170">Staffing\*</span></span> <br> <span data-ttu-id="78a04-171">Formazione\*</span><span class="sxs-lookup"><span data-stu-id="78a04-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="78a04-172">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="78a04-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="78a04-173">Modello Ospedale</span><span class="sxs-lookup"><span data-stu-id="78a04-173">Hospital template</span></span>

<span data-ttu-id="78a04-174">Il modello ospedale è pensato per comunicare e collaborare tra più reparti, pod e dipartimenti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="78a04-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="78a04-175">In questo modello sono inclusi diversi canali operativi, tra cui *Annunci,* Responsabile e Farmacia, ma di seguito viene fornito uno script che estende il modello con diversi canali di reparto o specializzati che è possibile aggiungere, eliminare o modificare in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="78a04-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="78a04-176">Ad esempio, se si ha un reparto di *Endocrinology,* ma non è necessario un canale per *Ophthalmology,* lo script può essere adattato per includere un canale *endocrinology* e rimuovere il canale *Ophthalmology.*</span><span class="sxs-lookup"><span data-stu-id="78a04-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="78a04-177">È consigliabile non aggiungere automaticamente ai preferiti questi canali specializzati o modellati, per evitare la saturazione delle notifiche.</span><span class="sxs-lookup"><span data-stu-id="78a04-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="78a04-178">Gli utenti in genere hanno preferito i canali pertinenti.</span><span class="sxs-lookup"><span data-stu-id="78a04-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="78a04-179">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="78a04-179">Base Template Type</span></span> |<span data-ttu-id="78a04-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="78a04-180">baseTemplateId</span></span> |<span data-ttu-id="78a04-181">Canali dei modelli di previsione</span><span class="sxs-lookup"><span data-stu-id="78a04-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="78a04-182">Sanità - Ospedale</span><span class="sxs-lookup"><span data-stu-id="78a04-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="78a04-183">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="78a04-183">Announcements\*</span></span> <br> <span data-ttu-id="78a04-184">Conformità\*</span><span class="sxs-lookup"><span data-stu-id="78a04-184">Compliance\*</span></span> <br> <span data-ttu-id="78a04-185">Responsabile</span><span class="sxs-lookup"><span data-stu-id="78a04-185">Custodial</span></span> <br> <span data-ttu-id="78a04-186">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="78a04-186">Human Resources</span></span> <br> <span data-ttu-id="78a04-187">Farmacia</span><span class="sxs-lookup"><span data-stu-id="78a04-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="78a04-188">\* Preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="78a04-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="78a04-189">Come usare i modelli di prima parte</span><span class="sxs-lookup"><span data-stu-id="78a04-189">How to use first-party templates</span></span>

<span data-ttu-id="78a04-190">Per usare questi modelli, basta modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID riportati sopra.</span><span class="sxs-lookup"><span data-stu-id="78a04-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="78a04-191">Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="78a04-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="78a04-192">I canali nel modello verranno creati automaticamente nella scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="78a04-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="78a04-193">Esempio: Script di estensione del modello Hospital</span><span class="sxs-lookup"><span data-stu-id="78a04-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="78a04-194">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="78a04-194">Related topics</span></span>

[<span data-ttu-id="78a04-195">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="78a04-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="78a04-196">Guida introduttiva a Teams per le organizzazioni del settore sanitario</span><span class="sxs-lookup"><span data-stu-id="78a04-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
