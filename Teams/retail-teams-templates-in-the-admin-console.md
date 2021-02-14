---
title: Usare i modelli di vendita al dettaglio di Teams nell'interfaccia di amministrazione
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
description: Informazioni su come usare i modelli di Teams per creare strutture di team progettate per le esigenze dei rivenditori, fornendo impostazioni predefinite, canali e app preinstallato utilizzando l'interfaccia di amministrazione.
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
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="5a7c9-103">Usare i modelli di vendita al dettaglio di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5a7c9-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="5a7c9-104">I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5a7c9-105">I modelli di Teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze dei rivenditori.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="5a7c9-106">È possibile usare i modelli di Teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e distribuirli all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="5a7c9-107">È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="5a7c9-108">In questo articolo verranno presentati tutti i modelli di Teams e verrà spiegato come usarli.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="5a7c9-109">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="5a7c9-110">Presuppongiamo che l'utente abbia già distribuito il servizio Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="5a7c9-111">Se Teams non è ancora stato ancora implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5a7c9-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="5a7c9-112">Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="5a7c9-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="5a7c9-113">Organizzare uno store</span><span class="sxs-lookup"><span data-stu-id="5a7c9-113">Organize a store</span></span>

<span data-ttu-id="5a7c9-114">Riunire i dipendenti della vendita al dettaglio in un'unica esperienza centrale per gestire le attività, condividere documenti e risolvere i problemi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="5a7c9-115">Integrare altre applicazioni per semplificare i processi di & di inizio e fine.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="5a7c9-116">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="5a7c9-116">Base template type</span></span> |<span data-ttu-id="5a7c9-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5a7c9-117">baseTemplateId</span></span> | <span data-ttu-id="5a7c9-118">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="5a7c9-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="5a7c9-119">Organizzare uno store</span><span class="sxs-lookup"><span data-stu-id="5a7c9-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="5a7c9-120">Canali:</span><span class="sxs-lookup"><span data-stu-id="5a7c9-120">Channels:</span></span> <ul><li><span data-ttu-id="5a7c9-121">Generale</span><span class="sxs-lookup"><span data-stu-id="5a7c9-121">General</span></span><li><span data-ttu-id="5a7c9-122">Maiusc handoff</span><span class="sxs-lookup"><span data-stu-id="5a7c9-122">Shift handoff</span></span></li><li><span data-ttu-id="5a7c9-123">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="5a7c9-123">Learning</span></span></li></ul> <span data-ttu-id="5a7c9-124">App:</span><span class="sxs-lookup"><span data-stu-id="5a7c9-124">Apps:</span></span> <ul><li><span data-ttu-id="5a7c9-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="5a7c9-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="5a7c9-126">Collaborazione con i manager</span><span class="sxs-lookup"><span data-stu-id="5a7c9-126">Manager Collaboration</span></span>

<span data-ttu-id="5a7c9-127">Il modello Collaborazione con i responsabili è ideale per creare un team in cui un set di responsabili può collaborare in negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione manager per l'area geografica della California e includere tutti i responsabili negozio di tale area geografica, nonché il responsabile regionale per tale area geografica.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="5a7c9-128">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="5a7c9-128">Base template type</span></span>| <span data-ttu-id="5a7c9-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5a7c9-129">baseTemplateId</span></span> | <span data-ttu-id="5a7c9-130">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="5a7c9-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="5a7c9-131">Vendita al dettaglio - collaborazione con i manager</span><span class="sxs-lookup"><span data-stu-id="5a7c9-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="5a7c9-132">Canali:</span><span class="sxs-lookup"><span data-stu-id="5a7c9-132">Channels:</span></span> <ul><li><span data-ttu-id="5a7c9-133">Generale</span><span class="sxs-lookup"><span data-stu-id="5a7c9-133">General</span></span><li><span data-ttu-id="5a7c9-134">Operazioni</span><span class="sxs-lookup"><span data-stu-id="5a7c9-134">Operations</span></span></li><li><span data-ttu-id="5a7c9-135">Apprendimento</span><span class="sxs-lookup"><span data-stu-id="5a7c9-135">Learning</span></span></li></ul> <span data-ttu-id="5a7c9-136">App:</span><span class="sxs-lookup"><span data-stu-id="5a7c9-136">Apps:</span></span> <ul><li><span data-ttu-id="5a7c9-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="5a7c9-137">Wiki</span></span></li></ul>|
||||
