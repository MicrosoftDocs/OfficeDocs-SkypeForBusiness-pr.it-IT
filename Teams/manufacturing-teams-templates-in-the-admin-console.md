---
title: Introduzione ai modelli di produzione di Teams nell'interfaccia di amministrazione
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
description: Informazioni sull'uso. Modelli di Teams per creare strutture di team progettate per le esigenze di produzione fornendo impostazioni predefinite, canali e app preinstallato utilizzando l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51a28e997e5c7c0b36fb49cd0bb46768b7808a29
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662221"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="4aa88-104">Usare i modelli di produzione di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="4aa88-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="4aa88-105">I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="4aa88-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4aa88-106">I modelli di Teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze di produzione.</span><span class="sxs-lookup"><span data-stu-id="4aa88-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="4aa88-107">È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4aa88-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="4aa88-108">In questo articolo vengono presentati tutti i modelli di Teams e viene consigliato come usarli.</span><span class="sxs-lookup"><span data-stu-id="4aa88-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="4aa88-109">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team nell'organizzazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="4aa88-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="4aa88-110">Il servizio Teams è già stato distribuito nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4aa88-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="4aa88-111">Se Teams non è ancora stato ancora implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4aa88-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="4aa88-112">Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="4aa88-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="4aa88-113">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="4aa88-113">Quality and safety</span></span>

<span data-ttu-id="4aa88-114">Centralizzare la comunicazione, l'accesso alle risorse e le operazioni di impianti con un team dello stabilimento di produzione.</span><span class="sxs-lookup"><span data-stu-id="4aa88-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="4aa88-115">Includere documenti su criteri e procedure, video di formazione, avvisi di sicurezza, processi di passaggio di turno.</span><span class="sxs-lookup"><span data-stu-id="4aa88-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="4aa88-116">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="4aa88-116">Base template type</span></span>|<span data-ttu-id="4aa88-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4aa88-117">baseTemplateId</span></span>| <span data-ttu-id="4aa88-118">Proprietà disponibili in questo modello di base</span><span class="sxs-lookup"><span data-stu-id="4aa88-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="4aa88-119">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="4aa88-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="4aa88-120">Canali:</span><span class="sxs-lookup"><span data-stu-id="4aa88-120">Channels:</span></span> <ul><li><span data-ttu-id="4aa88-121">Generale</span><span class="sxs-lookup"><span data-stu-id="4aa88-121">General</span></span><li><span data-ttu-id="4aa88-122">Annunci</span><span class="sxs-lookup"><span data-stu-id="4aa88-122">Announcements</span></span></li><li><span data-ttu-id="4aa88-123">Riga 1</span><span class="sxs-lookup"><span data-stu-id="4aa88-123">Line 1</span></span></li><li><span data-ttu-id="4aa88-124">Riga 2</span><span class="sxs-lookup"><span data-stu-id="4aa88-124">Line 2</span></span></li><li><span data-ttu-id="4aa88-125">Riga 3</span><span class="sxs-lookup"><span data-stu-id="4aa88-125">Line 3</span></span></li><li><span data-ttu-id="4aa88-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4aa88-126">Safety</span></span></li><li><span data-ttu-id="4aa88-127">Formazione</span><span class="sxs-lookup"><span data-stu-id="4aa88-127">Training</span></span></li><li><span data-ttu-id="4aa88-128">Manutenzione</span><span class="sxs-lookup"><span data-stu-id="4aa88-128">Maintenance</span></span></li><li><span data-ttu-id="4aa88-129">Cose divertenti</span><span class="sxs-lookup"><span data-stu-id="4aa88-129">Fun stuff</span></span></li></ul> <span data-ttu-id="4aa88-130">App:</span><span class="sxs-lookup"><span data-stu-id="4aa88-130">Apps:</span></span> <ul><li><span data-ttu-id="4aa88-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="4aa88-131">Wiki</span></span></li><li><span data-ttu-id="4aa88-132">Programmazione</span><span class="sxs-lookup"><span data-stu-id="4aa88-132">Planner</span></span></li></ul>|
||||
