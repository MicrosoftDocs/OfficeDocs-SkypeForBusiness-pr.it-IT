---
title: Introduzione ai modelli di team per le piccole e medie imprese
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Introduzione ai modelli di team per le piccole e medie imprese
ms.openlocfilehash: fd0d17ac78dc7dea0efde95315604189671caa9e
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36184612"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a><span data-ttu-id="4e2ee-103">Introduzione ai modelli di team per le piccole e medie imprese</span><span class="sxs-lookup"><span data-stu-id="4e2ee-103">Get started with Teams templates for Small and Medium Businesses</span></span>

<span data-ttu-id="4e2ee-104">I modelli di Microsoft teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4e2ee-105">Per le piccole e medie imprese, i modelli possono essere particolarmente potenti, in quanto aiutano gli amministratori a distribuire rapidamente team in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="4e2ee-106">I modelli consentono anche di orientare gli utenti e iniziare a usare teams in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="4e2ee-107">Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="4e2ee-108">Attualmente offriamo tre modelli SMB di prima parte che possono essere sfruttati per svariate situazioni.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-108">We currently offer three first party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="4e2ee-109">Tutti i modelli creeranno Team *privati* .</span><span class="sxs-lookup"><span data-stu-id="4e2ee-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="4e2ee-110">Dopo aver creato i team e essere pronti per l'implementazione per l'organizzazione, è possibile impostare la privacy a *livello* aziendale o *pubblico*, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="4e2ee-111">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates.md)di team.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="4e2ee-112">Modello a livello aziendale</span><span class="sxs-lookup"><span data-stu-id="4e2ee-112">Company-Wide template</span></span>
<span data-ttu-id="4e2ee-113">Il modello a livello aziendale è pensato per la comunicazione e la collaborazione rilevanti per l'intera società.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="4e2ee-114">Puoi usare il canale generale per gli annunci a livello aziendale, le notizie del settore o i post esecutivi.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="4e2ee-115">Il canale Human Resources è il luogo ideale per consolidare tutte le attività correlate alle risorse umane, ad esempio post di lavoro, nuovi imbarcazione per i dipendenti, formazione e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="4e2ee-116">Il canale Fun Stuff offre una piattaforma sociale per tutti i post casuali e divertenti.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="4e2ee-117">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-117">Base template type</span></span>  | <span data-ttu-id="4e2ee-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4e2ee-118">baseTemplateId</span></span> | <span data-ttu-id="4e2ee-119">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="4e2ee-120">SMB</span><span class="sxs-lookup"><span data-stu-id="4e2ee-120">SMB -</span></span> <br><span data-ttu-id="4e2ee-121">A livello aziendale</span><span class="sxs-lookup"><span data-stu-id="4e2ee-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="4e2ee-122">Canali</span><span class="sxs-lookup"><span data-stu-id="4e2ee-122">Channels</span></span> <ul><li><span data-ttu-id="4e2ee-123">Generale\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-123">General\*</span></span></li><li><span data-ttu-id="4e2ee-124">Risorse umane\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-124">Human Resources\*</span></span></li><li><span data-ttu-id="4e2ee-125">Cose divertenti\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="4e2ee-126">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="4e2ee-126">Apps</span></span><ul><li><span data-ttu-id="4e2ee-127">Portale aziendale (sito Web aggiunto al canale **risorse umane** )</span><span class="sxs-lookup"><span data-stu-id="4e2ee-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="4e2ee-128">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="4e2ee-128">Team properties</span></span> <ul><li><span data-ttu-id="4e2ee-129">Visibilità del team impostata su privato</span><span class="sxs-lookup"><span data-stu-id="4e2ee-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="4e2ee-130">\* Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="4e2ee-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="4e2ee-131">Per creare il team a livello aziendale utilizzando le impostazioni predefinite del modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="4e2ee-132">Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="4e2ee-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="4e2ee-133">Richiesta</span><span class="sxs-lookup"><span data-stu-id="4e2ee-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="4e2ee-134">Modello di team Executive</span><span class="sxs-lookup"><span data-stu-id="4e2ee-134">Executive Team template</span></span>

