---
title: Gestire i criteri di configurazione delle app in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di configurazione delle app in Microsoft Teams per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145923"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="c3d36-103">Gestire i criteri di configurazione delle app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="c3d36-104">Gli amministratori possono usare i criteri di configurazione delle app per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3d36-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="c3d36-105">Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c3d36-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="c3d36-106">Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="c3d36-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="c3d36-107">L'aggiunta di app consente di presentare le app necessarie agli utenti dell'organizzazione, incluse quelle create da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3d36-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="c3d36-108">Controllare se gli utenti possono aggiungere app a Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="c3d36-109">Installare le app per conto degli **utenti (in anteprima).**</span><span class="sxs-lookup"><span data-stu-id="c3d36-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="c3d36-110">È possibile scegliere quali app vengono installate per impostazione predefinita per gli utenti quando avviano Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="c3d36-111">Tenere presente che gli utenti possono comunque installare le app se i criteri di autorizzazione per le [app](teams-app-permission-policies.md) loro assegnati lo consentono.</span><span class="sxs-lookup"><span data-stu-id="c3d36-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="c3d36-112">Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="c3d36-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="c3d36-113">Client desktop di Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-113">Teams desktop client</span></span>  |<span data-ttu-id="c3d36-114">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-114">Teams mobile client</span></span> |
|---------|---------|
|![Client desktop di Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client teams per dispositivi mobili](media/mobile-app-ui.png)      |

