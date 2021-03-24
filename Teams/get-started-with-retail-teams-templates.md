---
title: Introduzione ai modelli di Teams
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
description: Scopri come usare i modelli di Teams per creare strutture di team studiate appositamente per le esigenze dei rivenditori al dettaglio fornendo impostazioni predefinite, canali, app preinstallate.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101202"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="25f0c-103">Introduzione ai modelli di Teams</span><span class="sxs-lookup"><span data-stu-id="25f0c-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="25f0c-104">I modelli di Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="25f0c-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="25f0c-105">I modelli di Teams includono definizioni predefinite delle strutture dei team progettate in base alle necessità dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="25f0c-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="25f0c-106">Puoi usare i modelli di Teams per creare rapidamente le tipologie di team più adatte ai rivenditori e implementarle nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f0c-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="25f0c-107">Puoi anche estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f0c-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="25f0c-108">In questo articolo verranno presentati i modelli di Teams e verrà consigliato come usarli.</span><span class="sxs-lookup"><span data-stu-id="25f0c-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="25f0c-109">Questo articolo è destinato agli utenti responsabili della pianificazione, dell'implementazione e della gestione di più team nell'organizzazione di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="25f0c-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="25f0c-110">Il servizio Teams è già stato implementato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f0c-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="25f0c-111">Se Teams non è ancora stato implementato, per iniziare, leggere [Come implementare Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="25f0c-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="25f0c-112">Per altre informazioni sui modelli di Teams in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="25f0c-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="25f0c-113">Modello Store</span><span class="sxs-lookup"><span data-stu-id="25f0c-113">Store template</span></span>

<span data-ttu-id="25f0c-114">Il modello Store è ideale per creare un team che rappresenta la sede di un singolo punto vendita per la vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="25f0c-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="25f0c-115">Con il modello Store è possibile creare un team per ogni punto vendita per la vendita al dettaglio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25f0c-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="25f0c-116">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="25f0c-116">Base template type</span></span> | <span data-ttu-id="25f0c-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="25f0c-117">baseTemplateId</span></span> | <span data-ttu-id="25f0c-118">Proprietà incluse nel modello base</span><span class="sxs-lookup"><span data-stu-id="25f0c-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="25f0c-119">Retail -</span><span class="sxs-lookup"><span data-stu-id="25f0c-119">Retail -</span></span> <br><span data-ttu-id="25f0c-120">Store</span><span class="sxs-lookup"><span data-stu-id="25f0c-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="25f0c-121">Canali</span><span class="sxs-lookup"><span data-stu-id="25f0c-121">Channels</span></span> <ul><li><span data-ttu-id="25f0c-122">Shifts handoff\*</span><span class="sxs-lookup"><span data-stu-id="25f0c-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="25f0c-123">Learning\*</span><span class="sxs-lookup"><span data-stu-id="25f0c-123">Learning\*</span></span></li></ul><span data-ttu-id="25f0c-124">\*Canali aggiunti automaticamente ai preferiti</span><span class="sxs-lookup"><span data-stu-id="25f0c-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="25f0c-125">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="25f0c-125">Team properties</span></span> <ul><li><span data-ttu-id="25f0c-126">Visibilità del team impostata su Public</span><span class="sxs-lookup"><span data-stu-id="25f0c-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="25f0c-127">Autorizzazioni dei membri</span><span class="sxs-lookup"><span data-stu-id="25f0c-127">Member permissions</span></span> <ul><li><span data-ttu-id="25f0c-128">Non possono creare/aggiornare/eliminare canali</span><span class="sxs-lookup"><span data-stu-id="25f0c-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="25f0c-129">Non possono aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="25f0c-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="25f0c-130">Non possono creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="25f0c-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="25f0c-131">Non possono creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="25f0c-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="25f0c-132">Modi consigliati per personalizzare il modello Store per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="25f0c-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="25f0c-133">Se l'organizzazione prevede reparti all'interno di ogni punto vendita, aggiungere un canale per ogni reparto.</span><span class="sxs-lookup"><span data-stu-id="25f0c-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="25f0c-134">L'aggiunta di un canale favorisce la comunicazione e la collaborazione all'interno del reparto.</span><span class="sxs-lookup"><span data-stu-id="25f0c-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="25f0c-135">Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, è opportuno aggiungerli come schede nel canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="25f0c-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="25f0c-136">Per le istruzioni, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="25f0c-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="25f0c-137">Modello Manager Collaboration</span><span class="sxs-lookup"><span data-stu-id="25f0c-137">Manager Collaboration template</span></span>

<span data-ttu-id="25f0c-138">Il modello Manager Collaboration è un altro dei modelli di Teams pensati per le esigenze dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="25f0c-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="25f0c-139">Il modello Manager Collaboration è ideale per creare un team che consenta a un set di responsabili di collaborare in punti vendita/aree geografiche e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="25f0c-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="25f0c-140">Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team Manager Collaboration per l'area californiana e includere tutti i responsabili dei punti vendita di tale regione, nonché i responsabili di area di tale area geografica.</span><span class="sxs-lookup"><span data-stu-id="25f0c-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="25f0c-141">Tipo di modello base</span><span class="sxs-lookup"><span data-stu-id="25f0c-141">Base template type</span></span> | <span data-ttu-id="25f0c-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="25f0c-142">baseTemplateId</span></span> | <span data-ttu-id="25f0c-143">Proprietà incluse nel modello base</span><span class="sxs-lookup"><span data-stu-id="25f0c-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="25f0c-144">Retail -</span><span class="sxs-lookup"><span data-stu-id="25f0c-144">Retail -</span></span> <br><span data-ttu-id="25f0c-145">Store</span><span class="sxs-lookup"><span data-stu-id="25f0c-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="25f0c-146">Canali</span><span class="sxs-lookup"><span data-stu-id="25f0c-146">Channels</span></span> <ul><li><span data-ttu-id="25f0c-147">Operations\*</span><span class="sxs-lookup"><span data-stu-id="25f0c-147">Operations\*</span></span></li><li><span data-ttu-id="25f0c-148">Learning\*</span><span class="sxs-lookup"><span data-stu-id="25f0c-148">Learning\*</span></span></li></ul><span data-ttu-id="25f0c-149">\*Canali aggiunti automaticamente ai preferiti</span><span class="sxs-lookup"><span data-stu-id="25f0c-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="25f0c-150">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="25f0c-150">Team properties</span></span> <ul><li><span data-ttu-id="25f0c-151">Visibilità del team impostata su Private</span><span class="sxs-lookup"><span data-stu-id="25f0c-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="25f0c-152">Autorizzazioni dei membri</span><span class="sxs-lookup"><span data-stu-id="25f0c-152">Member permissions</span></span> <ul><li><span data-ttu-id="25f0c-153">Possono creare/aggiornare/eliminare canali</span><span class="sxs-lookup"><span data-stu-id="25f0c-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="25f0c-154">Possono aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="25f0c-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="25f0c-155">Possono creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="25f0c-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="25f0c-156">Possono creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="25f0c-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="25f0c-157">Modi consigliati per personalizzare il modello Manager Collaboration per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="25f0c-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="25f0c-158">Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, che sono pertinenti per i responsabili, è opportuno aggiungerli come schede in un canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="25f0c-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="25f0c-159">Per le istruzioni, vedere la [documentazione relativa ai modelli di Microsoft Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="25f0c-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="25f0c-160">Come usare i modelli del produttore</span><span class="sxs-lookup"><span data-stu-id="25f0c-160">How to use first party templates</span></span>

<span data-ttu-id="25f0c-161">Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti.</span><span class="sxs-lookup"><span data-stu-id="25f0c-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="25f0c-162">Per altre informazioni su come implementare i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="25f0c-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="25f0c-163">I canali nel modello verranno creati automaticamente nella scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="25f0c-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="25f0c-164">Esempio: script di estensione del modello Store</span><span class="sxs-lookup"><span data-stu-id="25f0c-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="25f0c-165">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="25f0c-165">Relate topic</span></span>

[<span data-ttu-id="25f0c-166">Introduzione ai modelli di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="25f0c-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)