---
title: Acquistare app di terze parti per Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Informazioni su come acquistare app di terze parti per Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3b90af2e0fecba2d6c421a5b26547e93b18df05d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196180"
---
<a name="purchase-third-party-apps-for-teams"></a><span data-ttu-id="40a0e-103">Acquistare app di terze parti per Teams</span><span class="sxs-lookup"><span data-stu-id="40a0e-103">Purchase third-party apps for Teams</span></span>
======================================================

> [!NOTE]
> <span data-ttu-id="40a0e-104">Questa funzionalità è attualmente disponibile solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="40a0e-104">This feature is currently only available in the United States.</span></span>

<span data-ttu-id="40a0e-105">Le app Teams sono gratuite per l'installazione e alcune possono richiedere l'acquisto di abbonamenti a servizi per sperimentare tutte le funzionalità e l'ambito dell'app.</span><span class="sxs-lookup"><span data-stu-id="40a0e-105">Teams apps are free to install and some may require purchasing service subscriptions to experience the app's full functionality and scope.</span></span> <span data-ttu-id="40a0e-106">Questi abbonamenti a servizi sono chiamati offerte SaaS (Software as a Service), che possono essere acquistate tramite [AppSource](https://appsource.microsoft.com/) e ora tramite l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40a0e-106">These service subscriptions are called Software as a Service (SaaS) offers, which are available for purchase through [AppSource](https://appsource.microsoft.com/) and now through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="40a0e-107">La [pagina Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams consente di visualizzare e gestire tutte le app di Teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a0e-107">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="40a0e-108">Ad esempio, puoi visualizzare lo stato e le proprietà delle app a livello di organizzazione, caricare nuove app personalizzate nell'App Store della tua organizzazione, bloccare o consentire le app a livello di organizzazione e gestire le impostazioni delle app a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a0e-108">For example, you can see the org-level status and properties of apps, upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="40a0e-109">Qui è anche possibile acquistare licenze per i servizi offerti da app di terze parti per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a0e-109">Here, you can also purchase licenses for services offered by third-party apps for users in your organization.</span></span> <span data-ttu-id="40a0e-110">La **colonna** Licenze nella tabella indica se un'app offre un abbonamento SaaS per l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="40a0e-110">The **Licenses** column in the table indicates whether an app offers a SaaS subscription for purchase.</span></span>

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot che mostra app di terze parti con abbonamenti SaaS":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a><span data-ttu-id="40a0e-112">Cercare e acquistare servizi per un'app di terze parti</span><span class="sxs-lookup"><span data-stu-id="40a0e-112">Search for and purchase services for a third-party app</span></span>

1. <span data-ttu-id="40a0e-113">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.</span><span class="sxs-lookup"><span data-stu-id="40a0e-113">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="40a0e-114">È necessario essere un amministratore globale o un amministratore dei servizi di Teams per accedere alla pagina.</span><span class="sxs-lookup"><span data-stu-id="40a0e-114">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="40a0e-115">Cercare l'app desiderata.</span><span class="sxs-lookup"><span data-stu-id="40a0e-115">Search for the app that you want.</span></span> <span data-ttu-id="40a0e-116">Per identificare le app con un abbonamento SaaS a pagamento, cercare nella **colonna** Licenze.</span><span class="sxs-lookup"><span data-stu-id="40a0e-116">To identify apps that have a paid SaaS subscription, look in the **Licenses** column.</span></span> <span data-ttu-id="40a0e-117">Ogni app avrà uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a0e-117">Each app will have one of the following values:</span></span>
    - <span data-ttu-id="40a0e-118">**Acquista ora:** l'app offre un abbonamento SaaS ed è disponibile per l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="40a0e-118">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="40a0e-119">**Acquistato:** l'app offre un abbonamento SaaS per cui sono state acquistate licenze.</span><span class="sxs-lookup"><span data-stu-id="40a0e-119">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="40a0e-120">**- :** l'app non offre un abbonamento SaaS.</span><span class="sxs-lookup"><span data-stu-id="40a0e-120">**- -**: The app doesn't offer a SaaS subscription.</span></span>
