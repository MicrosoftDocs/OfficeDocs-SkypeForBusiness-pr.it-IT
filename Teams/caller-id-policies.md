---
title: Gestire i criteri di ID chiamante in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di ID chiamante in Microsoft teams per modificare o bloccare l'ID chiamante degli utenti di teams nell'organizzazione.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349780"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="e0f26-103">Gestire i criteri di ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0f26-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="e0f26-104">Come amministratore, puoi usare i criteri di ID chiamante in Microsoft teams per cambiare o bloccare l'ID chiamante (noto anche come ID linea chiamante).</span><span class="sxs-lookup"><span data-stu-id="e0f26-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="e0f26-105">Per impostazione predefinita, il numero di telefono degli utenti di teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono dei chiamanti PSTN può essere visualizzato quando chiamano un utente di teams.</span><span class="sxs-lookup"><span data-stu-id="e0f26-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="e0f26-106">Puoi usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di team dell'organizzazione o bloccare un numero in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e0f26-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="e0f26-107">Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante per visualizzare il numero di telefono principale dell'organizzazione anziché i numeri di telefono degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e0f26-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="e0f26-108">Puoi gestire i criteri ID chiamante accedendo **Voice**ai  >  **criteri ID chiamante** vocale nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e0f26-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e0f26-109">È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e0f26-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="e0f26-110">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e0f26-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="e0f26-111">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e0f26-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="e0f26-112">Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="e0f26-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="e0f26-113">Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="e0f26-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="e0f26-114">Creare un criterio ID chiamante personalizzato</span><span class="sxs-lookup"><span data-stu-id="e0f26-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="e0f26-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.</span><span class="sxs-lookup"><span data-stu-id="e0f26-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e0f26-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-116">Click **Add**.</span></span> <br>
<span data-ttu-id="e0f26-117">![Screenshot della nuova pagina dei criteri ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e0f26-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="e0f26-118">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e0f26-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e0f26-119">Da qui scegliere le impostazioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="e0f26-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="e0f26-120">**Bloccare l'ID chiamante in arrivo**: attivare questa impostazione per bloccare l'ID chiamante delle chiamate in arrivo dalla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0f26-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="e0f26-121">**Eseguire l'override dei criteri ID chiamante**: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni dei criteri relativi alla visualizzazione del loro numero per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="e0f26-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="e0f26-122">Ciò significa che gli utenti possono scegliere se visualizzare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e0f26-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="e0f26-123">Per altre informazioni, vedere [controllo dell'utente finale dell'ID chiamante in uscita](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="e0f26-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="e0f26-124">**Sostituire l'ID chiamante con**: impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0f26-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="e0f26-125">**Numero dell'utente**: Visualizza il numero dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e0f26-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="e0f26-126">**Numero di servizio**: consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e0f26-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="e0f26-127">**Anonymous**: Visualizza l'ID chiamante come anonimo.</span><span class="sxs-lookup"><span data-stu-id="e0f26-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="e0f26-128">**Sostituire l'ID chiamante con questo numero di servizio**: scegliere un numero di servizio per sostituire l'ID chiamante degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e0f26-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="e0f26-129">Questa opzione è disponibile se è **stato selezionato numero di servizio** in **Sostituisci l'ID chiamante con**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="e0f26-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="e0f26-131">Modificare un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="e0f26-131">Edit a caller ID policy</span></span>

<span data-ttu-id="e0f26-132">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="e0f26-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="e0f26-133">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.</span><span class="sxs-lookup"><span data-stu-id="e0f26-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e0f26-134">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e0f26-135">Modificare le impostazioni desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="e0f26-136">Assegnare un criterio ID chiamante personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="e0f26-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="e0f26-137">È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare un criterio personalizzato agli utenti di un gruppo, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0f26-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="e0f26-138">Assegnare un criterio ID linea chiamante personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="e0f26-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="e0f26-139">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="e0f26-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="e0f26-140">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="e0f26-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e0f26-141">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e0f26-142">In **criteri ID chiamante**selezionare il criterio che si vuole assegnare e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="e0f26-143">Per assegnare un criterio a più utenti alla volta:</span><span class="sxs-lookup"><span data-stu-id="e0f26-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="e0f26-144">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi cerca gli utenti o filtra la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="e0f26-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="e0f26-145">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e0f26-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="e0f26-146">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="e0f26-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="e0f26-147">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="e0f26-148">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e0f26-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e0f26-149">Accedere ai **Microsoft Teams admin center**  >  **Voice**  >  **criteri ID chiamante**vocale dell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e0f26-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e0f26-150">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="e0f26-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e0f26-151">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="e0f26-152">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e0f26-153">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e0f26-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e0f26-154">Al termine dell'aggiunta di utenti, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0f26-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="e0f26-155">Assegnare criteri di ID chiamante personalizzati agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="e0f26-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="e0f26-156">È consigliabile assegnare un criterio personalizzato a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="e0f26-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e0f26-157">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e0f26-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e0f26-158">A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e0f26-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="e0f26-159">Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0f26-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="e0f26-160">In questo esempio, assegniamo un criterio lID chiamante personalizzato denominato criteri ID chiamante supporto per tutti gli utenti del gruppo di supporto contoso.</span><span class="sxs-lookup"><span data-stu-id="e0f26-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e0f26-161">Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="e0f26-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e0f26-162">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="e0f26-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="e0f26-163">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="e0f26-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e0f26-164">Assegnare tutti gli utenti del gruppo a un determinato criterio ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e0f26-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="e0f26-165">In questo esempio è supportato il criterio ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="e0f26-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="e0f26-166">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e0f26-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="e0f26-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e0f26-167">Related topics</span></span>

- [<span data-ttu-id="e0f26-168">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="e0f26-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="e0f26-169">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="e0f26-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
