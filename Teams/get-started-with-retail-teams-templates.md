---
title: Introduzione ai modelli di teams in Retail
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze del rivenditore fornendo impostazioni predefinite, canali e app preinstallate.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b170047a3b8d3218b8e31bdc9d4b1035eb8706c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583203"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="38708-103">Introduzione ai modelli di teams in Retail</span><span class="sxs-lookup"><span data-stu-id="38708-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="38708-104">I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="38708-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="38708-105">I modelli di teams hanno definizioni predefinite delle strutture del team progettate intorno alle esigenze del rivenditore.</span><span class="sxs-lookup"><span data-stu-id="38708-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="38708-106">È possibile usare i modelli di teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e li distribuiscono in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38708-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="38708-107">Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.</span><span class="sxs-lookup"><span data-stu-id="38708-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="38708-108">In questo articolo verranno introdotti tutti i modelli di team e il modo in cui è consigliabile usarli.</span><span class="sxs-lookup"><span data-stu-id="38708-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="38708-109">Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="38708-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="38708-110">Supponiamo che tu abbia già implementato il servizio teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38708-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="38708-111">Se non sono stati ancora distribuiti team, iniziare leggendo la [procedura per l'implementazione di Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="38708-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="38708-112">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates.md)di teams.</span><span class="sxs-lookup"><span data-stu-id="38708-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="38708-113">Modello di archivio</span><span class="sxs-lookup"><span data-stu-id="38708-113">Store template</span></span>

<span data-ttu-id="38708-114">Il modello dello Store è ideale per creare un team che rappresenti una singola posizione per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="38708-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="38708-115">Usando il modello Store, è possibile creare un team per ogni posizione del punto vendita all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38708-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="38708-116">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="38708-116">Base template type</span></span> | <span data-ttu-id="38708-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="38708-117">baseTemplateId</span></span> | <span data-ttu-id="38708-118">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="38708-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="38708-119">Negozio</span><span class="sxs-lookup"><span data-stu-id="38708-119">Retail -</span></span> <br><span data-ttu-id="38708-120">Negozio</span><span class="sxs-lookup"><span data-stu-id="38708-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="38708-121">Canali</span><span class="sxs-lookup"><span data-stu-id="38708-121">Channels</span></span> <ul><li><span data-ttu-id="38708-122">Turni di consegna\*</span><span class="sxs-lookup"><span data-stu-id="38708-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="38708-123">Apprendimento\*</span><span class="sxs-lookup"><span data-stu-id="38708-123">Learning\*</span></span></li></ul><span data-ttu-id="38708-124">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="38708-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="38708-125">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="38708-125">Team properties</span></span> <ul><li><span data-ttu-id="38708-126">Visibilità del team impostata su pubblico</span><span class="sxs-lookup"><span data-stu-id="38708-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="38708-127">Autorizzazioni per i membri</span><span class="sxs-lookup"><span data-stu-id="38708-127">Member permissions</span></span> <ul><li><span data-ttu-id="38708-128">Non è possibile creare/aggiornare/eliminare i canali</span><span class="sxs-lookup"><span data-stu-id="38708-128">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="38708-129">Non è possibile aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="38708-129">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="38708-130">Non è possibile creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="38708-130">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="38708-131">Non è possibile creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="38708-131">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="38708-132">Modi consigliati per personalizzare il modello di archivio per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="38708-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="38708-133">Se l'organizzazione ha reparti all'interno di ogni archivio, aggiungere un canale per ogni reparto.</span><span class="sxs-lookup"><span data-stu-id="38708-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="38708-134">Ciò faciliterà la comunicazione e la collaborazione all'interno del reparto.</span><span class="sxs-lookup"><span data-stu-id="38708-134">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="38708-135">Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, è consigliabile aggiungerli come schede nel canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="38708-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="38708-136">Per istruzioni, vedere [Introduzione ai modelli di teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="38708-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="38708-137">Modello di Collaboration Manager</span><span class="sxs-lookup"><span data-stu-id="38708-137">Manager Collaboration template</span></span>

<span data-ttu-id="38708-138">Il modello di collaborazione di Manager è un altro dei modelli di Team progettati intorno alle esigenze del rivenditore.</span><span class="sxs-lookup"><span data-stu-id="38708-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="38708-139">Il modello di collaborazione di Manager è ideale per creare un team per un set di Manager che collaborano tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione di gestione per l'area della California e includere tutti i responsabili dello Store nell'area geografica, oltre al responsabile regionale per l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="38708-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="38708-140">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="38708-140">Base template type</span></span> | <span data-ttu-id="38708-141">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="38708-141">baseTemplateId</span></span> | <span data-ttu-id="38708-142">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="38708-142">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="38708-143">Negozio</span><span class="sxs-lookup"><span data-stu-id="38708-143">Retail -</span></span> <br><span data-ttu-id="38708-144">Negozio</span><span class="sxs-lookup"><span data-stu-id="38708-144">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="38708-145">Canali</span><span class="sxs-lookup"><span data-stu-id="38708-145">Channels</span></span> <ul><li><span data-ttu-id="38708-146">Operazioni\*</span><span class="sxs-lookup"><span data-stu-id="38708-146">Operations\*</span></span></li><li><span data-ttu-id="38708-147">Apprendimento\*</span><span class="sxs-lookup"><span data-stu-id="38708-147">Learning\*</span></span></li></ul><span data-ttu-id="38708-148">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="38708-148">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="38708-149">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="38708-149">Team properties</span></span> <ul><li><span data-ttu-id="38708-150">Visibilità del team impostata su privato</span><span class="sxs-lookup"><span data-stu-id="38708-150">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="38708-151">Autorizzazioni per i membri</span><span class="sxs-lookup"><span data-stu-id="38708-151">Member permissions</span></span> <ul><li><span data-ttu-id="38708-152">Può creare/aggiornare/eliminare i canali</span><span class="sxs-lookup"><span data-stu-id="38708-152">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="38708-153">Può aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="38708-153">Can add/remove apps</span></span> </li><li><span data-ttu-id="38708-154">Può creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="38708-154">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="38708-155">Può creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="38708-155">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="38708-156">Modi consigliati per personalizzare il modello di collaborazione di gestione per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="38708-156">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="38708-157">Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, che sono rilevanti per i responsabili, è consigliabile aggiungerli come schede in un canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="38708-157">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="38708-158">Per istruzioni, vedere la documentazione del [modello Microsoft teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="38708-158">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="38708-159">Come usare i modelli di First Party</span><span class="sxs-lookup"><span data-stu-id="38708-159">How to use first party templates</span></span>

<span data-ttu-id="38708-160">Per usare questi modelli, è sufficiente modificare la proprietà "template@odata. bind" nel corpo della richiesta da "standard" a TemplateIDs sopra.</span><span class="sxs-lookup"><span data-stu-id="38708-160">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="38708-161">Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph su come [creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="38708-161">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="38708-162">I canali nel modello verranno creati automaticamente nella scheda generale.</span><span class="sxs-lookup"><span data-stu-id="38708-162">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="38708-163">Esempio: script di estensione del modello di archiviazione</span><span class="sxs-lookup"><span data-stu-id="38708-163">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