<span data-ttu-id="4e2ee-135">Il modello Executive Team è ideale per creare un team per i dirigenti aziendali per comunicare e collaborare a iniziative aziendali come le priorità annuali, i bilanci fiscali, le iniziative strategiche, i clienti principali e così via. Questo modello include un canale *privato* per invitare gli utenti selezionati per argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="4e2ee-136">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-136">Base template type</span></span>  | <span data-ttu-id="4e2ee-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4e2ee-137">baseTemplateId</span></span> | <span data-ttu-id="4e2ee-138">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="4e2ee-139">SMB</span><span class="sxs-lookup"><span data-stu-id="4e2ee-139">SMB -</span></span> <br><span data-ttu-id="4e2ee-140">Team Executives</span><span class="sxs-lookup"><span data-stu-id="4e2ee-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="4e2ee-141">Canali</span><span class="sxs-lookup"><span data-stu-id="4e2ee-141">Channels</span></span> <ul><li><span data-ttu-id="4e2ee-142">Generale\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-142">General\*</span></span></li><li><span data-ttu-id="4e2ee-143">Privato\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-143">Private \*</span></span></li></ul> <span data-ttu-id="4e2ee-144">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="4e2ee-144">Apps</span></span><ul><li><span data-ttu-id="4e2ee-145">OneNote (aggiunto al canale **privato** )</span><span class="sxs-lookup"><span data-stu-id="4e2ee-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="4e2ee-146">Planner (aggiunto al canale **privato** )</span><span class="sxs-lookup"><span data-stu-id="4e2ee-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="4e2ee-147">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="4e2ee-147">Team properties</span></span> <ul><li><span data-ttu-id="4e2ee-148">Visibilità del team impostata su privato</span><span class="sxs-lookup"><span data-stu-id="4e2ee-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="4e2ee-149">\* Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="4e2ee-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="4e2ee-150">Per creare il team Executives prendendo i valori predefiniti dal modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="4e2ee-151">Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="4e2ee-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="4e2ee-152">Richiesta</span><span class="sxs-lookup"><span data-stu-id="4e2ee-152">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="4e2ee-153">Modello di Team dipartimentale</span><span class="sxs-lookup"><span data-stu-id="4e2ee-153">Departmental Team template</span></span>

<span data-ttu-id="4e2ee-154">Il modello del team dipartimentale può essere usato per creare un team per singoli reparti o per progetti.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="4e2ee-155">Il modello Finance team è ideale per tutti i post, gli annunci e la collaborazione e la comunicazione giornaliera all'interno dei membri del team finanziario (e i membri del team Executive in base alle esigenze).</span><span class="sxs-lookup"><span data-stu-id="4e2ee-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="4e2ee-156">Il modello include un canale *privato* per invitare gli utenti selezionati per argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="4e2ee-157">Forniamo anche lo script seguente per il team Finance che può essere usato per estendere il modello ad altri reparti o progetti specifici aggiungendo, eliminando o modificando a proprio piacimento.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="4e2ee-158">Ad esempio, se si ha un reparto *Marketing* , lo script può essere adattato rinominando il team da *Finance* a *Marketing* per creare un nuovo team di marketing</span><span class="sxs-lookup"><span data-stu-id="4e2ee-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="4e2ee-159">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-159">Base template type</span></span> | <span data-ttu-id="4e2ee-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4e2ee-160">baseTemplateId</span></span> | <span data-ttu-id="4e2ee-161">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="4e2ee-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="4e2ee-162">SMB</span><span class="sxs-lookup"><span data-stu-id="4e2ee-162">SMB -</span></span> <br><span data-ttu-id="4e2ee-163">Finanza</span><span class="sxs-lookup"><span data-stu-id="4e2ee-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="4e2ee-164">Canali</span><span class="sxs-lookup"><span data-stu-id="4e2ee-164">Channels</span></span> <ul><li><span data-ttu-id="4e2ee-165">Generale\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-165">General\*</span></span></li><li><span data-ttu-id="4e2ee-166">Privato\*</span><span class="sxs-lookup"><span data-stu-id="4e2ee-166">Private \*</span></span></li></ul><br> <span data-ttu-id="4e2ee-167">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="4e2ee-167">Apps</span></span><ul><li><span data-ttu-id="4e2ee-168">OneNote (aggiunto al canale **privato** )</span><span class="sxs-lookup"><span data-stu-id="4e2ee-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="4e2ee-169">Planner (aggiunto al canale **privato** )</span><span class="sxs-lookup"><span data-stu-id="4e2ee-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="4e2ee-170">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="4e2ee-170">Team properties</span></span> <ul><li><span data-ttu-id="4e2ee-171">Visibilità del team impostata su privato</span><span class="sxs-lookup"><span data-stu-id="4e2ee-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="4e2ee-172">\* Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="4e2ee-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="4e2ee-173">Per creare il team finanziario prendendo le impostazioni predefinite dal modello predefinito, fornisci la rappresentazione JSON dell'oggetto team nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4e2ee-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="4e2ee-174">Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph per la [creazione di un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="4e2ee-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="4e2ee-175">Richiesta</span><span class="sxs-lookup"><span data-stu-id="4e2ee-175">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
``

### Example: Finance Team template extension script

``` Powershell
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

## <a name="related-topics"></a><span data-ttu-id="4e2ee-176">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4e2ee-176">Related topics</span></span>

- [<span data-ttu-id="4e2ee-177">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="4e2ee-177">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="4e2ee-178">[Creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="4e2ee-178">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

