---
title: Introduzione ai modelli di Teams nella vendita al dettaglio
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
description: Informazioni su come usare i modelli di Teams per creare strutture di team progettate per le esigenze dei rivenditori, fornendo impostazioni predefinite, canali e app preinstallato.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424636"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="6dfc9-103">Introduzione ai modelli di Teams nella vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="6dfc9-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="6dfc9-104">I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6dfc9-105">I modelli di Teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="6dfc9-106">È possibile usare i modelli di Teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e distribuirli all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="6dfc9-107">È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="6dfc9-108">In questo articolo verranno presentati tutti i modelli di Teams e verrà consigliato come usarli.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="6dfc9-109">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="6dfc9-110">Il servizio Teams è già stato distribuito nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="6dfc9-111">Se Teams non è ancora stato ancora implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc9-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="6dfc9-112">Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc9-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="6dfc9-113">Modello Store</span><span class="sxs-lookup"><span data-stu-id="6dfc9-113">Store template</span></span>

<span data-ttu-id="6dfc9-114">Il modello Store è ideale per creare un team che rappresenti una singola sede di un negozio.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="6dfc9-115">Con il modello Store, è possibile creare un team per ogni punto vendita all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="6dfc9-116">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="6dfc9-116">Base template type</span></span> | <span data-ttu-id="6dfc9-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6dfc9-117">baseTemplateId</span></span> | <span data-ttu-id="6dfc9-118">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="6dfc9-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="6dfc9-119">Vendita al dettaglio -</span><span class="sxs-lookup"><span data-stu-id="6dfc9-119">Retail -</span></span> <br><span data-ttu-id="6dfc9-120">Negozio</span><span class="sxs-lookup"><span data-stu-id="6dfc9-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="6dfc9-121">Canali</span><span class="sxs-lookup"><span data-stu-id="6dfc9-121">Channels</span></span> <ul><li><span data-ttu-id="6dfc9-122">Shifts handoff\*</span><span class="sxs-lookup"><span data-stu-id="6dfc9-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="6dfc9-123">Apprendimento\*</span><span class="sxs-lookup"><span data-stu-id="6dfc9-123">Learning\*</span></span></li></ul><span data-ttu-id="6dfc9-124">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="6dfc9-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="6dfc9-125">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="6dfc9-125">Team properties</span></span> <ul><li><span data-ttu-id="6dfc9-126">Visibilità del team impostata su Pubblico</span><span class="sxs-lookup"><span data-stu-id="6dfc9-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="6dfc9-127">Autorizzazioni per i membri</span><span class="sxs-lookup"><span data-stu-id="6dfc9-127">Member permissions</span></span> <ul><li><span data-ttu-id="6dfc9-128">Non è possibile creare/aggiornare/eliminare canali</span><span class="sxs-lookup"><span data-stu-id="6dfc9-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="6dfc9-129">Non è possibile aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="6dfc9-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="6dfc9-130">Non è possibile creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="6dfc9-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="6dfc9-131">Non è possibile creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="6dfc9-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="6dfc9-132">Modi consigliati per personalizzare il modello dello Store per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="6dfc9-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="6dfc9-133">Se l'organizzazione ha reparti all'interno di ogni negozio, aggiungere un canale per ogni reparto.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="6dfc9-134">L'aggiunta di un canale facilita la comunicazione e la collaborazione all'interno del reparto.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="6dfc9-135">Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, è consigliabile bloccarli come schede nel canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="6dfc9-136">Per [istruzioni, vedere Introduzione ai modelli di Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc9-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="6dfc9-137">Modello collaborazione manager</span><span class="sxs-lookup"><span data-stu-id="6dfc9-137">Manager Collaboration template</span></span>

<span data-ttu-id="6dfc9-138">Il modello Collaborazione con i manager è un altro dei modelli di Teams progettati in base alle esigenze dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="6dfc9-139">Il modello Collaborazione con i responsabili è ideale per creare un team in cui un set di responsabili può collaborare in negozi/aree geografiche e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="6dfc9-140">Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione manager per l'area geografica della California e includere tutti i responsabili negozio di tale area geografica, nonché il responsabile regionale per tale area geografica.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="6dfc9-141">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="6dfc9-141">Base template type</span></span> | <span data-ttu-id="6dfc9-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6dfc9-142">baseTemplateId</span></span> | <span data-ttu-id="6dfc9-143">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="6dfc9-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="6dfc9-144">Vendita al dettaglio -</span><span class="sxs-lookup"><span data-stu-id="6dfc9-144">Retail -</span></span> <br><span data-ttu-id="6dfc9-145">Negozio</span><span class="sxs-lookup"><span data-stu-id="6dfc9-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="6dfc9-146">Canali</span><span class="sxs-lookup"><span data-stu-id="6dfc9-146">Channels</span></span> <ul><li><span data-ttu-id="6dfc9-147">Operazioni\*</span><span class="sxs-lookup"><span data-stu-id="6dfc9-147">Operations\*</span></span></li><li><span data-ttu-id="6dfc9-148">Apprendimento\*</span><span class="sxs-lookup"><span data-stu-id="6dfc9-148">Learning\*</span></span></li></ul><span data-ttu-id="6dfc9-149">\*Canali preferiti automaticamente</span><span class="sxs-lookup"><span data-stu-id="6dfc9-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="6dfc9-150">Proprietà del team</span><span class="sxs-lookup"><span data-stu-id="6dfc9-150">Team properties</span></span> <ul><li><span data-ttu-id="6dfc9-151">Visibilità del team impostata su Privato</span><span class="sxs-lookup"><span data-stu-id="6dfc9-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="6dfc9-152">Autorizzazioni per i membri</span><span class="sxs-lookup"><span data-stu-id="6dfc9-152">Member permissions</span></span> <ul><li><span data-ttu-id="6dfc9-153">Può creare/aggiornare/eliminare canali</span><span class="sxs-lookup"><span data-stu-id="6dfc9-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="6dfc9-154">Può aggiungere/rimuovere app</span><span class="sxs-lookup"><span data-stu-id="6dfc9-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="6dfc9-155">Può creare/aggiornare/rimuovere schede</span><span class="sxs-lookup"><span data-stu-id="6dfc9-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="6dfc9-156">Può creare/aggiornare/rimuovere connettori</span><span class="sxs-lookup"><span data-stu-id="6dfc9-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="6dfc9-157">Modi consigliati per personalizzare il modello Collaborazione con i manager per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="6dfc9-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="6dfc9-158">Se l'organizzazione ha siti Web interni rilevanti per i responsabili, ad esempio un sito di SharePoint, è consigliabile bloccarli come schede in un canale del team pertinente.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="6dfc9-159">Per istruzioni, vedere la documentazione del modello [Microsoft Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc9-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="6dfc9-160">Come usare i modelli di prima parte</span><span class="sxs-lookup"><span data-stu-id="6dfc9-160">How to use first party templates</span></span>

<span data-ttu-id="6dfc9-161">Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID riportati sopra.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="6dfc9-162">Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="6dfc9-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="6dfc9-163">I canali nel modello verranno creati automaticamente nella scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="6dfc9-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="6dfc9-164">Esempio: Script dell'estensione del modello Store</span><span class="sxs-lookup"><span data-stu-id="6dfc9-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="6dfc9-165">Correla argomento</span><span class="sxs-lookup"><span data-stu-id="6dfc9-165">Relate topic</span></span>

[<span data-ttu-id="6dfc9-166">Introduzione ai modelli di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="6dfc9-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
