---
title: Teams modelli per piccole e medie imprese creati con Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Usare Microsoft Teams predefiniti predefiniti di Microsoft Graph creare rapidamente e facilmente team per piccole e medie imprese.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116994"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="6cffa-103">Teams modelli predefiniti di Microsoft Graph per le piccole e medie imprese</span><span class="sxs-lookup"><span data-stu-id="6cffa-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="6cffa-104">I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="6cffa-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6cffa-105">Per le piccole e medie imprese, i modelli possono essere particolarmente efficaci, perché consentono agli amministratori di distribuire rapidamente Teams all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cffa-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="6cffa-106">I modelli aiutano anche a orientare gli utenti e a iniziare a usare Teams efficace.</span><span class="sxs-lookup"><span data-stu-id="6cffa-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="6cffa-107">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cffa-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="6cffa-108">Attualmente sono disponibili tre modelli SMB di prima parte che è possibile sfruttare per un'ampia gamma di situazioni.</span><span class="sxs-lookup"><span data-stu-id="6cffa-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="6cffa-109">Tutti i modelli creeranno *Teams.*</span><span class="sxs-lookup"><span data-stu-id="6cffa-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="6cffa-110">Dopo aver creato il Teams e essere pronti per l'implementazione nell'organizzazione, è possibile impostare la privacy su *A* livello di organizzazione o *Pubblico,* in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6cffa-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="6cffa-111">Per scoprire di più sui modelli dei team in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="6cffa-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="6cffa-112">Company-Wide modello</span><span class="sxs-lookup"><span data-stu-id="6cffa-112">Company-Wide template</span></span>
<span data-ttu-id="6cffa-113">Il modello Company-Wide è destinato alla comunicazione e alla collaborazione rilevanti per l'intera azienda.</span><span class="sxs-lookup"><span data-stu-id="6cffa-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="6cffa-114">È possibile usare il canale Generale per annunci aziendali, notizie di settore o post esecutivi.</span><span class="sxs-lookup"><span data-stu-id="6cffa-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="6cffa-115">Il canale Risorse umane è un'ottima posizione per consolidare tutte le attività correlate alle risorse umane, come post di lavoro, onboarding di nuovi dipendenti, formazione e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6cffa-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="6cffa-116">Il canale Cose divertenti offre una piattaforma social per tutti i post casuali e divertenti.</span><span class="sxs-lookup"><span data-stu-id="6cffa-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="6cffa-117">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-117">Base template type</span></span>  | <span data-ttu-id="6cffa-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6cffa-118">baseTemplateId</span></span> | <span data-ttu-id="6cffa-119">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="6cffa-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="6cffa-120">SMB -</span></span> <br><span data-ttu-id="6cffa-121">A livello aziendale</span><span class="sxs-lookup"><span data-stu-id="6cffa-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="6cffa-122">Canali</span><span class="sxs-lookup"><span data-stu-id="6cffa-122">Channels</span></span> <ul><li><span data-ttu-id="6cffa-123">Generale\*</span><span class="sxs-lookup"><span data-stu-id="6cffa-123">General\*</span></span></li><li><span data-ttu-id="6cffa-124">Risorse umane\*</span><span class="sxs-lookup"><span data-stu-id="6cffa-124">Human Resources\*</span></span></li><li><span data-ttu-id="6cffa-125">Cose divertenti\*</span><span class="sxs-lookup"><span data-stu-id="6cffa-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="6cffa-126">App</span><span class="sxs-lookup"><span data-stu-id="6cffa-126">Apps</span></span><ul><li><span data-ttu-id="6cffa-127">Portale aziendale (sito Web aggiunto al **canale Risorse** umane)</span><span class="sxs-lookup"><span data-stu-id="6cffa-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="6cffa-128">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="6cffa-128">Team properties</span></span> <ul><li><span data-ttu-id="6cffa-129">Visibilità del team impostata su Private</span><span class="sxs-lookup"><span data-stu-id="6cffa-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="6cffa-130">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="6cffa-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="6cffa-131">Per creare il team Company-Wide predefinito dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="6cffa-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="6cffa-132">Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="6cffa-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="6cffa-133">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6cffa-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="6cffa-134">Modello Team per dirigenti</span><span class="sxs-lookup"><span data-stu-id="6cffa-134">Executive Team template</span></span>

