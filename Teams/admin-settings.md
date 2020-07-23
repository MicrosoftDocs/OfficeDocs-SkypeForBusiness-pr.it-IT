---
title: Impostazioni di amministrazione per le app in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Informazioni sui criteri e le impostazioni che è possibile usare per gestire le app per l'organizzazione in Microsoft teams.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ae1776cf57368ea0f18cb6b0e46e5a11dffe447
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45228902"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="e10a0-103">Impostazioni di amministrazione per le app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e10a0-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="e10a0-104">Le app contengono strumenti fuori sede per l'organizzazione per ottenere un numero maggiore di team.</span><span class="sxs-lookup"><span data-stu-id="e10a0-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="e10a0-105">Queste app combinano la funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="e10a0-106">Puoi gestire le app per l'organizzazione in **app teams** nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="e10a0-107">Vedere [usare i ruoli di amministratore di team per gestire i team](https://docs.microsoft.com/microsoftteams/using-admin-roles) per leggere informazioni su come ottenere ruoli di amministratore e autorizzazioni. Ad esempio, puoi consentire o bloccare le app a livello di organizzazione, impostare i criteri per controllare quali app sono disponibili per gli utenti del team e personalizzare i team tramite il blocco delle app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e10a0-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="e10a0-108">Stiamo migliorando continuamente l'esperienza dell'app in teams e aggiungendo funzionalità e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e10a0-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="e10a0-109">Nel corso del tempo creeremo altre funzionalità di gestione delle app, quindi ricontrolla le informazioni più aggiornate sui criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="e10a0-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="e10a0-110">Gestire le app</span><span class="sxs-lookup"><span data-stu-id="e10a0-110">Manage apps</span></span>

<span data-ttu-id="e10a0-111">Usa la pagina **Gestisci app** per visualizzare e gestire tutte le app Teams nel catalogo app dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="e10a0-112">Puoi vedere lo stato e le proprietà a livello di organizzazione delle app, bloccare o consentire le app a livello di organizzazione, caricare nuove app personalizzate nel catalogo del tenant e gestire le impostazioni dell'app in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="e10a0-113">La pagina **Gestisci app** consente di visualizzare tutte le app disponibili nel catalogo del tenant, fornendo le informazioni necessarie per decidere quali app consentire o bloccare in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="e10a0-114">Puoi quindi usare i [criteri di autorizzazione](#app-permission-policies)per le app, i [criteri di configurazione delle app](#app-setup-policies)e i [criteri e le impostazioni delle app personalizzate](#custom-app-policies-and-settings) per configurare l'esperienza dell'app per utenti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="e10a0-115">Per altre informazioni, vedere [gestire le app in teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e10a0-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="e10a0-116">Criteri di autorizzazione app</span><span class="sxs-lookup"><span data-stu-id="e10a0-116">App permission policies</span></span>

<span data-ttu-id="e10a0-117">Con i criteri di autorizzazione delle app, puoi controllare quali app sono disponibili per gli utenti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="e10a0-118">È possibile consentire o bloccare tutte le app o le app specifiche pubblicate da Microsoft, da terze parti e dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="e10a0-119">Ad esempio, puoi usare i criteri di autorizzazione delle app per:</span><span class="sxs-lookup"><span data-stu-id="e10a0-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="e10a0-120">Distribuire gradualmente nuove app di terze parti o personalizzate a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="e10a0-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="e10a0-121">Semplificare l'esperienza utente, soprattutto quando si avvia l'implementazione di team in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e10a0-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="e10a0-122">Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e10a0-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="e10a0-123">Criteri di configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="e10a0-123">App setup policies</span></span>

<span data-ttu-id="e10a0-124">I criteri di configurazione dell'app consentono di personalizzare l'esperienza dell'app per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e10a0-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="e10a0-125">Scegli le app che vuoi aggiungere alla barra dell'app nei client di teams e l'ordine in cui vengono visualizzate, nei client Web, desktop e mobili.</span><span class="sxs-lookup"><span data-stu-id="e10a0-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="e10a0-126">Ecco alcuni esempi di come usare i criteri di configurazione delle app:</span><span class="sxs-lookup"><span data-stu-id="e10a0-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="e10a0-127">Guidare la consapevolezza e l'adozione delle app principali.</span><span class="sxs-lookup"><span data-stu-id="e10a0-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="e10a0-128">Ad esempio, Aggiungi un'app di reclutamento e gestione dei talenti personalizzati per gli utenti del team HR.</span><span class="sxs-lookup"><span data-stu-id="e10a0-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="e10a0-129">Funzionalità di aggiunta selettiva di core team, ad esempio chat, team e chiamate.</span><span class="sxs-lookup"><span data-stu-id="e10a0-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="e10a0-130">In questo modo, puoi garantire agli utenti un'attività specifica in teams.</span><span class="sxs-lookup"><span data-stu-id="e10a0-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="e10a0-131">Per altre informazioni, vedere [gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e10a0-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="e10a0-132">Criteri e impostazioni delle app personalizzate</span><span class="sxs-lookup"><span data-stu-id="e10a0-132">Custom app policies and settings</span></span>

<span data-ttu-id="e10a0-133">Teams consente agli sviluppatori dell'organizzazione di creare, testare e distribuire app personalizzate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="e10a0-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="e10a0-134">Le app personalizzate possono essere aggiunte ai team caricando un pacchetto dell'app in un file con estensione zip direttamente in un team o nel contesto personale.</span><span class="sxs-lookup"><span data-stu-id="e10a0-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="e10a0-135">Puoi usare i criteri di configurazione delle app per controllare chi nell'organizzazione può caricare app personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e10a0-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="e10a0-136">Puoi anche impostare le impostazioni a livello di organizzazione per controllare se gli utenti possono interagire con specifiche app personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e10a0-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="e10a0-137">Per altre informazioni, vedere [gestire i criteri e le impostazioni dell'app personalizzata in teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e10a0-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
