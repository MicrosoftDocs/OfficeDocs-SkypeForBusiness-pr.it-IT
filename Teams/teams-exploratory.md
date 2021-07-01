---
title: Gestire l'esperienza Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Gli utenti di Microsoft 365 o Office 365 che non hanno una licenza di Microsoft Teams possono iniziare a usare una licenza Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8803219c93a66d7094ce6ca1aa635f1fbff8580e
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230553"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="d14d3-103">Gestire la licenza di Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="d14d3-p101">L'esperienza Microsoft Teams Exploratory consente agli utenti dell'organizzazione che hanno Azure Active Directory (AAD) e non hanno una licenza per Teams di iniziare a usare un'esperienza esplorativa di Teams. Gli amministratori possono attivare o disattivare questa funzionalità per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d14d3-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="d14d3-106">Contenuto dell'esperienza Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="d14d3-107">I piani di servizio che un amministratore visualizzerà nell'ambito dell'esperienza Teams Exploratory sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d14d3-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="d14d3-108">Exchange Online (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="d14d3-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="d14d3-109">Flow per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d14d3-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="d14d3-110">Insights by MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="d14d3-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="d14d3-111">Microsoft Forms (Piano E1)</span><span class="sxs-lookup"><span data-stu-id="d14d3-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="d14d3-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="d14d3-112">Microsoft Planner</span></span>
- <span data-ttu-id="d14d3-113">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d14d3-113">Microsoft Search</span></span>
- <span data-ttu-id="d14d3-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="d14d3-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="d14d3-115">SKU Microsoft Stream per Microsoft 365 e Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="d14d3-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="d14d3-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d14d3-116">Microsoft Teams</span></span>
- <span data-ttu-id="d14d3-117">Gestione di dispositivi mobili per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d14d3-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="d14d3-118">App di Office Mobile per Office 365</span><span class="sxs-lookup"><span data-stu-id="d14d3-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="d14d3-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="d14d3-119">Office Online</span></span>
- <span data-ttu-id="d14d3-120">PowerApps per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d14d3-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="d14d3-121">SharePoint Online (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="d14d3-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="d14d3-122">Sway</span><span class="sxs-lookup"><span data-stu-id="d14d3-122">Sway</span></span>
- <span data-ttu-id="d14d3-123">To-Do (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="d14d3-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="d14d3-124">Whiteboard (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="d14d3-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="d14d3-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="d14d3-125">Yammer Enterprise</span></span>

  <span data-ttu-id="d14d3-126"><sup>1</sup> Il passaggio dall’uso di Microsoft Stream all’uso di [OneDrive for Business e SharePoint per le registrazioni delle riunioni](tmr-meeting-recording-change.md) avverrà in modo graduale.</span><span class="sxs-lookup"><span data-stu-id="d14d3-126"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="d14d3-127">Al momento dell’avvio, sarà possibile acconsentire esplicitamente a questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="d14d3-127">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="d14d3-128">Se si vuole continuare a usare Stream, a novembre sarà necessario rifiutare esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-128">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="d14d3-129">All'inizio del 2021, tutti i clienti dovranno usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d14d3-129">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="d14d3-130">Chi è idoneo</span><span class="sxs-lookup"><span data-stu-id="d14d3-130">Who's eligible</span></span>

<span data-ttu-id="d14d3-131">Gli utenti soddisfano i criteri per un'esperienza Teams Exploratory se:</span><span class="sxs-lookup"><span data-stu-id="d14d3-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="d14d3-132">Hanno un indirizzo di posta elettronica gestito nel dominio di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="d14d3-133">Appartengono a un tenant con un abbonamento a pagamento.</span><span class="sxs-lookup"><span data-stu-id="d14d3-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="d14d3-134">Non hanno una licenza di Teams attiva.</span><span class="sxs-lookup"><span data-stu-id="d14d3-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="d14d3-135">Nonsono in un tenant in cui sono stati creati i criteri di assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="d14d3-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="d14d3-136">Gli utenti devono essere abilitati all'iscrizione per app e versioni di valutazione (nell'interfaccia di amministrazione di Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d14d3-136">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="d14d3-137">Per altre informazioni, vedere [Gestire l'esperienza Teams Exploratory](#manage-the-teams-exploratory-experience) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d14d3-137">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="d14d3-138">Chi non è idoneo</span><span class="sxs-lookup"><span data-stu-id="d14d3-138">Who isn't eligible</span></span>

<span data-ttu-id="d14d3-139">Gli utenti non soddisfano i criteri se:</span><span class="sxs-lookup"><span data-stu-id="d14d3-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="d14d3-140">al momento o in precedenza disponevano di Teams con una licenza a pagamento, non pagata o di prova</span><span class="sxs-lookup"><span data-stu-id="d14d3-140">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="d14d3-141">si trovano in un tenant che usava/riceveva almeno un'offerta speciale COVID.</span><span class="sxs-lookup"><span data-stu-id="d14d3-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="d14d3-142">L'organizzazione non è idonea per questa offerta se è un Syndication Partner Customer oppure un cliente GCC, GCC High, DoD o EDU.</span><span class="sxs-lookup"><span data-stu-id="d14d3-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="d14d3-143">Come aderire all'esperienza Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="d14d3-144">Gli utenti idonei possono aderire all'esperienza Teams Exploratory eseguendo l'accesso a Teams dal desktop o sul Web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="d14d3-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="d14d3-145">Al momento, l'abilitazione di Teams Exploratory tramite dispositivi mobili non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d14d3-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="d14d3-146">Al momento dell’iscrizione, questa licenza verrà loro assegnata automaticamente e l'amministratore del tenant riceverà una notifica tramite posta elettronica la prima volta che un utente dell'organizzazione avvia l'esperienza Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="d14d3-147">Gestire l'esperienza Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="d14d3-148">L'esperienza Teams Exploratory deve essere avviata da singoli utenti finali e non può essere avviata per conto dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d14d3-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="d14d3-149">L'esperienza Teams Exploratory include una licenza di Exchange Online, la cui assegnazione deve essere eseguita dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="d14d3-149">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="d14d3-150">Se l'utente non ha già una licenza di Exchange e l'amministratore non ha ancora assegnato la licenza di Exchange Online, l'utente non potrà pianificare riunioni in Teams e potrebbe non avere accesso ad altre funzionalità di Teams.</span><span class="sxs-lookup"><span data-stu-id="d14d3-150">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="d14d3-151">Gli amministratori possono impedire agli utenti finali di eseguire l'esperienza Teams Exploratory all'interno dell'organizzazione usando l'interruttore **Consenti agli utenti di installare le versioni di valutazione di app e servizi**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="d14d3-152">Impedire agli utenti di installare le versioni di valutazione di app e servizi</span><span class="sxs-lookup"><span data-stu-id="d14d3-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="d14d3-153">È possibile disattivare la possibilità di installare versioni di valutazione di app e servizi, che non consentirebbero agli utenti di eseguire l'esperienza Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="d14d3-154">Nell'interfaccia di amministrazione di Microsoft 365, passare a **Impostazioni** > **Impostazioni organizzazione**, selezionare **Servizi**, quindi **App e servizi di proprietà dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![pagina Servizi nell'interfaccia di amministrazione](media/iw-trial-services.png)

2. <span data-ttu-id="d14d3-156">Eliminare il segno di spunta da **Consenti agli utenti di installare le versioni di valutazione di app e servizi**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![pagina App e servizi di proprietà degli utenti nell'interfaccia di amministrazione](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="d14d3-158">Se l'organizzazione non è idonea per l'esperienza Teams Exploratory, l'opzione **Consenti agli utenti di installare le versioni di valutazione di app e servizi** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d14d3-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="d14d3-159">Gestire la disponibilità per un utente con una licenza che include Teams</span><span class="sxs-lookup"><span data-stu-id="d14d3-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="d14d3-160">Un utente a cui è stata assegnata una licenza che include Teams non è idoneo per l'esperienza Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-160">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="d14d3-161">Quando il piano di servizio Teams è attivato, l'utente può accedere e usare Teams.</span><span class="sxs-lookup"><span data-stu-id="d14d3-161">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="d14d3-162">Se il piano di servizio è disabilitato, l'utente non può accedere e l'esperienza Teams Exploratory non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d14d3-162">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="d14d3-163">È necessario avere i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d14d3-163">You must have admin privileges.</span></span>

<span data-ttu-id="d14d3-164">Per disattivare l'accesso a Teams:</span><span class="sxs-lookup"><span data-stu-id="d14d3-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="d14d3-165">Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Utenti** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="d14d3-166">Selezionare la casella accanto al nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="d14d3-167">Nella riga **Licenze di prodotto** scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="d14d3-168">Nel riquadro **Licenze di prodotto** spostare l'interruttore nella posizione **No**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![pagina Licenze di prodotto nell'interfaccia di amministrazione.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="d14d3-170">Gestire la disponibilità di Teams per gli utenti che usano già l'esperienza Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="d14d3-p107">Se un utente usa già l'esperienza Teams Exploratory, è possibile disattivarla rimuovendo la licenza o il piano di servizio. Per procedere in tal senso, è necessario disporre dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d14d3-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="d14d3-173">Per disattivare la licenza dell'esperienza Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="d14d3-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="d14d3-174">Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Utenti** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="d14d3-175">Selezionare la casella accanto al nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="d14d3-176">Nella riga **Licenze di prodotto** scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="d14d3-177">Nel riquadro **Licenze di prodotto** spostare l'interruttore relativo alla licenza Exploratory nella posizione **No**.</span><span class="sxs-lookup"><span data-stu-id="d14d3-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d14d3-178">L'interruttore Teams Exploratory verrà visualizzato dopo che il primo utente dell'organizzazione ha avviato l'esperienza Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="d14d3-179">Gestire Teams per gli utenti che hanno la licenza di Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="d14d3-180">Gli utenti che hanno una licenza di Teams Exploratory possono essere gestiti nello stesso modo in cui si gestiscono gli utenti con una normale licenza a pagamento.</span><span class="sxs-lookup"><span data-stu-id="d14d3-180">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="d14d3-181">Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d14d3-181">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="d14d3-182">Aggiornare gli utenti da Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="d14d3-183">Per aggiornare gli utenti da Teams Exploratory, è necessario disporre dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d14d3-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="d14d3-184">Per altre informazioni, vedere [Aggiornare gli utenti dalla versione di valutazione di Teams Exploratory](upgrade-from-teams-exploratory.md).</span><span class="sxs-lookup"><span data-stu-id="d14d3-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d14d3-185">Se allo scadere della licenza di Teams Exploratory non viene immediatamente eseguito l'aggiornamento a un abbonamento che include Teams, l'utente perderà l'accesso a Teams dopo un periodo di prova di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d14d3-185">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period.</span></span> <span data-ttu-id="d14d3-186">Altri 30 giorni, trascorsi i quali i dati verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="d14d3-186">Another 30 days after which, the data is deleted.</span></span> <span data-ttu-id="d14d3-187">L'utente esiste ancora in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d14d3-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="d14d3-188">Una volta assegnata una nuova licenza all'utente per abilitare nuovamente le funzionalità di Teams, tutto il contenuto sarà ancora disponibile se l'utente viene aggiunto entro il periodo di tolleranza.</span><span class="sxs-lookup"><span data-stu-id="d14d3-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="d14d3-189">Rimuovere una licenza di Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="d14d3-190">Se si vuole rimuovere questa licenza con PowerShell, vedere [Rimuovere le licenze dagli account utente con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="d14d3-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="d14d3-191">Se si vuole rimuovere questa licenza tramite il portale di amministrazione, vedere [Eliminare un utente dall'organizzazione](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="d14d3-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="d14d3-192">Quali sono i criteri di conservazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d14d3-192">What is the data retention policy</span></span>

<span data-ttu-id="d14d3-193">Vedere le [Informazioni sull'abbonamento a Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d14d3-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="d14d3-194">Durata dell'esperienza di Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="d14d3-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="d14d3-195">A partire dall'inizio del 2021, Teams Exploratory è disponibile con un abbonamento di 12 mesi, dall'iscrizione iniziale degli utenti, per tutti i nuovi clienti.</span><span class="sxs-lookup"><span data-stu-id="d14d3-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="d14d3-196">Il nuovo abbonamento a Teams Exploratory inizia dal momento dell’iscrizione del primo utente e scadrà dopo 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="d14d3-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="d14d3-197">La data di fine verrà applicata a tutti gli utenti dello stesso tenant, con un periodo di 12 mesi a partire dalla data di iscrizione del primo utente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="d14d3-198">La data di fine è configurata a livello di organizzazione, il che significa che verrà applicata a tutti gli utenti della stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d14d3-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="d14d3-199">Ad esempio, l'utente 1 inizia l'abbonamento il 1° gennaio 2021.</span><span class="sxs-lookup"><span data-stu-id="d14d3-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="d14d3-200">Pertanto, la data di fine dell'abbonamento sarà il 31 dicembre 2021.</span><span class="sxs-lookup"><span data-stu-id="d14d3-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="d14d3-201">Un altro utente, l’utente 2, inizia l'abbonamento il 1° ottobre 2021.</span><span class="sxs-lookup"><span data-stu-id="d14d3-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="d14d3-202">L'utente 2 può usare Teams Exploratory per due mesi, perché la data di fine sarà il 31 dicembre 2021 poiché fa parte dell'abbonamento della stessa organizzazione dell'utente 1.</span><span class="sxs-lookup"><span data-stu-id="d14d3-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="d14d3-203">Cosa devono fare gli amministratori alla fine dei 12 mesi</span><span class="sxs-lookup"><span data-stu-id="d14d3-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="d14d3-204">Alla fine dell'abbonamento di 12 mesi, gli amministratori devono convertire tutti gli utenti di Teams Exploratory in una licenza a pagamento che include Teams.</span><span class="sxs-lookup"><span data-stu-id="d14d3-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="d14d3-205">È fondamentale assicurarsi che questa operazione venga completata prima che scada l'abbonamento a Teams Exploratory per evitare l’interruzione dell'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="d14d3-206">I clienti verranno disabilitati e sarà loro impedito l'avvio di una nuova licenza per la versione di valutazione Exploratory per tre mesi dopo la scadenza della precedente.</span><span class="sxs-lookup"><span data-stu-id="d14d3-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="d14d3-207">Per altre informazioni, vedere [Aggiornare gli utenti da Teams Exploratory](#upgrade-users-from-teams-exploratory), in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d14d3-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
