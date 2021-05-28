---
title: Creare un team usando i modelli sanitari
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
description: Usare i modelli di team nell'interfaccia di amministrazione o con Microsoft Graph creare rapidamente e facilmente i team fornendo un modello predefinito di impostazioni, canali e app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684353"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="ea23e-103">Usare i modelli di un team di assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="ea23e-103">Use a healthcare team templates</span></span>

<span data-ttu-id="ea23e-104">I modelli consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="ea23e-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ea23e-105">Per le organizzazioni sanitarie, i modelli possono essere particolarmente efficaci, in quanto forniscono agli utenti una struttura che consente agli utenti di orientarsi su come usare in modo efficace Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ea23e-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="ea23e-106">In più, i modelli consentono agli amministratori di implementare team coerenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea23e-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="ea23e-107">Questo articolo è per i responsabili dedicati alla pianificazione, all'implementazione e alla gestione di più team nell'organizzazione del settore sanitario.</span><span class="sxs-lookup"><span data-stu-id="ea23e-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="ea23e-108">Scegliere un metodo per creare team con i modelli di assistenza sanitaria del team:</span><span class="sxs-lookup"><span data-stu-id="ea23e-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="ea23e-109">Chi</span><span class="sxs-lookup"><span data-stu-id="ea23e-109">Who</span></span> | <span data-ttu-id="ea23e-110">Metodo da usare:</span><span class="sxs-lookup"><span data-stu-id="ea23e-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="ea23e-111">Amministratori e professionisti IT</span><span class="sxs-lookup"><span data-stu-id="ea23e-111">Admins and IT Professionals</span></span> | <span data-ttu-id="ea23e-112">[Usare l'Teams di amministrazione per](#use-the-team-templates-in-the-admin-center) creare team basati sui modelli del team sanitario.</span><span class="sxs-lookup"><span data-stu-id="ea23e-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="ea23e-113">Sviluppatori e integratori di sistemi</span><span class="sxs-lookup"><span data-stu-id="ea23e-113">Developers and systems integrators</span></span> | <span data-ttu-id="ea23e-114">[Usare microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) per creare un team basato sui modelli del team sanitario.</span><span class="sxs-lookup"><span data-stu-id="ea23e-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="ea23e-115">Usare i modelli di team nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="ea23e-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="ea23e-116">Microsoft Teams amministratori possono usare l'Teams di amministrazione per creare team con i modelli di team.</span><span class="sxs-lookup"><span data-stu-id="ea23e-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="ea23e-117">Attualmente sono disponibili due modelli del produttore per il settore sanitario da usare in diverse situazioni.</span><span class="sxs-lookup"><span data-stu-id="ea23e-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="ea23e-118">Per altre informazioni sui modelli di team in generale, vedere Introduzione ai [modelli di team nell'interfaccia di amministrazione.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="ea23e-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="ea23e-119">Collaborare all'assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="ea23e-119">Collaborate on patient care</span></span>

 <span data-ttu-id="ea23e-120">Semplificare le comunicazioni e la collaborazione nell'assistenza sanitaria all'interno di un reparto, un dispensario o un dipartimento.</span><span class="sxs-lookup"><span data-stu-id="ea23e-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="ea23e-121">Il modello può essere usato per agevolare la gestione dei pazienti e le esigenze operative di un reparto.</span><span class="sxs-lookup"><span data-stu-id="ea23e-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="ea23e-122">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-122">Base template type</span></span> |<span data-ttu-id="ea23e-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ea23e-123">baseTemplateId</span></span>| <span data-ttu-id="ea23e-124">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="ea23e-125">Collaborare all'assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="ea23e-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="ea23e-126">Canali:</span><span class="sxs-lookup"><span data-stu-id="ea23e-126">Channels:</span></span><ul><li><span data-ttu-id="ea23e-127">Generale</span><span class="sxs-lookup"><span data-stu-id="ea23e-127">General</span></span></li><li><span data-ttu-id="ea23e-128">Annunci</span><span class="sxs-lookup"><span data-stu-id="ea23e-128">Announcements</span></span></li><li><span data-ttu-id="ea23e-129">Briefing</span><span class="sxs-lookup"><span data-stu-id="ea23e-129">Huddles</span></span></li><li><span data-ttu-id="ea23e-130">Giri di visite</span><span class="sxs-lookup"><span data-stu-id="ea23e-130">Rounds</span></span></li><li><span data-ttu-id="ea23e-131">Personale</span><span class="sxs-lookup"><span data-stu-id="ea23e-131">Staffing</span></span></li><li><span data-ttu-id="ea23e-132">Formazione</span><span class="sxs-lookup"><span data-stu-id="ea23e-132">Training</span></span></li></ul> <span data-ttu-id="ea23e-133">App:</span><span class="sxs-lookup"><span data-stu-id="ea23e-133">Apps:</span></span> <ul><li><span data-ttu-id="ea23e-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="ea23e-134">Wiki</span></span></li><li><span data-ttu-id="ea23e-135">Elenchi</span><span class="sxs-lookup"><span data-stu-id="ea23e-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="ea23e-136">Ospedale</span><span class="sxs-lookup"><span data-stu-id="ea23e-136">Hospital</span></span>

