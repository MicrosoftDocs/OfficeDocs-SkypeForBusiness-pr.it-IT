---
title: Gestire i criteri delle chiamate di emergenza in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri delle chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e697e05c4ade1e14ee2f59da5b60413e60e2367
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905108"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="3d113-103">Gestire i criteri delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d113-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="3d113-104">Se l'organizzazione usa i piani di chiamata o il routing diretto del sistema telefonico distribuito, è possibile usare i criteri per le chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="3d113-105">Puoi impostare gli utenti a cui inviare una notifica e il modo in cui vengono informati quando un utente a cui viene assegnato il criterio chiama i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="3d113-106">Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente alla scrivania di sicurezza dell'organizzazione e farli ascoltare in chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="3d113-107">Puoi gestire i criteri delle chiamate di emergenza passando ai**criteri di emergenza** **vocale** > nell'interfaccia di amministrazione di Microsoft teams oppure usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d113-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="3d113-108">I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3d113-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="3d113-109">Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3d113-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3d113-110">Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3d113-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3d113-111">Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.</span><span class="sxs-lookup"><span data-stu-id="3d113-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="3d113-112">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3d113-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="3d113-113">Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="3d113-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="3d113-114">Creare un criterio di chiamata di emergenza personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d113-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d113-115">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d113-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3d113-116">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="3d113-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d113-117">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3d113-117">Click **Add**.</span></span>
3. <span data-ttu-id="3d113-118">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3d113-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="3d113-119">Impostare il modo in cui si vuole informare gli utenti dell'organizzazione, in genere il servizio di sicurezza, quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="3d113-120">A questo scopo, in **modalità notifica**selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d113-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="3d113-121">**Solo notifica**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati.</span><span class="sxs-lookup"><span data-stu-id="3d113-121">**Notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="3d113-122">**In conferenza ma in sordina**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati, che possono ascoltare, ma non partecipare, nella conversazione tra il chiamante e l'operatore di PSAP.</span><span class="sxs-lookup"><span data-stu-id="3d113-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="3d113-123">Se è stata selezionata la modalità di notifica **in conferenza ma disattivato** , nella casella **Numero chiamata in uscita per le notifiche** è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-123">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="3d113-124">Ad esempio, immettere il numero del servizio di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare o partecipare alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="3d113-124">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in or participate in the call.</span></span>
6. <span data-ttu-id="3d113-125">Cercare e selezionare uno o più utenti o gruppi, ad esempio il servizio di sicurezza dell'organizzazione, per avvisare quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3d113-125">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="3d113-126">La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3d113-126">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="3d113-127">Può essere notificato un massimo di 50 utenti.</span><span class="sxs-lookup"><span data-stu-id="3d113-127">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="3d113-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d113-128">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d113-129">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d113-129">Using PowerShell</span></span>

<span data-ttu-id="3d113-130">Vedere [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3d113-130">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="3d113-131">Modificare un criterio per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="3d113-131">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d113-132">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d113-132">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3d113-133">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="3d113-133">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="3d113-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="3d113-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d113-135">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="3d113-135">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3d113-136">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d113-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d113-137">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d113-137">Using PowerShell</span></span>

<span data-ttu-id="3d113-138">Vedere [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3d113-138">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="3d113-139">Assegnare un criterio di chiamata di emergenza personalizzato agli utenti</span><span class="sxs-lookup"><span data-stu-id="3d113-139">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d113-140">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d113-140">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3d113-141">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="3d113-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3d113-142">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="3d113-142">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="3d113-143">In **criteri**per le chiamate di emergenza selezionare i criteri da assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d113-143">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="3d113-144">Per assegnare un criterio teams personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="3d113-144">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="3d113-145">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3d113-145">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3d113-146">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="3d113-146">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d113-147">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="3d113-147">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3d113-148">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="3d113-148">Select **Manage users**.</span></span>
4. <span data-ttu-id="3d113-149">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3d113-149">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3d113-150">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3d113-150">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3d113-151">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3d113-151">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d113-152">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d113-152">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="3d113-153">Assegnare un criterio di chiamata di emergenza personalizzato a un utente</span><span class="sxs-lookup"><span data-stu-id="3d113-153">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="3d113-154">Vedere [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3d113-154">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="3d113-155">Assegnare un criterio di chiamata di emergenza personalizzato agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="3d113-155">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="3d113-156">È consigliabile assegnare un criterio di chiamata di emergenza personalizzato a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="3d113-156">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="3d113-157">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3d113-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="3d113-158">A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3d113-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="3d113-159">In questo esempio assegniamo un criterio denominato criteri per le chiamate di emergenza per tutti gli utenti del gruppo operazioni contoso.</span><span class="sxs-lookup"><span data-stu-id="3d113-159">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="3d113-160">Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="3d113-160">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="3d113-161">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="3d113-161">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="3d113-162">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="3d113-162">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3d113-163">Assegnare tutti gli utenti del gruppo a un determinato criterio teams.</span><span class="sxs-lookup"><span data-stu-id="3d113-163">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="3d113-164">In questo esempio, i criteri di routing delle chiamate di emergenza delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3d113-164">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="3d113-165">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3d113-165">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="3d113-166">Assegnare un criterio di chiamata di emergenza personalizzato a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="3d113-166">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="3d113-167">Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="3d113-167">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="3d113-168">L'esempio seguente mostra come assegnare un criterio denominato criteri di chiamata di emergenza contoso 1 al sito di Microsoft1.</span><span class="sxs-lookup"><span data-stu-id="3d113-168">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a><span data-ttu-id="3d113-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3d113-169">Related topics</span></span>

- [<span data-ttu-id="3d113-170">Gestire i criteri di routing delle chiamate di emergenza in teams</span><span class="sxs-lookup"><span data-stu-id="3d113-170">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="3d113-171">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="3d113-171">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
