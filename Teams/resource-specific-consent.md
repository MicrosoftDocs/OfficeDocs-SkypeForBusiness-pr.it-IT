---
title: Consenso specifico delle risorse in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sulle impostazioni che è necessario configurare per controllare se i proprietari dei team dell'organizzazione possono dare il consenso alle app.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256602"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="ae907-103">Consenso specifico delle risorse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae907-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="ae907-104">Il consenso specifico delle risorse in Microsoft teams consente ai proprietari del team di consentire alle app di accedere ai dati del team.</span><span class="sxs-lookup"><span data-stu-id="ae907-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="ae907-105">Esempi di questo tipo di accesso includono la possibilità di leggere i messaggi del canale, creare ed eliminare canali e creare e rimuovere le schede dei canali.</span><span class="sxs-lookup"><span data-stu-id="ae907-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="ae907-106">Come amministratore, puoi controllare se i proprietari del team dell'organizzazione possono dare il consenso tramite le impostazioni configurate usando il modulo PowerShell di Azure Active Directory (Azure AD) o il portale di Azure e l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ae907-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="ae907-107">Imposta se i proprietari del team possono dare il consenso alle app</span><span class="sxs-lookup"><span data-stu-id="ae907-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="ae907-108">Ecco le impostazioni che devi impostare per controllare se i proprietari del team possono dare il consenso alle app.</span><span class="sxs-lookup"><span data-stu-id="ae907-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="ae907-109">Assicurarsi di esaminare tutte le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ae907-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="ae907-110">Impostazioni in Azure AD</span><span class="sxs-lookup"><span data-stu-id="ae907-110">Settings in Azure AD</span></span>

