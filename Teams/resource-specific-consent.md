---
title: Consenso specifico delle risorse in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sulle impostazioni che è necessario configurare per controllare se i proprietari dei team nell'organizzazione possono fornire il consenso alle app.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815676"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="b1244-103">Consenso specifico delle risorse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1244-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b1244-104">Il consenso specifico delle risorse in Microsoft Teams consente ai proprietari dei team di dare il consenso alle app per accedere ai dati del team.</span><span class="sxs-lookup"><span data-stu-id="b1244-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="b1244-105">Esempi di tale accesso includono la possibilità di leggere i messaggi del canale, creare ed eliminare canali e creare e rimuovere schede dei canali.</span><span class="sxs-lookup"><span data-stu-id="b1244-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="b1244-106">Come amministratore, puoi controllare se i proprietari dei team nella tua organizzazione possono dare il consenso tramite le impostazioni configurate usando il modulo PowerShell di Azure Active Directory (Azure AD) o il portale di Azure e l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1244-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="b1244-107">Specificare se i proprietari del team possono concedere il consenso alle app</span><span class="sxs-lookup"><span data-stu-id="b1244-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="b1244-108">Ecco le impostazioni che è necessario configurare per controllare se i proprietari del team possono fornire il consenso alle app.</span><span class="sxs-lookup"><span data-stu-id="b1244-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="b1244-109">Assicurarsi di controllare tutte le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b1244-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="b1244-110">Impostazioni in Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1244-110">Settings in Azure AD</span></span>