3. <span data-ttu-id="40a0e-121">Dopo aver trovato l'app, fare  clic **su** Acquista ora per passare alla scheda Piani e prezzi della pagina dei dettagli dell'app.</span><span class="sxs-lookup"><span data-stu-id="40a0e-121">When you find the app, click **Purchase now** to go to the **Plans and pricing** tab of the app details page.</span></span> <span data-ttu-id="40a0e-122">Esaminare i piani e le informazioni sui prezzi per l'offerta SaaS per l'app.</span><span class="sxs-lookup"><span data-stu-id="40a0e-122">Review the plans and pricing information for the SaaS offer for the app.</span></span> <span data-ttu-id="40a0e-123">Se servono altre informazioni, fare clic sul collegamento **Altre** informazioni per passare alla pagina dell'app in [AppSource.](https://appsource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="40a0e-123">If you need more information, click the **learn more** link to go to the app's page on [AppSource](https://appsource.microsoft.com/).</span></span>  
4. <span data-ttu-id="40a0e-124">Per acquistare un piano, fare clic **su Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="40a0e-124">To buy a plan, click **Purchase now**.</span></span> <span data-ttu-id="40a0e-125">Si verrà reindirizzati all'esperienza di acquisto per l'offerta associata all'app Teams.</span><span class="sxs-lookup"><span data-stu-id="40a0e-125">You'll be redirected to the purchase experience for the offer associated with the Teams app.</span></span> <span data-ttu-id="40a0e-126">È qui che completerai l'acquisto del servizio o dell'offerta SaaS.</span><span class="sxs-lookup"><span data-stu-id="40a0e-126">This is where you'll complete your purchase of the service or SaaS offer.</span></span>
5. <span data-ttu-id="40a0e-127">Scegliere il piano desiderato.</span><span class="sxs-lookup"><span data-stu-id="40a0e-127">Choose the plan that you want.</span></span> <span data-ttu-id="40a0e-128">Se l'offerta SaaS include più piani, fare clic su **Cambia** per visualizzare l'elenco dei piani disponibili.</span><span class="sxs-lookup"><span data-stu-id="40a0e-128">If the SaaS offer includes more than one plan, click **Change** to see the list of available plans.</span></span>
6. <span data-ttu-id="40a0e-129">Selezionare il periodo  di fatturazione (mensile o **annuale)** e quindi immettere il numero di licenze utente da acquistare.</span><span class="sxs-lookup"><span data-stu-id="40a0e-129">Select your billing term (either **Monthly** or **Yearly**), and then enter the number of user licenses that you want to buy.</span></span>
7. <span data-ttu-id="40a0e-130">Immetti il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="40a0e-130">Enter your payment method.</span></span>
8. <span data-ttu-id="40a0e-131">Quando sei pronto, seleziona Eseguire **l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="40a0e-131">When you're ready, select **Place order**.</span></span>
9. <span data-ttu-id="40a0e-132">Fare **clic su Configura ora** per attivare l'abbonamento nel sito Web del publisher.</span><span class="sxs-lookup"><span data-stu-id="40a0e-132">Click **Configure now** to activate your subscription on the publisher's website.</span></span>

<span data-ttu-id="40a0e-133">Dopo aver acquistato l'offerta SaaS associata all'app di Teams,  è possibile visualizzare i dettagli di acquisto seguenti nella scheda Piani e prezzi della pagina dei dettagli dell'app.</span><span class="sxs-lookup"><span data-stu-id="40a0e-133">After you've purchased the SaaS offer associated with the Teams app, you can view the following purchase details on the **Plans and pricing** tab of the app details page.</span></span>

- <span data-ttu-id="40a0e-134">**Data di attivazione della** licenza: data in cui è stata attivata la licenza.</span><span class="sxs-lookup"><span data-stu-id="40a0e-134">**License activation date**: Date on which your license was activated.</span></span> <span data-ttu-id="40a0e-135">Se l'account non è ancora configurato, viene visualizzato come Attivazione in sospeso **dell'abbonamento.**</span><span class="sxs-lookup"><span data-stu-id="40a0e-135">If your account isn't yet set up, this shows as **Subscription pending activation**.</span></span>
- <span data-ttu-id="40a0e-136">**Licenze:** numero di licenze acquistate.</span><span class="sxs-lookup"><span data-stu-id="40a0e-136">**Licenses**: Number of licenses you purchased.</span></span>

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot della scheda Piani e prezzi della pagina dei dettagli dell'app":::

<span data-ttu-id="40a0e-138">Selezionare **Gestisci licenze** per passare all'interfaccia di amministrazione di Microsoft 365 per visualizzare e gestire le licenze acquistate e per gestire le assegnazioni di licenze per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="40a0e-138">Select **Manage licenses** to go to the Microsoft 365 admin center to view and manage the licenses you purchased and to manage license assignments for users.</span></span>

<span data-ttu-id="40a0e-139">Gli amministratori globali possono visualizzare gli acquisti effettuati da chiunque nell'organizzazione, mentre gli amministratori dei servizi di Teams possono visualizzare solo gli acquisti effettuati da soli.</span><span class="sxs-lookup"><span data-stu-id="40a0e-139">Global admins can view the purchases made by anyone in the organization whereas Teams service admins can only view the purchases made by themselves.</span></span>  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a><span data-ttu-id="40a0e-140">Hai un'offerta SaaS per un'app Teams che desideri elencare e vendere nell'interfaccia di amministrazione di Microsoft Teams e in AppSource?</span><span class="sxs-lookup"><span data-stu-id="40a0e-140">Have a SaaS offer for a Teams app that you want to list and sell in the Microsoft Teams admin center and AppSource?</span></span>

<span data-ttu-id="40a0e-141">Gli sviluppatori possono creare offerte SaaS associate alle loro app di Teams.</span><span class="sxs-lookup"><span data-stu-id="40a0e-141">Developers can create SaaS offers associated with their Teams apps.</span></span> <span data-ttu-id="40a0e-142">Queste offerte vengono pubblicate tramite il [Centro per i partner](https://partner.microsoft.com) e sono disponibili per l'acquisto da parte delle organizzazioni tramite [AppSource](https://appsource.microsoft.com/) e l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40a0e-142">These offers are published through [Partner Center](https://partner.microsoft.com) and are available for organizations to purchase through [AppSource](https://appsource.microsoft.com/) and the Microsoft Teams admin center.</span></span>
 
<span data-ttu-id="40a0e-143">Gli sviluppatori di app di terze parti [possono accedere a Creare un'offerta SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="40a0e-143">Third-party app developers can go to [Create a SaaS offer](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) for more information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40a0e-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="40a0e-144">Related topics</span></span>

- [<span data-ttu-id="40a0e-145">Gestire le app nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40a0e-145">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="40a0e-146">Creare un'offerta SaaS</span><span class="sxs-lookup"><span data-stu-id="40a0e-146">Create a SaaS offer</span></span>](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
