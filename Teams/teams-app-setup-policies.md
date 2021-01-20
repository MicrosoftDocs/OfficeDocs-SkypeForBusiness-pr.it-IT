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
description: Informazioni su come usare e gestire i criteri di configurazione delle app in Microsoft teams per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 32b2accc906b0f4f0dc85b5edf1d9501b64dda14
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909530"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="e81b3-103">Gestire i criteri di configurazione delle app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e81b3-104">Se hai abilitato l'impostazione dell'app a livello di organizzazione, **Consenti l'interazione con** le app personalizzate, potresti non vedere i criteri di configurazione delle app ancora nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e81b3-105">Attualmente viene implementato e sarà presto disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e81b3-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="e81b3-106">Come amministratore, puoi usare i criteri di configurazione delle app per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e81b3-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="e81b3-107">Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e81b3-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="e81b3-108">Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e81b3-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="e81b3-109">Il blocco delle app consente di mostrare le app che gli utenti dell'organizzazione hanno bisogno, incluse le app create da terze parti o dagli sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e81b3-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="e81b3-110">Controllare se gli utenti possono aggiungere app a Teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="e81b3-111">Installare app per conto degli utenti **(in anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="e81b3-112">Scegli le app da installare per impostazione predefinita per gli utenti quando avviano teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="e81b3-113">Tieni presente che gli utenti possono ancora installare le app se i [criteri di autorizzazione dell'app](teams-app-permission-policies.md) assegnati consentiti.</span><span class="sxs-lookup"><span data-stu-id="e81b3-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="e81b3-114">Le app sono aggiunte alla barra dell'app, che è la barra sul lato del client desktop teams e nella parte inferiore dei client per dispositivi mobili di Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="e81b3-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="e81b3-115">Client desktop Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-115">Teams desktop client</span></span>  |<span data-ttu-id="e81b3-116">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-116">Teams mobile client</span></span> |
|---------|---------|
|![Client desktop Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client per dispositivi mobili di Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="e81b3-119">Per visualizzare le app già installate, nella barra dell'app gli utenti selezionano **... Altre app** nei client desktop e Web teams e scorrere rapidamente verso l'alto nei client per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="e81b3-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="e81b3-120">Puoi gestire i criteri di configurazione delle app nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e81b3-121">Usa il criterio globale (predefinito per l'intera organizzazione) oppure crea e assegna criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e81b3-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="e81b3-122">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e81b3-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e81b3-123">Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="e81b3-124">Per includere le app desiderate, è possibile modificare le impostazioni del criterio globale.</span><span class="sxs-lookup"><span data-stu-id="e81b3-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="e81b3-125">Per personalizzare i team per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e81b3-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![pagina Criteri di configurazione dell'app](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="e81b3-127">Se si dispone di team per l'istruzione, è importante sapere che l'app assegnazioni è bloccata per impostazione predefinita nel criterio globale, anche se attualmente non viene visualizzata nell'elenco dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="e81b3-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="e81b3-128">Sarà la quarta app nell'elenco delle app aggiunte nei client di teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="e81b3-129">Creare criteri di configurazione dell'app personalizzati</span><span class="sxs-lookup"><span data-stu-id="e81b3-129">Create a custom app setup policy</span></span>

<span data-ttu-id="e81b3-130">Puoi usare l'interfaccia di amministrazione di Microsoft teams per creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e81b3-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="e81b3-131">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione delle **app teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="e81b3-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e81b3-132">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-132">Select **Add**.</span></span>

   ![pagina Aggiungi criteri di configurazione dell'app](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="e81b3-134">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e81b3-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="e81b3-135">Attivare o disattivare **carica app personalizzate**, a seconda che si voglia consentire agli utenti di caricare app personalizzate in teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="e81b3-136">Non è possibile modificare questa impostazione se l'opzione **Consenti app di terze parti** è disattivata nelle [impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).</span><span class="sxs-lookup"><span data-stu-id="e81b3-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="e81b3-137">Attivare o disattivare Consenti il **blocco dell'utente**, a seconda che si voglia consentire agli utenti di personalizzare la barra dell'app per bloccare le app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e81b3-138">L'impostazione **Consenti il blocco degli utenti** è disponibile nell'interfaccia di amministrazione di teams negli ambienti Microsoft 365 Government community Cloud (GCC) (GCC, GCC High e DOD), ma al momento non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e81b3-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="e81b3-139">Per installare le app per gli utenti **(in anteprima)**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e81b3-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="e81b3-140">In **app installate** selezionare **Aggiungi app**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="e81b3-141">Nel riquadro **Aggiungi app installate** Cerca le app che vuoi installare automaticamente per gli utenti quando avviano teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="e81b3-142">Puoi anche filtrare le app per i criteri di autorizzazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e81b3-143">Dopo aver scelto l'elenco di app, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="e81b3-145">Per aggiungere le app, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e81b3-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="e81b3-146">In **app** aggiunte selezionare **Aggiungi app**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="e81b3-147">Nel riquadro **Aggiungi app** aggiunte cercare le app da aggiungere e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="e81b3-148">Puoi anche filtrare le app per i criteri di autorizzazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e81b3-149">Dopo aver scelto l'elenco di app da aggiungere, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![riquadro delle app aggiunti](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="e81b3-151">Disporre le app nell'ordine in cui si vuole che vengano visualizzate in teams e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![sezione app Pinned](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="e81b3-153">Modificare i criteri di configurazione di un'app</span><span class="sxs-lookup"><span data-stu-id="e81b3-153">Edit an app setup policy</span></span>

<span data-ttu-id="e81b3-154">È possibile usare l'interfaccia di amministrazione di Microsoft teams per modificare un criterio, inclusi i criteri globali (a livello di organizzazione) e i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="e81b3-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="e81b3-155">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione delle **app teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="e81b3-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e81b3-156">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="e81b3-157">Da lì, apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="e81b3-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="e81b3-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="e81b3-159">Assegnare criteri di configurazione dell'app personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="e81b3-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="e81b3-160">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="e81b3-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="e81b3-161">Uso dei criteri di configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="e81b3-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e81b3-162">Quali criteri di configurazione dell'app incorporati sono inclusi nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="e81b3-163">**Globale (impostazione predefinita a livello di organizzazione)**: questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio.</span><span class="sxs-lookup"><span data-stu-id="e81b3-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="e81b3-164">Modificare il criterio globale per aggiungere le app più importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e81b3-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="e81b3-165">**FrontlineWorker**: questo criterio è per i lavoratori Frontline.</span><span class="sxs-lookup"><span data-stu-id="e81b3-165">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="e81b3-166">È possibile assegnarla agli operatori Frontline nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e81b3-166">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="e81b3-167">È importante sapere che, come i criteri personalizzati creati, è necessario assegnare i criteri agli utenti affinché le impostazioni siano attive.</span><span class="sxs-lookup"><span data-stu-id="e81b3-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="e81b3-168">Per altre informazioni, vedere la sezione [assegnazione di un criterio di configurazione dell'app personalizzata per gli utenti](#assign-a-custom-app-setup-policy-to-users) di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e81b3-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="e81b3-169">Perché non è possibile trovare un'app nel riquadro Aggiungi app aggiunte</span><span class="sxs-lookup"><span data-stu-id="e81b3-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="e81b3-170">Non tutte le app possono essere aggiunte ai team tramite criteri di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="e81b3-171">Alcune app potrebbero non supportare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e81b3-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="e81b3-172">Per trovare le app che possono essere bloccate, Cerca l'app nel riquadro **Aggiungi app Pinned** .</span><span class="sxs-lookup"><span data-stu-id="e81b3-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="e81b3-173">Le schede che hanno un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di teams e queste app sono disponibili nel riquadro **Aggiungi app Pinned** .</span><span class="sxs-lookup"><span data-stu-id="e81b3-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="e81b3-174">Tieni presente che nell'app store teams sono elencate tutte le app teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="e81b3-175">Il riquadro **Aggiungi app Pinned** include solo le app che possono essere aggiunte ai team tramite criteri.</span><span class="sxs-lookup"><span data-stu-id="e81b3-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="e81b3-176">Sono un team per l'Education admin. Informazioni utili sui criteri di configurazione delle app in teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="e81b3-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="e81b3-177">L'app chiamante non è disponibile in teams per l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="e81b3-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="e81b3-178">Quando crei un nuovo criterio di configurazione dell'app personalizzata, l'app chiamante viene visualizzata nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="e81b3-179">Tuttavia, l'app non viene aggiunta ai client e ai team di teams per l'istruzione gli utenti non vedranno l'app chiamate in teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="e81b3-180">Numero di app bloccate che possono essere aggiunte a un criterio</span><span class="sxs-lookup"><span data-stu-id="e81b3-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="e81b3-181">Un minimo di due app deve essere aggiunto ai client per dispositivi mobili Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="e81b3-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="e81b3-182">Se un criterio include meno di due app, i client mobili non riflettono le impostazioni dei criteri e continueranno invece a usare la configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="e81b3-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="e81b3-183">Il numero di app pinne che è possibile aggiungere a un criterio non contiene alcun limite.</span><span class="sxs-lookup"><span data-stu-id="e81b3-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="e81b3-184">Quanto tempo occorre per applicare le modifiche ai criteri</span><span class="sxs-lookup"><span data-stu-id="e81b3-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="e81b3-185">Dopo aver modificato o assegnato un criterio, le modifiche apportate potrebbero richiedere qualche ora.</span><span class="sxs-lookup"><span data-stu-id="e81b3-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="e81b3-186">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="e81b3-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="e81b3-187">In che modo gli utenti possono visualizzare tutte le app aggiunte in teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="e81b3-188">Per visualizzare tutte le app bloccate per un utente, è possibile che gli utenti debbano eseguire le operazioni seguenti, a seconda del numero di app installate e delle dimensioni della finestra del client teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="e81b3-189">Client desktop Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-189">Teams desktop client</span></span> |<span data-ttu-id="e81b3-190">Client per dispositivi mobili di Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="e81b3-191">Nella barra dell'app sul lato di teams selezionare **... Altre app**.</span><span class="sxs-lookup"><span data-stu-id="e81b3-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="e81b3-192">Nella barra dell'app nella parte inferiore del team scorrere rapidamente verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="e81b3-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Altre app nel client desktop Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Altre app nel client per dispositivi mobili Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="e81b3-195">Informazioni utili sull'esperienza di teams mobile</span><span class="sxs-lookup"><span data-stu-id="e81b3-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="e81b3-196">I client mobili di Teams (iOS e Android) attualmente non supportano le app personali con schede statiche.</span><span class="sxs-lookup"><span data-stu-id="e81b3-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="e81b3-197">A seconda delle app impostate nel criterio, le app aggiunte al client desktop teams potrebbero non essere visualizzate nei client per dispositivi mobili teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="e81b3-198">I bot personali verranno comunque visualizzati in chat su client mobili.</span><span class="sxs-lookup"><span data-stu-id="e81b3-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="e81b3-199">Con i client di teams per dispositivi mobili, gli utenti vedranno le app di core team, come attività, chat e team, ed è possibile aggiungere alcune app di primo tipo da Microsoft, ad esempio turni.</span><span class="sxs-lookup"><span data-stu-id="e81b3-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="e81b3-200">Gli utenti possono modificare l'ordine delle app bloccati da un criterio</span><span class="sxs-lookup"><span data-stu-id="e81b3-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="e81b3-201">Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e mobili di teams se l'opzione **Consenti il blocco utente** è attivata.</span><span class="sxs-lookup"><span data-stu-id="e81b3-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="e81b3-202">Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="e81b3-203">Il blocco degli utenti ha la precedenza</span><span class="sxs-lookup"><span data-stu-id="e81b3-203">Does user pinning take precedence</span></span>

<span data-ttu-id="e81b3-204">Se i criteri di configurazione dell'app assegnati all'utente vengono modificati per bloccare il blocco delle app degli utenti, i team rimuovono tutte le app aggiunte alla barra dell'app.</span><span class="sxs-lookup"><span data-stu-id="e81b3-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="e81b3-205">Se il criterio viene quindi modificato in modo da consentire il blocco delle app degli utenti, gli utenti devono ripetere l'aggiunta delle app precedentemente bloccate.</span><span class="sxs-lookup"><span data-stu-id="e81b3-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="e81b3-206">App Team personalizzate</span><span class="sxs-lookup"><span data-stu-id="e81b3-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="e81b3-207">La mia organizzazione ha creato un'app teams personalizzata e pubblicata, in AppSource o nel catalogo dell'app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene bloccata alla barra dell'app in teams.</span><span class="sxs-lookup"><span data-stu-id="e81b3-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="e81b3-208">Come risolvere il problema</span><span class="sxs-lookup"><span data-stu-id="e81b3-208">How do I fix it</span></span>

<span data-ttu-id="e81b3-209">Prima di inviare l'app, assicurati di seguire le linee guida per il logo.</span><span class="sxs-lookup"><span data-stu-id="e81b3-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="e81b3-210">Per altre informazioni, vedere [elenco di controllo per l'invio del dashboard del venditore](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span><span class="sxs-lookup"><span data-stu-id="e81b3-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e81b3-211">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e81b3-211">Related topics</span></span>

[<span data-ttu-id="e81b3-212">Impostazioni di amministrazione per le app in Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="e81b3-213">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="e81b3-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
