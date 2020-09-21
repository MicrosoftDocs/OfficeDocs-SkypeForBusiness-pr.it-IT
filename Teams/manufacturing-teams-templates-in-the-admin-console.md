---
title: Introduzione ai modelli di manufacturing dei team nella console di amministrazione
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
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze di produzione fornendo impostazioni predefinite, canali e app preinstallate tramite la console di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 896435daaf7b1036a54649e8670b0a19d88b2474
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136062"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="52e76-103">Usare i modelli di manufacturing teams nella console di amministrazione</span><span class="sxs-lookup"><span data-stu-id="52e76-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="52e76-104">I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.</span><span class="sxs-lookup"><span data-stu-id="52e76-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="52e76-105">I modelli di teams hanno definizioni predefinite delle strutture del team progettate in base alle esigenze di produzione.</span><span class="sxs-lookup"><span data-stu-id="52e76-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="52e76-106">Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.</span><span class="sxs-lookup"><span data-stu-id="52e76-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="52e76-107">In questo articolo verranno introdotti tutti i modelli di team e il modo in cui è consigliabile usarli.</span><span class="sxs-lookup"><span data-stu-id="52e76-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="52e76-108">Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione di manufacturing.</span><span class="sxs-lookup"><span data-stu-id="52e76-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="52e76-109">Supponiamo che tu abbia già implementato il servizio teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52e76-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="52e76-110">Se non sono stati ancora distribuiti team, iniziare leggendo la [procedura per l'implementazione di Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="52e76-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="52e76-111">Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates-in-the-admin-console.md)di teams.</span><span class="sxs-lookup"><span data-stu-id="52e76-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="52e76-112">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="52e76-112">Quality and safety</span></span>

<span data-ttu-id="52e76-113">Centralizzare le comunicazioni, l'accesso alle risorse e le operazioni impiantistiche con un team di impianti produttivi.</span><span class="sxs-lookup"><span data-stu-id="52e76-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="52e76-114">Includere documenti relativi a criteri e procedure, video di formazione, avvisi di sicurezza, processi di consegna dei turni.</span><span class="sxs-lookup"><span data-stu-id="52e76-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="52e76-115">Tipo di modello di base</span><span class="sxs-lookup"><span data-stu-id="52e76-115">Base template type</span></span>|<span data-ttu-id="52e76-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="52e76-116">baseTemplateId</span></span> | <span data-ttu-id="52e76-117">Proprietà disponibili con questo modello di base</span><span class="sxs-lookup"><span data-stu-id="52e76-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="52e76-118">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="52e76-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="52e76-119">Canali</span><span class="sxs-lookup"><span data-stu-id="52e76-119">Channels:</span></span> <ul><li><span data-ttu-id="52e76-120">Generale</span><span class="sxs-lookup"><span data-stu-id="52e76-120">General</span></span><li><span data-ttu-id="52e76-121">Annunci</span><span class="sxs-lookup"><span data-stu-id="52e76-121">Announcements</span></span></li><li><span data-ttu-id="52e76-122">Riga 1</span><span class="sxs-lookup"><span data-stu-id="52e76-122">Line 1</span></span></li><li><span data-ttu-id="52e76-123">Linea 2</span><span class="sxs-lookup"><span data-stu-id="52e76-123">Line 2</span></span></li><li><span data-ttu-id="52e76-124">Linea 3</span><span class="sxs-lookup"><span data-stu-id="52e76-124">Line 3</span></span></li><li><span data-ttu-id="52e76-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="52e76-125">Safety</span></span></li><li><span data-ttu-id="52e76-126">Formazione</span><span class="sxs-lookup"><span data-stu-id="52e76-126">Training</span></span></li><li><span data-ttu-id="52e76-127">Manutenzione</span><span class="sxs-lookup"><span data-stu-id="52e76-127">Maintenance</span></span></li><li><span data-ttu-id="52e76-128">Cose divertenti</span><span class="sxs-lookup"><span data-stu-id="52e76-128">Fun stuff</span></span></li></ul> <span data-ttu-id="52e76-129">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="52e76-129">Apps:</span></span> <ul><li><span data-ttu-id="52e76-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="52e76-130">Wiki</span></span></li></ul>|
||||