<span data-ttu-id="6cffa-135">Il modello Executive Team è ideale per creare un team in cui i dirigenti aziendali possano comunicare e collaborare a iniziative aziendali come priorità annuali, budget fiscali, iniziative strategiche e clienti principali.</span><span class="sxs-lookup"><span data-stu-id="6cffa-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="6cffa-136">Questo modello viene fornito con un *canale privato* per invitare utenti selezionati per argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="6cffa-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="6cffa-137">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-137">Base template type</span></span>  | <span data-ttu-id="6cffa-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6cffa-138">baseTemplateId</span></span> | <span data-ttu-id="6cffa-139">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="6cffa-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="6cffa-140">SMB -</span></span> <br><span data-ttu-id="6cffa-141">Team dirigenti</span><span class="sxs-lookup"><span data-stu-id="6cffa-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="6cffa-142">Canali</span><span class="sxs-lookup"><span data-stu-id="6cffa-142">Channels</span></span> <ul><li><span data-ttu-id="6cffa-143">Generale\*</span><span class="sxs-lookup"><span data-stu-id="6cffa-143">General\*</span></span></li><li><span data-ttu-id="6cffa-144">Privato \*</span><span class="sxs-lookup"><span data-stu-id="6cffa-144">Private \*</span></span></li></ul> <span data-ttu-id="6cffa-145">App</span><span class="sxs-lookup"><span data-stu-id="6cffa-145">Apps</span></span><ul><li><span data-ttu-id="6cffa-146">OneNote (aggiunto al **canale** privato)</span><span class="sxs-lookup"><span data-stu-id="6cffa-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="6cffa-147">Planner (aggiunto al **canale** privato)</span><span class="sxs-lookup"><span data-stu-id="6cffa-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="6cffa-148">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="6cffa-148">Team properties</span></span> <ul><li><span data-ttu-id="6cffa-149">Visibilità del team impostata su Private</span><span class="sxs-lookup"><span data-stu-id="6cffa-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="6cffa-150">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="6cffa-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="6cffa-151">Per creare il team dirigenti prendendo le impostazioni predefinite dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="6cffa-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="6cffa-152">Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="6cffa-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="6cffa-153">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6cffa-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="6cffa-154">Modello Team di reparto</span><span class="sxs-lookup"><span data-stu-id="6cffa-154">Departmental Team template</span></span>

<span data-ttu-id="6cffa-155">Il modello team reparto può essere usato per creare un team per singoli reparti o per progetti.</span><span class="sxs-lookup"><span data-stu-id="6cffa-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="6cffa-156">Il modello di team Finance è ideale per tutti i post, gli annunci e la collaborazione e la comunicazione giornaliera all'interno dei membri del team Finance e dei membri del team di dirigenti, se appropriato.</span><span class="sxs-lookup"><span data-stu-id="6cffa-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="6cffa-157">Il modello viene fornito con un *canale privato* per invitare utenti selezionati per argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="6cffa-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="6cffa-158">Forniamo anche lo script seguente per il team Finanziario che può essere usato per estendere il modello ad altri reparti o progetti specifici aggiungendo, eliminando o modificando a proprio piacimento.</span><span class="sxs-lookup"><span data-stu-id="6cffa-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="6cffa-159">Ad esempio, se si ha un reparto *Marketing,* lo script può essere adattato rinominando il team da *Finanze* a *Marketing* per creare un nuovo team di marketing</span><span class="sxs-lookup"><span data-stu-id="6cffa-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="6cffa-160">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-160">Base template type</span></span> | <span data-ttu-id="6cffa-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6cffa-161">baseTemplateId</span></span> | <span data-ttu-id="6cffa-162">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="6cffa-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="6cffa-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="6cffa-163">SMB -</span></span> <br><span data-ttu-id="6cffa-164">Finanze</span><span class="sxs-lookup"><span data-stu-id="6cffa-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="6cffa-165">Canali</span><span class="sxs-lookup"><span data-stu-id="6cffa-165">Channels</span></span> <ul><li><span data-ttu-id="6cffa-166">Generale\*</span><span class="sxs-lookup"><span data-stu-id="6cffa-166">General\*</span></span></li><li><span data-ttu-id="6cffa-167">Privato \*</span><span class="sxs-lookup"><span data-stu-id="6cffa-167">Private \*</span></span></li></ul><br> <span data-ttu-id="6cffa-168">App</span><span class="sxs-lookup"><span data-stu-id="6cffa-168">Apps</span></span><ul><li><span data-ttu-id="6cffa-169">OneNote (aggiunto al **canale** privato)</span><span class="sxs-lookup"><span data-stu-id="6cffa-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="6cffa-170">Planner (aggiunto al **canale** privato)</span><span class="sxs-lookup"><span data-stu-id="6cffa-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="6cffa-171">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="6cffa-171">Team properties</span></span> <ul><li><span data-ttu-id="6cffa-172">Visibilità del team impostata su Private</span><span class="sxs-lookup"><span data-stu-id="6cffa-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="6cffa-173">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="6cffa-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="6cffa-174">Per creare il team Finance prendendo le impostazioni predefinite dal modello predefinito, specificare la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="6cffa-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="6cffa-175">Per altre informazioni su come distribuire modelli Teams, vedere l'articolo microsoft Graph sulla creazione [di un team.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="6cffa-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="6cffa-176">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6cffa-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="6cffa-177">Esempio: script di estensione del modello Finance Team</span><span class="sxs-lookup"><span data-stu-id="6cffa-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6cffa-178">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6cffa-178">Related topics</span></span>

- [<span data-ttu-id="6cffa-179">Introduzione ai modelli Teams nella console di amministrazione</span><span class="sxs-lookup"><span data-stu-id="6cffa-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="6cffa-180">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="6cffa-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="6cffa-181">[Creare un team](/graph/api/team-post?view=graph-rest-beta) (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="6cffa-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>