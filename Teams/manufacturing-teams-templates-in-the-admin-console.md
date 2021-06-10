---
title: Introduzione ai modelli di team di produzione nell'interfaccia di amministrazione
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
description: Informazioni su come usare i modelli di team per creare strutture del team progettate per le esigenze di produzione, fornendo impostazioni predefinite, canali e app preinstallato tramite l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec27cba4336d86f51a32582440d5d7902ffca2b9
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684483"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a><span data-ttu-id="3a370-103">Usare i modelli di team di produzione nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="3a370-103">Use manufacturing team templates in the admin center</span></span>

<span data-ttu-id="3a370-104">I modelli di team consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallato.</span><span class="sxs-lookup"><span data-stu-id="3a370-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3a370-105">I modelli di team hanno definizioni predefinite delle strutture del team progettate in base alle esigenze di produzione.</span><span class="sxs-lookup"><span data-stu-id="3a370-105">Team templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="3a370-106">È anche possibile estendere i modelli di team per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a370-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3a370-107">In questo articolo vengono presentati tutti i modelli di team e viene consigliato come usarli.</span><span class="sxs-lookup"><span data-stu-id="3a370-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="3a370-108">Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="3a370-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="3a370-109">Il servizio Teams è già stato implementato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a370-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3a370-110">Se Teams non è ancora stato implementato, per iniziare, leggere [Come implementare Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3a370-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="3a370-111">Per altre informazioni sui modelli di team in generale, vedere Introduzione [ai modelli di team.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="3a370-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="3a370-112">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a370-112">Quality and safety</span></span>

<span data-ttu-id="3a370-113">Centralizzare le comunicazioni, l'accesso alle risorse e le operazioni degli impianti con un team dell'impianto di produzione.</span><span class="sxs-lookup"><span data-stu-id="3a370-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="3a370-114">Includere documenti di criteri e procedure, video di formazione, avvisi di sicurezza, processi di passaggio del turno.</span><span class="sxs-lookup"><span data-stu-id="3a370-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="3a370-115">Tipologia di modello base</span><span class="sxs-lookup"><span data-stu-id="3a370-115">Base template type</span></span>|<span data-ttu-id="3a370-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3a370-116">baseTemplateId</span></span>| <span data-ttu-id="3a370-117">Proprietà del modello base</span><span class="sxs-lookup"><span data-stu-id="3a370-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3a370-118">Qualità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a370-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="3a370-119">Canali:</span><span class="sxs-lookup"><span data-stu-id="3a370-119">Channels:</span></span> <ul><li><span data-ttu-id="3a370-120">Generale</span><span class="sxs-lookup"><span data-stu-id="3a370-120">General</span></span><li><span data-ttu-id="3a370-121">Annunci</span><span class="sxs-lookup"><span data-stu-id="3a370-121">Announcements</span></span></li><li><span data-ttu-id="3a370-122">Riga 1</span><span class="sxs-lookup"><span data-stu-id="3a370-122">Line 1</span></span></li><li><span data-ttu-id="3a370-123">Riga 2</span><span class="sxs-lookup"><span data-stu-id="3a370-123">Line 2</span></span></li><li><span data-ttu-id="3a370-124">Riga 3</span><span class="sxs-lookup"><span data-stu-id="3a370-124">Line 3</span></span></li><li><span data-ttu-id="3a370-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a370-125">Safety</span></span></li><li><span data-ttu-id="3a370-126">Formazione</span><span class="sxs-lookup"><span data-stu-id="3a370-126">Training</span></span></li><li><span data-ttu-id="3a370-127">Manutenzione</span><span class="sxs-lookup"><span data-stu-id="3a370-127">Maintenance</span></span></li><li><span data-ttu-id="3a370-128">Cose divertenti</span><span class="sxs-lookup"><span data-stu-id="3a370-128">Fun stuff</span></span></li></ul> <span data-ttu-id="3a370-129">App:</span><span class="sxs-lookup"><span data-stu-id="3a370-129">Apps:</span></span> <ul><li><span data-ttu-id="3a370-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="3a370-130">Wiki</span></span></li><li><span data-ttu-id="3a370-131">Programmazione</span><span class="sxs-lookup"><span data-stu-id="3a370-131">Planner</span></span></li></ul>|
||||