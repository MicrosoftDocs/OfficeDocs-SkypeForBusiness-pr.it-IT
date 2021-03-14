---
title: Usare i modelli retail di Teams nell'interfaccia di amministrazione
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
description: Scopri come usare i modelli di Teams per creare strutture di team studiate appositamente per le esigenze dei rivenditori al dettaglio fornendo impostazioni predefinite, canali, app preinstallate tramite l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662641"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="5e961-103">Usare i modelli retail di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5e961-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="5e961-104">I modelli di Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="5e961-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5e961-105">I modelli di Teams dispongono di una definizione preintegrata delle strutture dei team progettate intorno alle necessità dei rivenditori al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5e961-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="5e961-106">Puoi usare i modelli di Teams per creare rapidamente le tipologie di team che funzionano bene per i rivenditori al dettaglio e implementarle nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e961-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="5e961-107">Puoi anche estendere i modelli di Teams per creare team che si adattino al meglio alle esistenze specifiche dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e961-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="5e961-108">In questo articolo, verranno presentati i modelli di Teams e come possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="5e961-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="5e961-109">Questo articolo è per i responsabili dedicati alla pianificazione, all'implementazione e alla gestione di più team nell'organizzazione di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5e961-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="5e961-110">Si presume che tu abbia già implementato il servizio Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e961-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="5e961-111">Qualora non lo avessi ancora fatto, inizia a leggere [Come implementare Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5e961-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="5e961-112">Per scoprire di più sui modelli dei team in generale, fai riferimento a [Introduzione ai modelli di Teams](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="5e961-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="5e961-113">Organizzare un negozio</span><span class="sxs-lookup"><span data-stu-id="5e961-113">Organize a store</span></span>

<span data-ttu-id="5e961-114">Unisci i tuoi dipendenti in un'unica esperienza centralizzata per gestire attività, condividere documenti e risolvere i problemi correlati ai clienti.</span><span class="sxs-lookup"><span data-stu-id="5e961-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="5e961-115">Integra applicazioni aggiuntive per ottimizzare i processi di inizio e fine turno.</span><span class="sxs-lookup"><span data-stu-id="5e961-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="5e961-116">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="5e961-116">Base template type</span></span> |<span data-ttu-id="5e961-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5e961-117">baseTemplateId</span></span> | <span data-ttu-id="5e961-118">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="5e961-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="5e961-119">Organizzare un negozio</span><span class="sxs-lookup"><span data-stu-id="5e961-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="5e961-120">Canali:</span><span class="sxs-lookup"><span data-stu-id="5e961-120">Channels:</span></span> <ul><li><span data-ttu-id="5e961-121">Generale</span><span class="sxs-lookup"><span data-stu-id="5e961-121">General</span></span><li><span data-ttu-id="5e961-122">Passaggio di consegne del turno</span><span class="sxs-lookup"><span data-stu-id="5e961-122">Shift handoff</span></span></li><li><span data-ttu-id="5e961-123">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="5e961-123">Learning</span></span></li></ul> <span data-ttu-id="5e961-124">App:</span><span class="sxs-lookup"><span data-stu-id="5e961-124">Apps:</span></span> <ul><li><span data-ttu-id="5e961-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="5e961-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="5e961-126">Collaborazione tra responsabili</span><span class="sxs-lookup"><span data-stu-id="5e961-126">Manager Collaboration</span></span>

<span data-ttu-id="5e961-127">Il modello Collaborazione tra responsabili è perfetto per creare un team formato da un gruppo di responsabili e agevolare la loro collaborazione tra negozi/aree geografiche, ecc. Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team di Collaborazione tra responsabili per l'area californiana e includere tutti gli Store manager in quella regione, come anche gli Area manager di quello Stato.</span><span class="sxs-lookup"><span data-stu-id="5e961-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="5e961-128">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="5e961-128">Base template type</span></span>| <span data-ttu-id="5e961-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5e961-129">baseTemplateId</span></span> | <span data-ttu-id="5e961-130">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="5e961-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="5e961-131">Vendita al dettaglio: collaborazione tra responsabili</span><span class="sxs-lookup"><span data-stu-id="5e961-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="5e961-132">Canali:</span><span class="sxs-lookup"><span data-stu-id="5e961-132">Channels:</span></span> <ul><li><span data-ttu-id="5e961-133">Generale</span><span class="sxs-lookup"><span data-stu-id="5e961-133">General</span></span><li><span data-ttu-id="5e961-134">Operazioni</span><span class="sxs-lookup"><span data-stu-id="5e961-134">Operations</span></span></li><li><span data-ttu-id="5e961-135">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="5e961-135">Learning</span></span></li></ul> <span data-ttu-id="5e961-136">App:</span><span class="sxs-lookup"><span data-stu-id="5e961-136">Apps:</span></span> <ul><li><span data-ttu-id="5e961-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="5e961-137">Wiki</span></span></li></ul>|
||||
