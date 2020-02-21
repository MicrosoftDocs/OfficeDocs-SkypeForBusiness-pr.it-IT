---
title: Pubblicare app nel catalogo delle app del tenant di Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Linee guida per la pubblicazione di app nel catalogo delle app tenant di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161615"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="4947a-103">Pubblicare app nel catalogo delle app del tenant di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4947a-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="4947a-104">Puoi usare il catalogo delle app del tenant di Microsoft teams per testare e distribuire le applicazioni line-of-business alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4947a-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="4947a-105">Il catalogo delle app tenant teams consente di distribuire applicazioni line-of-business costruite appositamente per l'organizzazione e di affidarsi a tutte le funzioni aziendali critiche.</span><span class="sxs-lookup"><span data-stu-id="4947a-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="4947a-106">Per pubblicare le app per l'organizzazione, accedere al client teams usando un account con il ruolo amministratore globale o servizio teams e quindi seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4947a-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="4947a-107">Pubblicare un'app nel catalogo dell'app tenant dal client Teams</span><span class="sxs-lookup"><span data-stu-id="4947a-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="4947a-108">Questa procedura descrive come pubblicare un'app usando il client teams.</span><span class="sxs-lookup"><span data-stu-id="4947a-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="4947a-109">Puoi anche pubblicare un'app nella pagina **Gestisci app** nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4947a-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4947a-110">Per altre informazioni, vedere [gestire le app in teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="4947a-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="4947a-111">Ottenere un pacchetto dell'app Teams</span><span class="sxs-lookup"><span data-stu-id="4947a-111">Get a Teams app package</span></span>

<span data-ttu-id="4947a-112">Viene creato un pacchetto dell'app teams con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="4947a-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="4947a-113">Una volta che hai il pacchetto dell'app, puoi aggiungerlo al catalogo app tenant.</span><span class="sxs-lookup"><span data-stu-id="4947a-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="4947a-114">Mentre tutti gli utenti dell'organizzazione possono visualizzare il catalogo delle app, solo gli amministratori globali e i servizi di teams hanno la possibilità di pubblicarli e gestirli.</span><span class="sxs-lookup"><span data-stu-id="4947a-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="4947a-115">Vai al catalogo app tenant</span><span class="sxs-lookup"><span data-stu-id="4947a-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="4947a-116">Avviare teams ed eseguire l'accesso usando le credenziali di amministratore del servizio globale o teams.</span><span class="sxs-lookup"><span data-stu-id="4947a-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="4947a-117">Seleziona **app** sul lato sinistro dell'app e quindi seleziona la nuova sezione denominata per l'organizzazione specifica (in questo esempio, contoso).</span><span class="sxs-lookup"><span data-stu-id="4947a-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="4947a-118">Gli utenti dell'organizzazione possono visualizzare le app nel catalogo e installarle per i team di cui fanno parte.</span><span class="sxs-lookup"><span data-stu-id="4947a-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="4947a-120">Aggiungere un'app al catalogo dell'app tenant</span><span class="sxs-lookup"><span data-stu-id="4947a-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="4947a-121">Nella pagina **app** selezionare **carica un caricamento di un'app** > personalizzata**per contoso**.</span><span class="sxs-lookup"><span data-stu-id="4947a-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="4947a-123">Puoi anche scegliere **carica per me o i miei team**, che si chiama *sideload*.</span><span class="sxs-lookup"><span data-stu-id="4947a-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="4947a-124">Sideload rende l'app disponibile solo per i team o per i team selezionati.)</span><span class="sxs-lookup"><span data-stu-id="4947a-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="4947a-125">Passare al pacchetto dell'app e selezionarlo e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4947a-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image03.png)

<span data-ttu-id="4947a-127">Quando si torna al catalogo dell'app tenant, la nuova app Enterprise sarà presente.</span><span class="sxs-lookup"><span data-stu-id="4947a-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="4947a-128">Ricordati che solo tu e i membri dell'organizzazione hai accesso a questo catalogo app.</span><span class="sxs-lookup"><span data-stu-id="4947a-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="4947a-129">Aggiornare un'app nel catalogo app tenant</span><span class="sxs-lookup"><span data-stu-id="4947a-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="4947a-130">Dal catalogo dell'app tenant selezionare "**...**"</span><span class="sxs-lookup"><span data-stu-id="4947a-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="4947a-131">nell'angolo in alto a destra dell'app che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4947a-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="4947a-132">Passare al pacchetto dell'app aggiornata e selezionarlo e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4947a-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Screenshot dell'app teams Store che mostra il catalogo app.](media/private-app-store-teams-image04.png)

<span data-ttu-id="4947a-134">L'app verrà aggiornata alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="4947a-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="4947a-135">Puoi anche eliminare l'app per l'intera società da questo menu.</span><span class="sxs-lookup"><span data-stu-id="4947a-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="4947a-136">Usare l'interfaccia di amministrazione di Microsoft teams per gestire il catalogo delle app tenant</span><span class="sxs-lookup"><span data-stu-id="4947a-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="4947a-137">Se si hanno app che necessitano di correzioni di bug, è possibile disabilitare temporaneamente le app per gli utenti in un criterio di autorizzazione per le app.</span><span class="sxs-lookup"><span data-stu-id="4947a-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="4947a-138">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.</span><span class="sxs-lookup"><span data-stu-id="4947a-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="4947a-139">Selezionare i criteri di autorizzazione per le app che si desidera modificare e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4947a-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="4947a-140">In **app tenant**selezionare **Blocca app specifiche e Consenti a tutti gli altri**e quindi aggiungere le app che si vuole bloccare.</span><span class="sxs-lookup"><span data-stu-id="4947a-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="4947a-141">La disattivazione di un'app impedisce agli utenti di interagire con l'app, senza eliminare completamente l'app.</span><span class="sxs-lookup"><span data-stu-id="4947a-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="4947a-142">Questi controlli offrono maggiore flessibilità e controllo per la gestione delle app nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4947a-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="4947a-143">Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4947a-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>