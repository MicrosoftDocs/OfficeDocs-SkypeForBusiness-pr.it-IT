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
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697711"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="1cd5d-103">Gestire i criteri di configurazione delle app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="1cd5d-104">Gli amministratori possono usare i criteri di configurazione delle app per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cd5d-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="1cd5d-105">Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="1cd5d-106">Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="1cd5d-107">L'aggiunta di app consente di mostrare le app necessarie agli utenti dell'organizzazione, incluse le app create da terze parti o dagli sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="1cd5d-108">Controllare se gli utenti possono aggiungere app a Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="1cd5d-109">Installare le app per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-109">Install apps on behalf of users.</span></span> <span data-ttu-id="1cd5d-110">È possibile scegliere le app installate per impostazione predefinita per gli utenti all'avvio di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="1cd5d-111">Tenere presente che gli utenti possono comunque installare le app se i criteri di autorizzazione [dell'app](teams-app-permission-policies.md) assegnati lo consentono.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="1cd5d-112">Per le app installate dagli amministratori, gli utenti non possono disinstallare tali app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="1cd5d-113">Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="1cd5d-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="1cd5d-114">Client desktop di Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-114">Teams desktop client</span></span>  |<span data-ttu-id="1cd5d-115">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-115">Teams mobile client</span></span> |
|---------|---------|
|![Client desktop di Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client per dispositivi mobili di Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="1cd5d-118">Per visualizzare le app installate dagli amministratori, nella barra dell'app gli utenti **selezionano ... Altre app** nei client desktop e Web di Teams e scorri verso l'alto nei client mobili.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="1cd5d-119">I criteri di configurazione delle app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1cd5d-120">Usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="1cd5d-121">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1cd5d-122">Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="1cd5d-123">Modificare le impostazioni nei criteri globali per includere le app desiderate.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="1cd5d-124">Per personalizzare Teams per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![pagina Criteri di configurazione delle app](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="1cd5d-126">Se si dispone di Teams per l'istruzione, è importante sapere che l'app Attività è aggiunta per impostazione predefinita nei criteri globali anche se attualmente non è elencata nei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="1cd5d-127">Sarà la quarta app nell'elenco delle app aggiunte nei client di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="1cd5d-128">Creare criteri di configurazione dell'app personalizzati</span><span class="sxs-lookup"><span data-stu-id="1cd5d-128">Create a custom app setup policy</span></span>

<span data-ttu-id="1cd5d-129">È possibile usare l'interfaccia di amministrazione di Microsoft Teams per creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="1cd5d-130">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Criteri di **configurazione delle app** di  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1cd5d-131">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-131">Select **Add**.</span></span>

   ![Pagina Aggiungi criteri di configurazione delle app](media/app-setup-policies-add.png)

3. <span data-ttu-id="1cd5d-133">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="1cd5d-134">Attivare o disattivare **Carica app personalizzate,** a seconda che si voglia consentire agli utenti di caricare app personalizzate in Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="1cd5d-135">Non è possibile modificare questa impostazione se Consenti **app** di terze parti è disattivato nelle impostazioni dell'app a [livello di organizzazione.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="1cd5d-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="1cd5d-136">Attivare o disattivare **Consenti** l'aggiunta all'utente, a seconda che si voglia consentire agli utenti di personalizzare la barra dell'app aggiungendo app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cd5d-137">L'impostazione Consenti blocco utenti è disponibile nell'interfaccia di amministrazione di Teams negli ambienti GCC (Government Community Cloud) di Microsoft 365 (GCC, GCC High e DoD), ma attualmente non ha alcun effetto. </span><span class="sxs-lookup"><span data-stu-id="1cd5d-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="1cd5d-138">Per installare le app per gli utenti, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cd5d-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="1cd5d-139">In **App installate** selezionare Aggiungi **app.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1cd5d-140">Nel riquadro **Aggiungi app installate** cercare le app da installare automaticamente per gli utenti all'avvio di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="1cd5d-141">È anche possibile filtrare le app in base ai criteri di autorizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1cd5d-142">Dopo aver scelto l'elenco di app, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![Riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="1cd5d-144">Per aggiungere app, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1cd5d-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="1cd5d-145">In **App aggiunte** selezionare Aggiungi **app.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1cd5d-146">Nel riquadro **Aggiungi app aggiunte** cercare le app da aggiungere e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="1cd5d-147">È anche possibile filtrare le app in base ai criteri di autorizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1cd5d-148">Dopo aver scelto l'elenco di app da aggiungere, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![Riquadro Aggiungi app aggiunte](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="1cd5d-150">Disporre le app nell'ordine in cui si vuole che vengano visualizzate in Teams e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![sezione App aggiunte](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="1cd5d-152">Modificare i criteri di configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="1cd5d-152">Edit an app setup policy</span></span>

<span data-ttu-id="1cd5d-153">È possibile usare l'interfaccia di amministrazione di Microsoft Teams per modificare un criterio, inclusi i criteri globali (impostazione predefinita a livello di organizzazione) e i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="1cd5d-154">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Criteri di **configurazione delle app** di  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1cd5d-155">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="1cd5d-156">Da lì, apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="1cd5d-157">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="1cd5d-158">Assegnare criteri di configurazione dell'app personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="1cd5d-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="1cd5d-159">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="1cd5d-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="1cd5d-160">Uso dei criteri di configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="1cd5d-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1cd5d-161">Quali criteri di configurazione delle app predefiniti sono inclusi nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="1cd5d-162">**Globale (impostazione predefinita a livello di organizzazione):** questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="1cd5d-163">Modificare i criteri globali per aggiungere app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="1cd5d-164">**FrontlineWorker:** questo criterio è per i frontline worker.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="1cd5d-165">È possibile assegnarlo ai Frontline Worker dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="1cd5d-166">È importante sapere che, come i criteri personalizzati creati dall'utente, è necessario assegnare il criterio agli utenti perché le impostazioni siano attive.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="1cd5d-167">Per altre informazioni, vedere la sezione Assegnare un criterio di configurazione [dell'app](#assign-a-custom-app-setup-policy-to-users) personalizzato agli utenti di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="1cd5d-168">Perché non si trova un'app nel riquadro Aggiungi app aggiunte</span><span class="sxs-lookup"><span data-stu-id="1cd5d-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="1cd5d-169">Non tutte le app possono essere aggiunte a Teams tramite un criterio di configurazione delle app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="1cd5d-170">Alcune app potrebbero non supportare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="1cd5d-171">Per trovare le app che possono essere aggiunte, cercare l'app nel **riquadro Aggiungi app aggiunte.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="1cd5d-172">Le schede con ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di Teams e queste app sono disponibili nel riquadro **Aggiungi app aggiunte.**</span><span class="sxs-lookup"><span data-stu-id="1cd5d-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="1cd5d-173">Tenere presente che l'app Store di Teams elenca tutte le app di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="1cd5d-174">Il **riquadro Aggiungi app aggiunte** include solo le app che possono essere aggiunte a Teams tramite un criterio.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="1cd5d-175">Sono un amministratore di Teams for Education. Informazioni sui criteri di configurazione delle app in Teams for Education</span><span class="sxs-lookup"><span data-stu-id="1cd5d-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="1cd5d-176">L'app Chiamate non è disponibile in Teams per l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="1cd5d-177">Quando si crea un nuovo criterio di configurazione dell'app personalizzato, l'app Chiamate viene visualizzata nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="1cd5d-178">Tuttavia, l'app non è aggiunta ai client di Teams e gli utenti di Teams per l'istruzione non vedono l'app Chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="1cd5d-179">Quante app aggiunte possono essere aggiunte a un criterio</span><span class="sxs-lookup"><span data-stu-id="1cd5d-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="1cd5d-180">È necessario aggiungere almeno due app ai client mobili di Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="1cd5d-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="1cd5d-181">Se un criterio ha meno di due app, i client mobili non rifletteranno le impostazioni dei criteri e continueranno invece a usare la configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="1cd5d-182">Non ci sono limiti al numero di app aggiunte che è possibile aggiungere a un criterio.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="1cd5d-183">Quanto tempo è necessario per l'applicazione delle modifiche ai criteri</span><span class="sxs-lookup"><span data-stu-id="1cd5d-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="1cd5d-184">La modifica o l'assegnazione di un criterio potrà richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="1cd5d-185">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="1cd5d-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="1cd5d-186">Come possono gli utenti vedere tutte le app aggiunte in Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="1cd5d-187">Per visualizzare tutte le app aggiunte per un utente, gli utenti potrebbero dover eseguire le operazioni seguenti a seconda del numero di app installate e delle dimensioni della finestra del client di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="1cd5d-188">Client desktop di Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-188">Teams desktop client</span></span> |<span data-ttu-id="1cd5d-189">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="1cd5d-190">Nella barra dell'app sul lato di Teams seleziona **... Altre app**.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="1cd5d-191">Nella barra dell'app nella parte inferiore di Teams scorrere rapidamente verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Altre app nel client desktop di Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Altre app nel client di Teams per dispositivi mobili](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="1cd5d-194">Cosa c'è da sapere sull'esperienza di Teams per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="1cd5d-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="1cd5d-195">I client mobili di Teams (iOS e Android) attualmente non supportano le app personali con schede statiche.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="1cd5d-196">A seconda delle app impostate nel criterio, le app aggiunte al client desktop di Teams potrebbero non essere visualizzate nei client mobili di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="1cd5d-197">I bot personali verranno comunque visualizzati in Chat sui client mobili.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="1cd5d-198">Con i client di Teams per dispositivi mobili, gli utenti potranno vedere le app principali di Teams, come Attività, Chat e Teams, ed è possibile aggiungere alcune app di prima parte da Microsoft, ad esempio Turni.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="1cd5d-199">Gli utenti possono modificare l'ordine delle app aggiunte tramite un criterio</span><span class="sxs-lookup"><span data-stu-id="1cd5d-199">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="1cd5d-200">Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e mobili di Teams se l'opzione Consenti **blocco** utenti è attivata.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="1cd5d-201">Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="1cd5d-202">Il blocco degli utenti ha la precedenza</span><span class="sxs-lookup"><span data-stu-id="1cd5d-202">Does user pinning take precedence</span></span>

<span data-ttu-id="1cd5d-203">I pin di amministratore hanno sempre la precedenza.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-203">Admin pins always take precedence.</span></span> <span data-ttu-id="1cd5d-204">Se **l'opzione Consenti aggiunta utenti** è attivata, gli utenti manterranno le app aggiunte sotto le app aggiunte dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-204">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="1cd5d-205">Se **l'opzione** Consenti blocco utenti è disattivata, gli utenti perderanno i pin preesistnti e nella barra dell'app saranno presenti solo le app aggiunte dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-205">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="1cd5d-206">App di Teams personalizzate</span><span class="sxs-lookup"><span data-stu-id="1cd5d-206">Custom Teams apps</span></span>

<span data-ttu-id="1cd5d-207">L'organizzazione ha creato un'app Teams personalizzata e l'ha pubblicata, in AppSource o nel catalogo app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene aggiunta alla barra dell'app in Teams.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="1cd5d-208">Come si risolve il problema</span><span class="sxs-lookup"><span data-stu-id="1cd5d-208">How do I fix it</span></span>

<span data-ttu-id="1cd5d-209">Assicurarsi di seguire le linee guida del logo prima di inviare l'app.</span><span class="sxs-lookup"><span data-stu-id="1cd5d-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="1cd5d-210">Per altre informazioni, vedere Elenco [di controllo per l'invio del dashboard del venditore.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="1cd5d-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cd5d-211">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1cd5d-211">Related topics</span></span>

[<span data-ttu-id="1cd5d-212">Impostazioni di amministrazione per le app in Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="1cd5d-213">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="1cd5d-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