<span data-ttu-id="b1244-111">Le due impostazioni seguenti determinano se i proprietari del team possono fornire il consenso alle app.</span><span class="sxs-lookup"><span data-stu-id="b1244-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1244-112">La modifica di queste impostazioni non influisce sull'accesso ai dati per le app con il consenso già concesso.</span><span class="sxs-lookup"><span data-stu-id="b1244-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="b1244-113">Ad esempio, se si configurano queste impostazioni per impedire ai proprietari dei team di concedere il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.</span><span class="sxs-lookup"><span data-stu-id="b1244-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="b1244-114">Impostazione "Gli utenti possono acconsentire alle app che accedono ai dati aziendali per loro conto"</span><span class="sxs-lookup"><span data-stu-id="b1244-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="b1244-115">Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app per loro conto.</span><span class="sxs-lookup"><span data-stu-id="b1244-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="b1244-116">Per consentire ai proprietari dei team di fornire il consenso, questa impostazione deve essere impostata su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="b1244-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="b1244-117">Per gestire questa impostazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1244-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="b1244-118">Nel portale di Azure passare a Impostazioni utente **delle applicazioni**  >  **enterprise.**</span><span class="sxs-lookup"><span data-stu-id="b1244-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="b1244-119">Nelle **applicazioni Enterprise** impostare **l'opzione Gli utenti possono acconsentire alle app che accedono ai** dati aziendali per conto loro su **No** o **Sì.**</span><span class="sxs-lookup"><span data-stu-id="b1244-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="b1244-120">È anche possibile gestire questa impostazione con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1244-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="b1244-121">Per altre informazioni, vedere [Configurare il contenuto utente per le applicazioni.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)</span><span class="sxs-lookup"><span data-stu-id="b1244-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="b1244-122">Impostazione "EnableGroupSpecificConsent"</span><span class="sxs-lookup"><span data-stu-id="b1244-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="b1244-123">Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app che accedono ai dati aziendali per i gruppi di loro proprietà.</span><span class="sxs-lookup"><span data-stu-id="b1244-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="b1244-124">Questa impostazione deve essere abilitata per i proprietari del team per fornire il consenso.</span><span class="sxs-lookup"><span data-stu-id="b1244-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="b1244-125">Per la procedura su come gestire questa impostazione con PowerShell, vedere Configurare il consenso del proprietario del gruppo per le app che accedono [ai dati del gruppo.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)</span><span class="sxs-lookup"><span data-stu-id="b1244-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b1244-126">Impostazioni nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1244-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b1244-127">Oltre alle impostazioni in Azure AD, le [](manage-apps.md) impostazioni delle [app](manage-apps.md#manage-org-wide-app-settings) a livello di organizzazione [](manage-apps.md#allow-and-block-apps) nella pagina Gestisci app, se un'app è bloccata o consentita nella pagina Gestisci app e i criteri di autorizzazione per le [app](teams-app-permission-policies.md) assegnati al proprietario del team determinano se un proprietario del team può fornire il consenso.</span><span class="sxs-lookup"><span data-stu-id="b1244-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1244-128">La modifica di queste impostazioni non influisce sull'accesso ai dati per le app con il consenso già concesso.</span><span class="sxs-lookup"><span data-stu-id="b1244-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="b1244-129">Ad esempio, se disattivi app di terze parti a livello di organizzazione o se blocchi app specifiche per impedire ai proprietari del team di fornire il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.</span><span class="sxs-lookup"><span data-stu-id="b1244-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="b1244-130">Impostazione "Consenti app di terze parti" nelle impostazioni delle app a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="b1244-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="b1244-131">Questa impostazione dell'app a livello di organizzazione controlla se gli utenti dell'organizzazione possono usare app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b1244-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="b1244-132">Questa impostazione deve essere attivata per consentire ai proprietari dei team di fornire il consenso.</span><span class="sxs-lookup"><span data-stu-id="b1244-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="b1244-133">Per gestire questa impostazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1244-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="b1244-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Gestisci app di **Teams** e quindi fare clic su  >  Impostazioni app a livello **di organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="b1244-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="b1244-135">In **App di terze parti,** disattiva o attiva Consenti app di terze **parti.**</span><span class="sxs-lookup"><span data-stu-id="b1244-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Screenshot dell'impostazione "Consenti app di terze parti in Teams"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="b1244-137">Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="b1244-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="b1244-138">Consentire o bloccare l'app a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="b1244-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="b1244-139">Quando si blocca o si [](manage-apps.md#allow-and-block-apps) consente un'app nella pagina Gestisci app, l'app viene bloccata o consentita a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1244-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="b1244-140">I proprietari del team possono dare il consenso a un'app solo se l'app è consentita.</span><span class="sxs-lookup"><span data-stu-id="b1244-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="b1244-141">Per consentire o bloccare un'app a livello dell'organizzazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1244-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="b1244-142">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.</span><span class="sxs-lookup"><span data-stu-id="b1244-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b1244-143">Nella pagina Gestisci app selezionare l'app  e quindi fare clic su Blocca per bloccarla o su Consenti **per** consentirla.</span><span class="sxs-lookup"><span data-stu-id="b1244-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Screenshot delle app bloccate nelle impostazioni a livello di organizzazione](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="b1244-145">Criteri di autorizzazione per le app assegnati al proprietario del team</span><span class="sxs-lookup"><span data-stu-id="b1244-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="b1244-146">I proprietari del team possono dare il consenso solo alle app che i criteri di autorizzazione per le app consentono di eseguire.</span><span class="sxs-lookup"><span data-stu-id="b1244-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="b1244-147">Per visualizzare e gestire i criteri di autorizzazione per le app assegnati a un proprietario del team, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1244-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="b1244-148">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="b1244-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b1244-149">Fare doppio clic sul nome visualizzato del proprietario del team e quindi fare clic su **Criteri.**</span><span class="sxs-lookup"><span data-stu-id="b1244-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="b1244-150">I criteri assegnati al proprietario del team sono elencati in **Criteri di autorizzazione app.**</span><span class="sxs-lookup"><span data-stu-id="b1244-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="b1244-151">Per assegnare un criterio diverso, fare clic su **Modifica** e quindi selezionare il criterio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="b1244-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="b1244-152">Per modificare le impostazioni del criterio assegnato al proprietario del team, fare clic sul nome del criterio e quindi apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="b1244-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="b1244-153">Caricamento di app personalizzate</span><span class="sxs-lookup"><span data-stu-id="b1244-153">Uploading custom apps</span></span>

<span data-ttu-id="b1244-154">Quando si carica un'app personalizzata (anche nota come sideload) che usa il consenso specifico della risorsa, l'app deve provengono dal tenant in cui viene installata.</span><span class="sxs-lookup"><span data-stu-id="b1244-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="b1244-155">In altre parole, la registrazione dell'app Azure AD deve essere di questo tenant.</span><span class="sxs-lookup"><span data-stu-id="b1244-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="b1244-156">Gli amministratori globali non sono esenti da questa restrizione e possono caricare app personalizzate da qualsiasi tenant, direttamente in un team (sideload) o nel catalogo app tenant.</span><span class="sxs-lookup"><span data-stu-id="b1244-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1244-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b1244-157">Related topics</span></span>

- [<span data-ttu-id="b1244-158">Autorizzazioni RSC disponibili</span><span class="sxs-lookup"><span data-stu-id="b1244-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="b1244-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b1244-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="b1244-160">Gestire le app nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1244-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="b1244-161">Gestire i criteri di autorizzazione delle app in Teams</span><span class="sxs-lookup"><span data-stu-id="b1244-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
