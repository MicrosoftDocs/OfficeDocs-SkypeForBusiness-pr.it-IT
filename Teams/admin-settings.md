---
title: Impostazioni di amministrazione per le app in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Informazioni sui criteri e le impostazioni che è possibile usare per gestire le app per l'organizzazione in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb824c7082679591b3fa39a1c8a4b13152e0cc75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532523"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="29647-103">Impostazioni di amministrazione per le app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29647-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="29647-104">Le app offrono strumenti avanzati per l'organizzazione per ottenere il maggior numero di utenti da Teams.</span><span class="sxs-lookup"><span data-stu-id="29647-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="29647-105">Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="29647-106">Puoi gestire le app per la tua organizzazione nelle **app di Teams** nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="29647-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="29647-107">Vedere Usare [i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) e ottenere informazioni su come ottenere i ruoli di amministratore e le autorizzazioni. Ad esempio, è possibile consentire o bloccare app a livello di organizzazione, impostare criteri per controllare quali app sono disponibili per gli utenti di Teams e personalizzare Teams bloccando le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="29647-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="29647-108">Stiamo migliorando continuamente l'esperienza dell'app in Teams e aggiungendo funzionalità e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="29647-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="29647-109">Nel corso del tempo verranno integrate altre funzionalità di gestione delle app, quindi controllare di nuovo le informazioni più aggiornate sui criteri delle app.</span><span class="sxs-lookup"><span data-stu-id="29647-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="29647-110">Gestisci app</span><span class="sxs-lookup"><span data-stu-id="29647-110">Manage apps</span></span>

<span data-ttu-id="29647-111">Usare la **pagina Gestisci app** per visualizzare e gestire tutte le app di Teams nel catalogo app dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="29647-112">Puoi visualizzare lo stato e le proprietà a livello di organizzazione delle app, bloccare o consentire le app a livello di organizzazione, caricare nuove app personalizzate nel catalogo tenant e gestire le impostazioni delle app a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="29647-113">La **pagina Gestisci app** offre una visualizzazione di tutte le app disponibili nel catalogo tenant e fornisce le informazioni necessarie per decidere quali app consentire o bloccare nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="29647-114">È quindi possibile usare i criteri di autorizzazione per le [app,](#app-permission-policies)i criteri di configurazione delle [app,](#app-setup-policies)i criteri e le impostazioni delle [app](#custom-app-policies-and-settings) personalizzati per configurare l'esperienza dell'app per utenti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="29647-115">Per altre informazioni, vedere [Gestire le app in Teams.](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="29647-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="29647-116">Criteri di autorizzazione app</span><span class="sxs-lookup"><span data-stu-id="29647-116">App permission policies</span></span>

<span data-ttu-id="29647-117">I criteri di autorizzazione per le app consentono di controllare le app disponibili per utenti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="29647-118">È possibile consentire o bloccare tutte le app o determinate app pubblicate da Microsoft, da terze parti e dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="29647-119">Ad esempio, è possibile usare i criteri di autorizzazione per le app per:</span><span class="sxs-lookup"><span data-stu-id="29647-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="29647-120">Implementare gradualmente app create di terze parti o personalizzate per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="29647-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="29647-121">Semplificare l'esperienza utente, soprattutto quando si avvia l'implementazione di Teams nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29647-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="29647-122">Per altre informazioni, passare a [Gestire i criteri di autorizzazione delle app in Teams.](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29647-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="29647-123">Criteri di configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="29647-123">App setup policies</span></span>

<span data-ttu-id="29647-124">I criteri di configurazione delle app consentono di personalizzare l'esperienza dell'app per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="29647-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="29647-125">È possibile scegliere le app da aggiungere alla barra dell'app nei client di Teams e l'ordine in cui vengono visualizzate, su client Web, desktop e per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="29647-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="29647-126">Ecco alcuni esempi di come è possibile usare i criteri di configurazione delle app:</span><span class="sxs-lookup"><span data-stu-id="29647-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="29647-127">Aumentare la consapevolezza e l'adozione delle app di base.</span><span class="sxs-lookup"><span data-stu-id="29647-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="29647-128">Ad esempio, aggiungere un'app di selezione e gestione dei talenti personalizzata per gli utenti del team delle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="29647-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="29647-129">Aggiungere in modo selettivo le funzionalità principali di Teams, come Chat, Teams e Chiamate.</span><span class="sxs-lookup"><span data-stu-id="29647-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="29647-130">In questo modo ci si assicura che gli utenti siano coinvolti in attività specifiche all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="29647-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="29647-131">Per altre informazioni, vedere Gestire [i criteri di configurazione delle app in Teams.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29647-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="29647-132">Impostazioni e criteri per le app personalizzate</span><span class="sxs-lookup"><span data-stu-id="29647-132">Custom app policies and settings</span></span>

<span data-ttu-id="29647-133">Teams consente agli sviluppatori dell'organizzazione di creare, testare e distribuire app personalizzate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="29647-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="29647-134">È possibile aggiungere app personalizzate a Teams caricando un pacchetto dell'app in un file ZIP direttamente in un team o nel contesto personale.</span><span class="sxs-lookup"><span data-stu-id="29647-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="29647-135">È possibile usare i criteri di configurazione delle app per controllare gli utenti dell'organizzazione che possono caricare app personalizzate.</span><span class="sxs-lookup"><span data-stu-id="29647-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="29647-136">È anche possibile configurare impostazioni a livello di organizzazione per controllare se gli utenti possono interagire con specifiche app personalizzate.</span><span class="sxs-lookup"><span data-stu-id="29647-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="29647-137">Per altre informazioni, vai a Gestire le impostazioni e [i criteri delle app personalizzate in Teams.](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="29647-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