<span data-ttu-id="c3d36-117">Per visualizzare le app preinstallte, nella barra dell'app gli utenti **selezionano... Altre app** nei client desktop e web di Teams e scorrere rapidamente verso l'alto nei client mobili.</span><span class="sxs-lookup"><span data-stu-id="c3d36-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="c3d36-118">È possibile gestire i criteri di configurazione delle app nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c3d36-119">Usare i criteri globali (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c3d36-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="c3d36-120">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c3d36-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c3d36-121">Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="c3d36-122">È possibile modificare le impostazioni nel criterio globale per includere le app desiderate.</span><span class="sxs-lookup"><span data-stu-id="c3d36-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="c3d36-123">Per personalizzare Teams per diversi gruppi di utenti nell'organizzazione, creare e assegnare uno o più criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c3d36-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Pagina Criteri di configurazione delle app](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="c3d36-125">Se si dispone di Teams per l'istruzione, è importante sapere che l'app Attività è aggiunta per impostazione predefinita ai criteri globali anche se attualmente non è elencata nei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="c3d36-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="c3d36-126">Sarà la quarta app nell'elenco delle app aggiunte nei client di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="c3d36-127">Creare criteri di configurazione delle app personalizzati</span><span class="sxs-lookup"><span data-stu-id="c3d36-127">Create a custom app setup policy</span></span>

<span data-ttu-id="c3d36-128">È possibile usare l'interfaccia di amministrazione di Microsoft Teams per creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c3d36-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="c3d36-129">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **delle app di**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c3d36-130">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c3d36-130">Select **Add**.</span></span>

   ![Pagina Aggiungi criteri di configurazione delle app](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="c3d36-132">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="c3d36-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="c3d36-133">Attivare o disattivare **Carica app** personalizzate, a seconda che si voglia o meno consentire agli utenti di caricare app personalizzate in Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="c3d36-134">Non puoi modificare questa  impostazione se Consenti app di terze parti è disattivato nelle impostazioni dell'app [a livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="c3d36-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="c3d36-135">Attivare o disattivare **Consenti** l'aggiunta di app agli utenti, a seconda che si voglia consentire o meno agli utenti di personalizzare la barra dell'app aggiungendo app alla barra.</span><span class="sxs-lookup"><span data-stu-id="c3d36-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3d36-136">L'impostazione Consenti l'aggiunta di utenti è disponibile nell'interfaccia di amministrazione di Teams negli ambienti Microsoft 365 Government Community Cloud (GCC), ma attualmente non ha alcun effetto. </span><span class="sxs-lookup"><span data-stu-id="c3d36-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="c3d36-137">Per installare le app per gli **utenti (in anteprima),** eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3d36-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="c3d36-138">In **App installate** selezionare Aggiungi **app.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="c3d36-139">Nel riquadro **Aggiungi app installate,** cerca le app che vuoi installare automaticamente per gli utenti quando avviano Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="c3d36-140">È anche possibile filtrare le app in base ai criteri di autorizzazione per le app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c3d36-141">Dopo aver scelto l'elenco di app, seleziona **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![Riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="c3d36-143">Per aggiungere app, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3d36-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="c3d36-144">In **App aggiunte** selezionare Aggiungi **app.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="c3d36-145">Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="c3d36-146">È anche possibile filtrare le app in base ai criteri di autorizzazione per le app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c3d36-147">Dopo aver scelto l'elenco di app da aggiungere, seleziona **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![Riquadro Aggiungi app aggiunte](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="c3d36-149">Disponi le app nell'ordine in cui vuoi che vengano visualizzate in Teams, quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Sezione App aggiunte](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="c3d36-151">Modificare i criteri di configurazione di un'app</span><span class="sxs-lookup"><span data-stu-id="c3d36-151">Edit an app setup policy</span></span>

<span data-ttu-id="c3d36-152">È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (impostazione predefinita a livello di organizzazione) e i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d36-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="c3d36-153">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **delle app di**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c3d36-154">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c3d36-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="c3d36-155">Da lì, apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="c3d36-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="c3d36-156">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c3d36-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="c3d36-157">Assegnare criteri di configurazione delle app personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="c3d36-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="c3d36-158">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c3d36-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="c3d36-159">Uso dei criteri di configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="c3d36-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c3d36-160">Quali criteri di configurazione delle app incorporati sono inclusi nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="c3d36-161">**Globale (impostazione predefinita a livello** di organizzazione): questo criterio predefinito viene applicato a tutti gli utenti dell'organizzazione, a meno che non venga assegnato un altro criterio.</span><span class="sxs-lookup"><span data-stu-id="c3d36-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="c3d36-162">Modificare i criteri globali per aggiungere le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c3d36-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="c3d36-163">**FrontlineWorker:** questo criterio è per gli operatori sul campo.</span><span class="sxs-lookup"><span data-stu-id="c3d36-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="c3d36-164">È possibile assegnarla agli operatori sul campo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3d36-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="c3d36-165">È importante sapere che, ad esempio, i criteri personalizzati creati dall'utente devono essere assegnati agli utenti perché le impostazioni siano attive.</span><span class="sxs-lookup"><span data-stu-id="c3d36-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="c3d36-166">Per altre informazioni, vedere la sezione [Assegnare criteri](#assign-a-custom-app-setup-policy-to-users) di configurazione di app personalizzati agli utenti di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c3d36-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="c3d36-167">Perché non riesco a trovare un'app nel riquadro Aggiungi app aggiunte</span><span class="sxs-lookup"><span data-stu-id="c3d36-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="c3d36-168">Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="c3d36-169">Alcune app potrebbero non supportare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c3d36-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="c3d36-170">Per trovare le app che possono essere aggiunte, cerca l'app nel **riquadro Aggiungi app aggiunte.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="c3d36-171">Le schede con un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="c3d36-172">Tenere presente che nell'app store di Teams sono elencate tutte le app di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="c3d36-173">Il **riquadro Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.</span><span class="sxs-lookup"><span data-stu-id="c3d36-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="c3d36-174">Sono un amministratore di Teams per l'istruzione. Cosa devo sapere sui criteri di configurazione delle app in Teams for Education</span><span class="sxs-lookup"><span data-stu-id="c3d36-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="c3d36-175">L'app Chiamate non è disponibile in Teams per l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c3d36-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="c3d36-176">Quando crei un nuovo criterio di configurazione delle app personalizzato, l'app per le chiamate viene visualizzata nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="c3d36-177">Tuttavia, l'app non viene aggiunta ai client di Teams e gli utenti di Teams for Education non vedono l'app Chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="c3d36-178">Quante app aggiunte possono essere aggiunte a un criterio</span><span class="sxs-lookup"><span data-stu-id="c3d36-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="c3d36-179">È necessario aggiungere almeno due app ai client mobili di Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="c3d36-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="c3d36-180">Se un criterio include meno di due app, i client per dispositivi mobili non rifletteranno le impostazioni dei criteri, ma continueranno a usare la configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="c3d36-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="c3d36-181">Non ci sono limiti al numero di app aggiunte che è possibile aggiungere a un criterio.</span><span class="sxs-lookup"><span data-stu-id="c3d36-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="c3d36-182">Quanto tempo è necessario per l'applicazione delle modifiche ai criteri</span><span class="sxs-lookup"><span data-stu-id="c3d36-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="c3d36-183">La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="c3d36-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="c3d36-184">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="c3d36-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="c3d36-185">In che modo gli utenti possono vedere tutte le app aggiunte in Teams?</span><span class="sxs-lookup"><span data-stu-id="c3d36-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="c3d36-186">Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le operazioni seguenti a seconda del numero di app installate e delle dimensioni della finestra client di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="c3d36-187">Client desktop di Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-187">Teams desktop client</span></span> |<span data-ttu-id="c3d36-188">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="c3d36-189">Nella barra dell'app sul lato di Teams, **seleziona... Altre app.**</span><span class="sxs-lookup"><span data-stu-id="c3d36-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="c3d36-190">Nella barra dell'app, nella parte inferiore di Teams, scorri rapidamente verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="c3d36-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Altre app nel client desktop di Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![altre app nel client teams per dispositivi mobili](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="c3d36-193">Cosa devo sapere sull'esperienza di Teams per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3d36-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="c3d36-194">I client mobili di Teams (iOS e Android) attualmente non supportano le app personali con schede statiche.</span><span class="sxs-lookup"><span data-stu-id="c3d36-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="c3d36-195">A seconda delle app impostate nel criterio, le app aggiunte al client desktop di Teams potrebbero non essere visualizzate nei client mobili di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="c3d36-196">I bot personali verranno comunque visualizzati in Chat sui client mobili.</span><span class="sxs-lookup"><span data-stu-id="c3d36-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="c3d36-197">Con i client di Teams per dispositivi mobili, gli utenti vedono le app principali di Teams, come Attività, Chat e Teams, e puoi aggiungere alcune app di prima parte di Microsoft, come Turni.</span><span class="sxs-lookup"><span data-stu-id="c3d36-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="c3d36-198">Gli utenti possono modificare l'ordine delle app aggiunte tramite un criterio</span><span class="sxs-lookup"><span data-stu-id="c3d36-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="c3d36-199">Se l'opzione Consenti l'aggiunta di utenti è  attivata, gli utenti possono cambiare l'ordine delle app aggiunte nei client desktop e per dispositivi mobili di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="c3d36-200">Gli utenti non possono cambiare l'ordine delle app aggiunte nei client Web di Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="c3d36-201">L'aggiunta utente ha la precedenza</span><span class="sxs-lookup"><span data-stu-id="c3d36-201">Does user pinning take precedence</span></span>

<span data-ttu-id="c3d36-202">Se il criterio di configurazione delle app assegnato all'utente viene modificato in modo da bloccare il blocco dell'app utente, Teams rimuove tutte le app aggiunte alla barra dell'app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="c3d36-203">Se il criterio viene modificato per consentire l'aggiunta di app utente, gli utenti devono aggiungere di nuovo le app aggiunte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c3d36-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="c3d36-204">App di Teams personalizzate</span><span class="sxs-lookup"><span data-stu-id="c3d36-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="c3d36-205">La mia organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams.</span><span class="sxs-lookup"><span data-stu-id="c3d36-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="c3d36-206">Come si corregge?</span><span class="sxs-lookup"><span data-stu-id="c3d36-206">How do I fix it</span></span>

<span data-ttu-id="c3d36-207">Assicurarsi di seguire le linee guida per il logo prima di inviare l'app.</span><span class="sxs-lookup"><span data-stu-id="c3d36-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="c3d36-208">Per altre informazioni, vedi l'elenco [di controllo per l'invio al dashboard del venditore.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="c3d36-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3d36-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c3d36-209">Related topics</span></span>

[<span data-ttu-id="c3d36-210">Impostazioni di amministrazione per le app in Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="c3d36-211">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="c3d36-211">Assign policies to your users in Teams</span></span>](assign-policies.md)
