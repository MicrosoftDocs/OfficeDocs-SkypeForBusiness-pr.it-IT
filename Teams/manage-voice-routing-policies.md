---
title: Gestire i criteri di routing vocale in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come creare e gestire i criteri di routing vocale in Microsoft teams.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350190"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="519d9-103">Gestire i criteri di routing vocale in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="519d9-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="519d9-104">Se si è distribuito il [routing diretto del sistema telefonico](direct-routing-landing-page.md) nell'organizzazione, è possibile usare i criteri di routing vocale per consentire agli utenti di Skype for business online di ricevere e effettuare chiamate telefoniche alla rete PSTN (Public Switched Telephone Network) usando l'infrastruttura di telefonia locale.</span><span class="sxs-lookup"><span data-stu-id="519d9-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="519d9-105">Un criterio di routing vocale è un contenitore per i record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="519d9-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="519d9-106">Per creare e gestire i criteri di routing vocale, è possibile **passare a**criteri di routing Voice Voice nell'interfaccia di amministrazione di  >  **Voice routing policies** Microsoft teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="519d9-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="519d9-107">Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="519d9-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="519d9-108">Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="519d9-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="519d9-109">Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.</span><span class="sxs-lookup"><span data-stu-id="519d9-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="519d9-110">È importante sapere che l'assegnazione di criteri di routing vocale a un utente non consente loro di effettuare chiamate PSTN in teams.</span><span class="sxs-lookup"><span data-stu-id="519d9-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="519d9-111">Dovrai anche abilitare l'instradamento diretto dell'utente per il sistema telefonico e completare altri passaggi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="519d9-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="519d9-112">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="519d9-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="519d9-113">Creare un criterio di routing vocale personalizzato</span><span class="sxs-lookup"><span data-stu-id="519d9-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="519d9-114">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="519d9-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="519d9-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing**vocale e quindi fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="519d9-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="519d9-116">![Screenshot della pagina Aggiungi criteri di routing vocale nell'interfaccia di amministrazione di Microsoft Teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="519d9-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="519d9-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="519d9-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="519d9-118">In **record utilizzo PSTN**fare clic su **Aggiungi utilizzo PSTN**e quindi selezionare i record che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="519d9-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="519d9-119">Se è necessario creare un nuovo record di utilizzo PSTN, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="519d9-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="519d9-120">Se sono stati aggiunti più record di utilizzo PSTN, disponili nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="519d9-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="519d9-121">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="519d9-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="519d9-122">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="519d9-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="519d9-123">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="519d9-123">Using PowerShell</span></span>

<span data-ttu-id="519d9-124">Vedere [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="519d9-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="519d9-125">Modificare un criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="519d9-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="519d9-126">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="519d9-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="519d9-127">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="519d9-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="519d9-128">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **accedere ai**  >  **criteri di routing**vocale.</span><span class="sxs-lookup"><span data-stu-id="519d9-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="519d9-129">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="519d9-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="519d9-130">Fare clic su **Aggiungi/Rimuovi record di utilizzo PSTN**, apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="519d9-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="519d9-131">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="519d9-131">Using PowerShell</span></span>

<span data-ttu-id="519d9-132">Vedere [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="519d9-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="519d9-133">Assegnare criteri di routing vocale personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="519d9-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="519d9-134">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="519d9-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="519d9-135">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="519d9-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="519d9-136">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="519d9-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="519d9-137">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="519d9-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="519d9-138">In **criteri di routing vocale**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="519d9-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="519d9-139">Per assegnare un criterio a più utenti alla volta:</span><span class="sxs-lookup"><span data-stu-id="519d9-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="519d9-140">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi cerca gli utenti o filtra la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="519d9-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="519d9-141">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="519d9-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="519d9-142">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="519d9-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="519d9-143">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="519d9-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="519d9-144">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="519d9-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="519d9-145">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **accedere ai**  >  **criteri di routing**vocale.</span><span class="sxs-lookup"><span data-stu-id="519d9-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="519d9-146">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="519d9-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="519d9-147">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="519d9-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="519d9-148">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="519d9-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="519d9-149">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="519d9-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="519d9-150">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="519d9-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="519d9-151">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="519d9-151">Using PowerShell</span></span>

<span data-ttu-id="519d9-152">Vedere [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="519d9-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="519d9-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="519d9-153">Related topics</span></span>

- [<span data-ttu-id="519d9-154">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="519d9-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="519d9-155">Configurare il routing vocale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="519d9-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="519d9-156">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="519d9-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="519d9-157">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="519d9-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
