---
title: Gestire i criteri dei team in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: Informazioni su come usare e gestire i criteri per i team dell'organizzazione per controllare gli utenti che possono eseguire in team e canali.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 5bcc084c96ededbf4337057834763e9d53ac4348
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968277"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="b0f92-103">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0f92-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="b0f92-104">Come amministratore, puoi usare i criteri di teams in Microsoft teams per controllare gli utenti che possono eseguire in team e canali.</span><span class="sxs-lookup"><span data-stu-id="b0f92-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="b0f92-105">Ad esempio, puoi impostare se gli utenti possono scoprire team privati nei risultati della ricerca e nella raccolta team e se gli utenti possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="b0f92-106">Per gestire i criteri dei team, è possibile **passare a** > **criteri** teams teams nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b0f92-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b0f92-107">Puoi usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b0f92-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="b0f92-108">Gli utenti dell'organizzazione otterranno automaticamente il criterio globale a meno che non si creino e non si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="b0f92-109">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="b0f92-110">Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="b0f92-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="b0f92-111">Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="b0f92-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="b0f92-112">Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="b0f92-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="b0f92-113">Creare un criterio teams personalizzato</span><span class="sxs-lookup"><span data-stu-id="b0f92-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="b0f92-114">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.</span><span class="sxs-lookup"><span data-stu-id="b0f92-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b0f92-115">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-115">Click **Add**.</span></span>
3. <span data-ttu-id="b0f92-116">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b0f92-116">Enter a name and description for the policy.</span></span>

    ![Screenshot delle impostazioni dei criteri di Teams](media/teams-policies.png)
4. <span data-ttu-id="b0f92-118">Scegliere le impostazioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="b0f92-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="b0f92-119">**Scoprire team privati**:<a name="discoverteams"> </a> attivare questa impostazione per consentire agli utenti di individuare team privati nei risultati della ricerca e nella raccolta team.</span><span class="sxs-lookup"><span data-stu-id="b0f92-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="b0f92-120">**Creare canali privati**: <a name="createchannels"> </a>attivare questa impostazione per consentire agli utenti di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="b0f92-121">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="b0f92-122">Modificare un criterio Teams</span><span class="sxs-lookup"><span data-stu-id="b0f92-122">Edit a teams policy</span></span>

<span data-ttu-id="b0f92-123">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="b0f92-124">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.</span><span class="sxs-lookup"><span data-stu-id="b0f92-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b0f92-125">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b0f92-126">Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="b0f92-127">Assegnare un criterio team personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="b0f92-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="b0f92-128">È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0f92-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="b0f92-129">Assegnare un criterio teams personalizzato a un utente</span><span class="sxs-lookup"><span data-stu-id="b0f92-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="b0f92-130">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="b0f92-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="b0f92-131">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b0f92-132">In **criteri Team**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="b0f92-133">Per assegnare un criterio teams personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="b0f92-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="b0f92-134">In alternativa, è anche possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0f92-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b0f92-135">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a** > **criteri**teams teams.</span><span class="sxs-lookup"><span data-stu-id="b0f92-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b0f92-136">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="b0f92-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b0f92-137">Selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="b0f92-138">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b0f92-139">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b0f92-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b0f92-140">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b0f92-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="b0f92-141">Assegnare criteri Team personalizzati agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="b0f92-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="b0f92-142">È consigliabile assegnare un criterio teams personalizzato a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="b0f92-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="b0f92-143">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b0f92-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="b0f92-144">A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="b0f92-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="b0f92-145">Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b0f92-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b0f92-146">In questo esempio viene assegnato un criterio teams denominato criteri marketing teams a tutti gli utenti nel gruppo marketing di contoso.</span><span class="sxs-lookup"><span data-stu-id="b0f92-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="b0f92-147">Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="b0f92-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="b0f92-148">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="b0f92-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="b0f92-149">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="b0f92-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b0f92-150">Assegnare tutti gli utenti del gruppo a un determinato criterio teams.</span><span class="sxs-lookup"><span data-stu-id="b0f92-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="b0f92-151">In questo esempio si tratta di criteri per i team di marketing.</span><span class="sxs-lookup"><span data-stu-id="b0f92-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="b0f92-152">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b0f92-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0f92-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b0f92-153">Related topics</span></span>

- [<span data-ttu-id="b0f92-154">Gestire l'individuazione di team privati in Teams</span><span class="sxs-lookup"><span data-stu-id="b0f92-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="b0f92-155">Canali privati in teams</span><span class="sxs-lookup"><span data-stu-id="b0f92-155">Private channels in Teams</span></span>](private-channels.md)
