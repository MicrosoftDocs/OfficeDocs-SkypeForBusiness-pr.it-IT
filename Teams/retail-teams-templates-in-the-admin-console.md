---
title: Usare i modelli di teams Retail nell'interfaccia di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze del rivenditore fornendo impostazioni predefinite, canali e app preinstallate con l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662641"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="94064-103">Usare i modelli di teams Retail nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="94064-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="94064-104">I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="94064-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="94064-105">I modelli di teams hanno definizioni predefinite delle strutture del team progettate intorno alle esigenze del rivenditore.</span><span class="sxs-lookup"><span data-stu-id="94064-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="94064-106">È possibile usare i modelli di teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e li distribuiscono in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94064-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="94064-107">Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.</span><span class="sxs-lookup"><span data-stu-id="94064-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="94064-108">In questo articolo verranno presentati tutti i modelli di team e il modo in cui è consigliabile usarli.</span><span class="sxs-lookup"><span data-stu-id="94064-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="94064-109">Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="94064-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="94064-110">Supponiamo che tu abbia già implementato il servizio teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94064-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="94064-111">Se non sono stati ancora distribuiti team, iniziare leggendo la [procedura per l'implementazione di Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="94064-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="94064-112">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates-in-the-admin-console.md)di teams.</span><span class="sxs-lookup"><span data-stu-id="94064-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="94064-113">Organizzare uno Store</span><span class="sxs-lookup"><span data-stu-id="94064-113">Organize a store</span></span>

<span data-ttu-id="94064-114">Riunire i dipendenti al dettaglio in un'unica esperienza centralizzata per gestire le attività, condividere documenti e risolvere i problemi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="94064-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="94064-115">Integrare altre applicazioni per semplificare l'avvio di & i processi finali.</span><span class="sxs-lookup"><span data-stu-id="94064-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="94064-116">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="94064-116">Base template type</span></span> |<span data-ttu-id="94064-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="94064-117">baseTemplateId</span></span> | <span data-ttu-id="94064-118">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="94064-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="94064-119">Organizzare uno Store</span><span class="sxs-lookup"><span data-stu-id="94064-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="94064-120">Canali</span><span class="sxs-lookup"><span data-stu-id="94064-120">Channels:</span></span> <ul><li><span data-ttu-id="94064-121">Generale</span><span class="sxs-lookup"><span data-stu-id="94064-121">General</span></span><li><span data-ttu-id="94064-122">Cambio di consegna</span><span class="sxs-lookup"><span data-stu-id="94064-122">Shift handoff</span></span></li><li><span data-ttu-id="94064-123">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="94064-123">Learning</span></span></li></ul> <span data-ttu-id="94064-124">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="94064-124">Apps:</span></span> <ul><li><span data-ttu-id="94064-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="94064-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="94064-126">Collaborazione con i Manager</span><span class="sxs-lookup"><span data-stu-id="94064-126">Manager Collaboration</span></span>

<span data-ttu-id="94064-127">Il modello di collaborazione di Manager è ideale per creare un team per un set di Manager che collaborano tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione di gestione per l'area della California e includere tutti i responsabili dello Store nell'area geografica, oltre al responsabile regionale per l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="94064-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="94064-128">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="94064-128">Base template type</span></span>| <span data-ttu-id="94064-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="94064-129">baseTemplateId</span></span> | <span data-ttu-id="94064-130">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="94064-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="94064-131">Collaborazione al dettaglio-Manager</span><span class="sxs-lookup"><span data-stu-id="94064-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="94064-132">Canali</span><span class="sxs-lookup"><span data-stu-id="94064-132">Channels:</span></span> <ul><li><span data-ttu-id="94064-133">Generale</span><span class="sxs-lookup"><span data-stu-id="94064-133">General</span></span><li><span data-ttu-id="94064-134">Operazioni</span><span class="sxs-lookup"><span data-stu-id="94064-134">Operations</span></span></li><li><span data-ttu-id="94064-135">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="94064-135">Learning</span></span></li></ul> <span data-ttu-id="94064-136">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="94064-136">Apps:</span></span> <ul><li><span data-ttu-id="94064-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="94064-137">Wiki</span></span></li></ul>|
||||
