---
title: Pubblicare app nel catalogo delle app del tenant di Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Linee guida per la pubblicazione di app nel catalogo delle app tenant di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42fd9820f6f8ce11b245412a5ae99ed7b43dbc1e
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793532"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="30f3c-103">Pubblicare app nel catalogo delle app del tenant di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30f3c-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="30f3c-104">È possibile usare il catalogo delle app del tenant di Microsoft teams per testare e distribuire le applicazioni line-of-business alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30f3c-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="30f3c-105">Il catalogo delle app tenant teams consente di distribuire applicazioni line-of-business costruite appositamente per l'organizzazione e di affidarsi alle funzioni aziendali critiche.</span><span class="sxs-lookup"><span data-stu-id="30f3c-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="30f3c-106">Per pubblicare app per l'organizzazione, accedere al client teams usando un account con l'amministratore globale o i ruoli di amministratore del servizio teams e quindi seguire le istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="30f3c-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="30f3c-107">Pubblicare un'app nel catalogo delle app tenant dal client Teams</span><span class="sxs-lookup"><span data-stu-id="30f3c-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="30f3c-108">È necessario avere effettuato l'accesso al client Microsoft teams con un account che include l'amministratore globale o il ruolo di amministratore del servizio teams abilitato per pubblicare le app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30f3c-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="30f3c-109">Leggi altre informazioni sull' [uso dei ruoli di amministratore per gestire i team](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="30f3c-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="30f3c-110">Ottenere un pacchetto dell'app Teams</span><span class="sxs-lookup"><span data-stu-id="30f3c-110">Get a Teams app package</span></span>

<span data-ttu-id="30f3c-111">Viene creato un pacchetto dell'app teams con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="30f3c-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="30f3c-112">Una volta che hai il pacchetto dell'app, puoi aggiungerlo al catalogo dell'app Enterprise.</span><span class="sxs-lookup"><span data-stu-id="30f3c-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="30f3c-113">Mentre tutti gli utenti del tenant possono visualizzare il catalogo delle app, solo gli amministratori globali e i servizi di teams hanno la possibilità di pubblicarli e gestirli.</span><span class="sxs-lookup"><span data-stu-id="30f3c-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="30f3c-114">Vai al catalogo delle app tenant</span><span class="sxs-lookup"><span data-stu-id="30f3c-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="30f3c-115">Avviare il client Microsoft teams ed eseguire l'accesso usando le credenziali di amministratore del servizio globale o teams.</span><span class="sxs-lookup"><span data-stu-id="30f3c-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="30f3c-116">Seleziona **app** sul lato sinistro dell'app e quindi seleziona la nuova sezione denominata per l'organizzazione specifica (in questo esempio, contoso).</span><span class="sxs-lookup"><span data-stu-id="30f3c-116">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="30f3c-117">Gli utenti dell'organizzazione possono visualizzare le app nel catalogo e installarle per i team di cui fanno parte.</span><span class="sxs-lookup"><span data-stu-id="30f3c-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="30f3c-119">Aggiungere un'app al catalogo delle app tenant</span><span class="sxs-lookup"><span data-stu-id="30f3c-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="30f3c-120">Nella pagina **app** selezionare **carica un caricamento di un'app** > personalizzata**per contoso**.</span><span class="sxs-lookup"><span data-stu-id="30f3c-120">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="30f3c-122">Puoi anche scegliere **carica per me o i miei team**, che si chiama *sideload*.</span><span class="sxs-lookup"><span data-stu-id="30f3c-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="30f3c-123">Sideload rende l'app disponibile solo per i team o per i team selezionati.)</span><span class="sxs-lookup"><span data-stu-id="30f3c-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="30f3c-124">Passare al pacchetto dell'app e selezionarlo e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="30f3c-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image03.png)

<span data-ttu-id="30f3c-126">Quando si torna al catalogo delle app tenant, la nuova app Enterprise sarà presente.</span><span class="sxs-lookup"><span data-stu-id="30f3c-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="30f3c-127">Ricordati che solo tu e i membri dell'organizzazione hai accesso a questo catalogo app.</span><span class="sxs-lookup"><span data-stu-id="30f3c-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="30f3c-128">Aggiornare un'app nel catalogo delle app tenant</span><span class="sxs-lookup"><span data-stu-id="30f3c-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="30f3c-129">Dal catalogo delle app tenant selezionare "**...**"</span><span class="sxs-lookup"><span data-stu-id="30f3c-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="30f3c-130">nell'angolo in alto a destra dell'app che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="30f3c-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="30f3c-131">Passare al pacchetto dell'app aggiornata e selezionarlo e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="30f3c-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image04.png)

<span data-ttu-id="30f3c-133">L'app verrà aggiornata alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="30f3c-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="30f3c-134">Puoi anche eliminare l'app per l'intera società da questo menu.</span><span class="sxs-lookup"><span data-stu-id="30f3c-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="30f3c-135">Usare il portale di amministrazione di Office 365 per gestire il catalogo delle app tenant</span><span class="sxs-lookup"><span data-stu-id="30f3c-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="30f3c-136">Se si hanno app che necessitano di correzioni di bug, è possibile disabilitare temporaneamente le app tramite l'interfaccia di amministrazione di Microsoft 365 > i**criteri di autorizzazione** delle**app** > Teams dell'interfaccia di **Amministrazione** > teams > <il nome del criterio, ad esempio "Global (org-Wide default)" > **app tenant** > bloccare app specifiche e consentire a tutti gli altri utenti di aggiungere l'app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="30f3c-136">If you have apps that need bug fixes, you can temporarily disable apps through the Microsoft 365 admin center > **Teams admin center** > **Teams apps** > **Permission Policies** > <policy name, e.g. "Global (Org-wide default)"> **Tenant apps** > Block specific apps and allow all others and add your app to the list.</span></span>

![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image05.png)

<span data-ttu-id="30f3c-138">La disattivazione di un'app impedirà agli utenti di interagire con l'app, senza eliminare completamente l'app.</span><span class="sxs-lookup"><span data-stu-id="30f3c-138">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="30f3c-139">Questi controlli offrono maggiore flessibilità e controllo per la gestione delle app nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30f3c-139">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