<span data-ttu-id="ea23e-137">Semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="ea23e-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="ea23e-138">Questo modello include un set di canali di base per le operazioni ospedaliere e può essere esteso automaticamente in modo da includere specializzazioni, ad hoc.</span><span class="sxs-lookup"><span data-stu-id="ea23e-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="ea23e-139">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-139">Base template type</span></span> |<span data-ttu-id="ea23e-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ea23e-140">baseTemplateId</span></span> | <span data-ttu-id="ea23e-141">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="ea23e-142">Ospedale</span><span class="sxs-lookup"><span data-stu-id="ea23e-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="ea23e-143">Canali:</span><span class="sxs-lookup"><span data-stu-id="ea23e-143">Channels:</span></span> <ul><li><span data-ttu-id="ea23e-144">Generale</span><span class="sxs-lookup"><span data-stu-id="ea23e-144">General</span></span></li><li><span data-ttu-id="ea23e-145">Annunci</span><span class="sxs-lookup"><span data-stu-id="ea23e-145">Announcements</span></span></li><li><span data-ttu-id="ea23e-146">Conformità</span><span class="sxs-lookup"><span data-stu-id="ea23e-146">Compliance</span></span></li><li><span data-ttu-id="ea23e-147">Pulizie</span><span class="sxs-lookup"><span data-stu-id="ea23e-147">Custodial</span></span></li><li><span data-ttu-id="ea23e-148">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="ea23e-148">Human resources</span></span></li><li><span data-ttu-id="ea23e-149">Farmacia</span><span class="sxs-lookup"><span data-stu-id="ea23e-149">Pharmacy</span></span></li></ul> <span data-ttu-id="ea23e-150">App:</span><span class="sxs-lookup"><span data-stu-id="ea23e-150">Apps:</span></span> <ul><li><span data-ttu-id="ea23e-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="ea23e-151">Wiki</span></span></li><li><span data-ttu-id="ea23e-152">Elenchi</span><span class="sxs-lookup"><span data-stu-id="ea23e-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="ea23e-153">Usare i modelli del team con microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ea23e-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="ea23e-154">Gli sviluppatori possono usare microsoft Graph per creare team con i modelli di team.</span><span class="sxs-lookup"><span data-stu-id="ea23e-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="ea23e-155">Attualmente sono disponibili due modelli del produttore per il settore sanitario da usare in diverse situazioni.</span><span class="sxs-lookup"><span data-stu-id="ea23e-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="ea23e-156">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di team.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="ea23e-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="ea23e-157">Per informazioni sui modelli di team e sul tipo di Graph Microsoft, vedere panoramica [dell'API](/graph/teams-concept-overview?view=graph-rest-1.0) Microsoft Teams e tipo di risorsa [teamsTemplate.](/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="ea23e-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="ea23e-158">Modello di reparto</span><span class="sxs-lookup"><span data-stu-id="ea23e-158">Ward template</span></span>

<span data-ttu-id="ea23e-159">Il modello di reparto è destinato alla comunicazione e alla collaborazione all'interno di un reparto, un dispensario o un dipartimento.</span><span class="sxs-lookup"><span data-stu-id="ea23e-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="ea23e-160">Il modello può essere usato per agevolare la gestione dei pazienti oltre alle esigenze operative di un reparto.</span><span class="sxs-lookup"><span data-stu-id="ea23e-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="ea23e-161">Ad esempio, gli annunci di reparto possono essere pubblicati nel canale *Annunci* e i turni possono essere gestiti in *Personale*.</span><span class="sxs-lookup"><span data-stu-id="ea23e-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="ea23e-162">Questo modello è utile per semplificare l’operatività di reparto.</span><span class="sxs-lookup"><span data-stu-id="ea23e-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="ea23e-163">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-163">Base Template Type</span></span> |<span data-ttu-id="ea23e-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ea23e-164">baseTemplateId</span></span> |<span data-ttu-id="ea23e-165">Canali del modello di base</span><span class="sxs-lookup"><span data-stu-id="ea23e-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="ea23e-166">Settore sanitario - Reparto</span><span class="sxs-lookup"><span data-stu-id="ea23e-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="ea23e-167">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-167">Announcements\*</span></span> <br> <span data-ttu-id="ea23e-168">Briefing\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-168">Huddles\*</span></span> <br> <span data-ttu-id="ea23e-169">Giri di visite\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-169">Rounds\*</span></span> <br> <span data-ttu-id="ea23e-170">Personale\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-170">Staffing\*</span></span> <br> <span data-ttu-id="ea23e-171">Formazione\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="ea23e-172">\* Aggiunto automaticamente ai Preferiti</span><span class="sxs-lookup"><span data-stu-id="ea23e-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="ea23e-173">Modello ospedale</span><span class="sxs-lookup"><span data-stu-id="ea23e-173">Hospital template</span></span>