<span data-ttu-id="ae907-111">Le due impostazioni seguenti determinano se i proprietari del team possono dare il consenso alle app.</span><span class="sxs-lookup"><span data-stu-id="ae907-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae907-112">La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso.</span><span class="sxs-lookup"><span data-stu-id="ae907-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="ae907-113">Ad esempio, se si configurano queste impostazioni per impedire ai proprietari del team di concedere il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.</span><span class="sxs-lookup"><span data-stu-id="ae907-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="ae907-114">L'impostazione "gli utenti possono acconsentire alle app per l'accesso ai dati aziendali per loro conto"</span><span class="sxs-lookup"><span data-stu-id="ae907-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="ae907-115">Questa impostazione controlla se gli utenti dell'organizzazione possono acconsentire alle app per loro conto.</span><span class="sxs-lookup"><span data-stu-id="ae907-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="ae907-116">Per consentire ai proprietari del team di dare il consenso, questa impostazione deve essere impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ae907-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="ae907-117">Per gestire questa impostazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae907-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="ae907-118">In Azure Portal passa a **Enterprise applications**  >  **impostazioni utente delle**applicazioni Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ae907-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="ae907-119">In **applicazioni aziendali**, imposta **gli utenti possono consentire alle app di accedere ai dati aziendali per loro conto** in **No** o **Yes**.</span><span class="sxs-lookup"><span data-stu-id="ae907-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="ae907-120">È anche possibile gestire questa impostazione usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae907-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="ae907-121">Per altre informazioni, vedere [configurare il contenuto utente nelle applicazioni](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span><span class="sxs-lookup"><span data-stu-id="ae907-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="ae907-122">Impostazione "EnableGroupSpecificConsent"</span><span class="sxs-lookup"><span data-stu-id="ae907-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="ae907-123">Questa impostazione controlla se gli utenti dell'organizzazione possono consentire alle app di accedere ai dati aziendali per i gruppi di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="ae907-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="ae907-124">Questa impostazione deve essere abilitata per i proprietari del team per dare il consenso.</span><span class="sxs-lookup"><span data-stu-id="ae907-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="ae907-125">Per istruzioni su come gestire questa impostazione usando PowerShell, vedere Configurare il [consenso del proprietario del gruppo alle app che accedono ai dati del gruppo](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span><span class="sxs-lookup"><span data-stu-id="ae907-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae907-126">Impostazioni nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae907-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="ae907-127">Oltre alle impostazioni in Azure AD, le [impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings) nella pagina [Manage Apps](manage-apps.md) , indipendentemente dal fatto che un'app sia bloccata o consentita nella pagina [Gestisci](manage-apps.md#allow-and-block-apps) app, e i [criteri di autorizzazione dell'app](teams-app-permission-policies.md) assegnati al proprietario del team determinano se il proprietario del team può concedere il consenso.</span><span class="sxs-lookup"><span data-stu-id="ae907-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae907-128">La modifica di queste impostazioni non influisce sull'accesso ai dati per le app a cui è già stato concesso il consenso.</span><span class="sxs-lookup"><span data-stu-id="ae907-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="ae907-129">Ad esempio, se si disabilitano le app di terze parti a livello di organizzazione o se si bloccano app specifiche per evitare che i proprietari del team diano il consenso, queste modifiche non rimuovono l'accesso ai dati già concesso.</span><span class="sxs-lookup"><span data-stu-id="ae907-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="ae907-130">Impostazione "Consenti app di terze parti" nelle impostazioni dell'app a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae907-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="ae907-131">Questa impostazione dell'app a livello di organizzazione controlla se gli utenti possono usare app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ae907-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="ae907-132">Questa impostazione deve essere attivata per consentire ai proprietari del team di fornire il consenso.</span><span class="sxs-lookup"><span data-stu-id="ae907-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="ae907-133">Per gestire questa impostazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae907-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="ae907-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**, quindi fai clic su **impostazioni dell'app a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ae907-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="ae907-135">In **app di terze parti**disattivare o attivare **Consenti app**di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ae907-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Screenshot dell'impostazione "Consenti app di terze parti in teams"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="ae907-137">Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="ae907-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="ae907-138">Consentire o bloccare l'app a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae907-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="ae907-139">Quando blocchi o Consenti un'app nella pagina [Gestisci](manage-apps.md#allow-and-block-apps) app, questa app è bloccata o consentita per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae907-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="ae907-140">I proprietari del team possono concedere il consenso a un'app solo se l'app è consentita.</span><span class="sxs-lookup"><span data-stu-id="ae907-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="ae907-141">Per consentire o bloccare un'app a livello di organizzazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae907-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="ae907-142">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.</span><span class="sxs-lookup"><span data-stu-id="ae907-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="ae907-143">Nella pagina Gestisci app selezionare l'app e quindi fare clic su **blocca** per bloccarla o fare clic su **Consenti** per consentirla.</span><span class="sxs-lookup"><span data-stu-id="ae907-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Screenshot delle app bloccate nelle impostazioni a livello di organizzazione](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="ae907-145">Criteri di autorizzazione delle app assegnati al proprietario del team</span><span class="sxs-lookup"><span data-stu-id="ae907-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="ae907-146">I proprietari del team possono concedere solo il consenso alle app che il criterio di autorizzazione dell'app consente loro di eseguire.</span><span class="sxs-lookup"><span data-stu-id="ae907-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="ae907-147">Per visualizzare e gestire i criteri di autorizzazione delle app assegnati a un proprietario del team, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae907-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="ae907-148">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.</span><span class="sxs-lookup"><span data-stu-id="ae907-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="ae907-149">Fare doppio clic sul nome visualizzato del proprietario del team e quindi fare clic su **criteri**.</span><span class="sxs-lookup"><span data-stu-id="ae907-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="ae907-150">I criteri assegnati al proprietario del team sono elencati in **criteri di autorizzazione**per le app.</span><span class="sxs-lookup"><span data-stu-id="ae907-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="ae907-151">Per assegnare un criterio diverso, fare clic su **modifica**e quindi selezionare il criterio che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="ae907-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="ae907-152">Per modificare le impostazioni dei criteri assegnati al proprietario del team, fare clic sul nome del criterio e quindi apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="ae907-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="ae907-153">Caricamento di app personalizzate</span><span class="sxs-lookup"><span data-stu-id="ae907-153">Uploading custom apps</span></span>

<span data-ttu-id="ae907-154">Quando si carica un'app personalizzata (nota anche come sideload) che usa il consenso specifico delle risorse, l'app deve provenire dal tenant in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="ae907-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="ae907-155">In altre parole, la registrazione dell'app Azure AD deve essere di questo tenant.</span><span class="sxs-lookup"><span data-stu-id="ae907-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="ae907-156">Gli amministratori globali sono esentati da questa restrizione e possono caricare app personalizzate da qualsiasi tenant, direttamente in un team (sideload) o nel catalogo dell'app tenant.</span><span class="sxs-lookup"><span data-stu-id="ae907-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae907-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ae907-157">Related topics</span></span>

- [<span data-ttu-id="ae907-158">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ae907-158">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="ae907-159">Gestire le app nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae907-159">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="ae907-160">Gestire i criteri di autorizzazione delle app in Teams</span><span class="sxs-lookup"><span data-stu-id="ae907-160">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