<span data-ttu-id="ea23e-174">Il modello ospedale mira a semplificare le comunicazioni e la collaborazione tra più reparti, dispensari e dipartimenti all'interno di un ospedale.</span><span class="sxs-lookup"><span data-stu-id="ea23e-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="ea23e-175">Questo modello è incluso in diversi canali operativi, tra cui *Annunci*, *Pulizie* e *Farmacia*, ma di seguito viene fornito uno script che estende il modello con un'ampia varietà di altri canali incentrati su reparti o specializzazioni che è possibile aggiungere, eliminare o modificare in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea23e-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="ea23e-176">Ad esempio, se si ha un dipartimento di *Endocrinologia*, ma non è necessario un canale per *Oftalmologia*, lo script può essere adattato in modo da includere un canale *Endocrinologia* e rimuovere il canale *Oftalmologia*.</span><span class="sxs-lookup"><span data-stu-id="ea23e-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="ea23e-177">Per evitare la saturazione delle notifiche, è consigliabile non aggiungere automaticamente ai Preferiti questi canali incentrati su specializzazioni o reparti.</span><span class="sxs-lookup"><span data-stu-id="ea23e-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="ea23e-178">Gli utenti in genere aggiungono ai Preferiti i canali che trovano pertinenti.</span><span class="sxs-lookup"><span data-stu-id="ea23e-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="ea23e-179">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="ea23e-179">Base Template Type</span></span> |<span data-ttu-id="ea23e-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ea23e-180">baseTemplateId</span></span> |<span data-ttu-id="ea23e-181">Canali del modello di base</span><span class="sxs-lookup"><span data-stu-id="ea23e-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="ea23e-182">Settore sanitario - Ospedale</span><span class="sxs-lookup"><span data-stu-id="ea23e-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="ea23e-183">Annunci\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-183">Announcements\*</span></span> <br> <span data-ttu-id="ea23e-184">Conformità\*</span><span class="sxs-lookup"><span data-stu-id="ea23e-184">Compliance\*</span></span> <br> <span data-ttu-id="ea23e-185">Pulizie</span><span class="sxs-lookup"><span data-stu-id="ea23e-185">Custodial</span></span> <br> <span data-ttu-id="ea23e-186">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="ea23e-186">Human Resources</span></span> <br> <span data-ttu-id="ea23e-187">Farmacia</span><span class="sxs-lookup"><span data-stu-id="ea23e-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="ea23e-188">\* Aggiunto automaticamente ai Preferiti</span><span class="sxs-lookup"><span data-stu-id="ea23e-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="ea23e-189">Come usare i modelli del produttore</span><span class="sxs-lookup"><span data-stu-id="ea23e-189">How to use first-party templates</span></span>

<span data-ttu-id="ea23e-190">Per usare questi modelli, è sufficiente modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti.</span><span class="sxs-lookup"><span data-stu-id="ea23e-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="ea23e-191">Per altre informazioni su come distribuire i modelli di team, vedere l'articolo microsoft Graph su come [creare un team.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="ea23e-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="ea23e-192">I canali nel modello verranno creati automaticamente nella scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="ea23e-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="ea23e-193">Esempio: script di estensione del modello ospedale</span><span class="sxs-lookup"><span data-stu-id="ea23e-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="ea23e-194">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ea23e-194">Related topics</span></span>

[<span data-ttu-id="ea23e-195">Introduzione ai modelli di team</span><span class="sxs-lookup"><span data-stu-id="ea23e-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="ea23e-196">Introduzione al team per le organizzazioni sanitarie</span><span class="sxs-lookup"><span data-stu-id="ea23e-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)