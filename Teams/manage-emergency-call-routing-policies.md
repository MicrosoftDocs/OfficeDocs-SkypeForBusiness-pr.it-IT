---
title: Gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di routing delle chiamate di emergenza per la funzionalità Dynamic E911 in Microsoft teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: aed3b3d3cbd1023a3370c3c271e07a61179447da
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615806"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="c9c78-103">Gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-103">Manage emergency call routing policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="c9c78-104">Se è stato distribuito il routing diretto del sistema telefonico nell'organizzazione, è possibile usare i criteri di routing delle chiamate di emergenza in Microsoft teams per configurare i numeri di emergenza e specificare il modo in cui le chiamate di emergenza vengono instradate.</span><span class="sxs-lookup"><span data-stu-id="c9c78-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="c9c78-105">I criteri di routing delle chiamate di emergenza determinano se i servizi di emergenza avanzati sono abilitati per gli utenti a cui sono assegnati i criteri, i numeri usati per chiamare i servizi di emergenza, ad esempio 911 negli Stati Uniti, e la modalità di routing delle chiamate ai servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="c9c78-106">Puoi gestire i criteri di routing delle chiamate di emergenza passando a criteri per l'**emergenza** **vocale** > nell'interfaccia di amministrazione di Microsoft teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9c78-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="c9c78-107">I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c9c78-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c9c78-108">Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c9c78-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="c9c78-109">Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c9c78-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c9c78-110">Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.</span><span class="sxs-lookup"><span data-stu-id="c9c78-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="c9c78-111">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c9c78-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="c9c78-112">Se i criteri di routing delle chiamate di emergenza sono stati assegnati a un sito di rete e a un utente e, se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="c9c78-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="c9c78-113">Creare un criterio di routing delle chiamate di emergenza personalizzato</span><span class="sxs-lookup"><span data-stu-id="c9c78-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c9c78-114">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c9c78-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di routing delle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="c9c78-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c9c78-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-116">Click **Add**.</span></span>
3. <span data-ttu-id="c9c78-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="c9c78-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c9c78-118">Per abilitare servizi di emergenza avanzati, attivare **servizi di emergenza avanzati**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="c9c78-119">Quando sono abilitati i servizi di emergenza avanzati, i team recuperano le informazioni sui criteri e sulla posizione dal servizio e includono tali informazioni come parte della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="c9c78-120">Definire uno dei numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="c9c78-121">Per eseguire questa operazione, in **numeri di emergenza**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9c78-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="c9c78-122">**Stringa di chiamata di emergenza**: immettere la stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="c9c78-123">Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-123">This dial string indicates that a call is an emergency call.</span></span>
    2. <span data-ttu-id="c9c78-124">**Maschera di chiamata di emergenza**: per ogni numero di emergenza è possibile specificare zero o più maschere di chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-124">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="c9c78-125">Una maschera di chiamata è il numero che si vuole tradurre nel valore della stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-125">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="c9c78-126">In questo modo, i numeri di emergenza alternativi possono essere chiamati e i servizi di emergenza raggiungono ancora la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9c78-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="c9c78-127">Ad esempio, Aggiungi 112 come maschera di chiamata di emergenza, che è il numero del servizio di emergenza per la maggior parte dell'Europa e 911 come stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c9c78-127">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="c9c78-128">Un utente di teams proveniente da Europa che sta visitando potrebbe non sapere che 911 è il numero di emergenza negli Stati Uniti e quando chiama 112, viene effettuata la chiamata a 911.</span><span class="sxs-lookup"><span data-stu-id="c9c78-128">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="c9c78-129">Per definire più maschere di chiamata, separare ogni valore con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="c9c78-129">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="c9c78-130">Ad esempio, 112; 212.</span><span class="sxs-lookup"><span data-stu-id="c9c78-130">For example, 112;212.</span></span>
    3. <span data-ttu-id="c9c78-131">**Uso PSTN**: selezionare l'utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="c9c78-131">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="c9c78-132">L'utilizzo PSTN viene usato per determinare quale route viene usata per instradare chiamate di emergenza da utenti autorizzati ad usarle.</span><span class="sxs-lookup"><span data-stu-id="c9c78-132">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="c9c78-133">La route associata a questo uso deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di risposta di sicurezza pubblica più vicino (PSAP).</span><span class="sxs-lookup"><span data-stu-id="c9c78-133">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9c78-134">Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio.</span><span class="sxs-lookup"><span data-stu-id="c9c78-134">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="c9c78-135">Questo significa che per un criterio puoi definire più numeri di emergenza ed è possibile impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata solo una volta.</span><span class="sxs-lookup"><span data-stu-id="c9c78-135">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="c9c78-136">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-136">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c9c78-137">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9c78-137">Using PowerShell</span></span>

<span data-ttu-id="c9c78-138">Vedere [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c9c78-138">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="c9c78-139">Modificare i criteri di routing delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="c9c78-139">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c9c78-140">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-140">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c9c78-141">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="c9c78-141">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="c9c78-142">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di routing delle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="c9c78-142">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c9c78-143">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c9c78-144">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-144">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c9c78-145">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9c78-145">Using PowerShell</span></span>

<span data-ttu-id="c9c78-146">Vedere [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c9c78-146">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="c9c78-147">Assegnare criteri di routing delle chiamate di emergenza personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="c9c78-147">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c9c78-148">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-148">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c9c78-149">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="c9c78-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c9c78-150">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-150">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="c9c78-151">In **criteri di routing delle chiamate di emergenza**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-151">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="c9c78-152">Per assegnare un criterio teams personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="c9c78-152">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="c9c78-153">In alternativa, è anche possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9c78-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c9c78-154">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di routing delle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="c9c78-154">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c9c78-155">Selezionare il criterio facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="c9c78-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c9c78-156">Selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="c9c78-157">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c9c78-158">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c9c78-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c9c78-159">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c9c78-159">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c9c78-160">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9c78-160">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="c9c78-161">Assegnare criteri di routing delle chiamate di emergenza personalizzati a un utente</span><span class="sxs-lookup"><span data-stu-id="c9c78-161">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="c9c78-162">Vedere [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c9c78-162">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="c9c78-163">Assegnare criteri di routing delle chiamate di emergenza personalizzati agli utenti di un gruppo</span><span class="sxs-lookup"><span data-stu-id="c9c78-163">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="c9c78-164">È consigliabile assegnare criteri di routing delle chiamate di emergenza personalizzati a più utenti già identificati.</span><span class="sxs-lookup"><span data-stu-id="c9c78-164">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="c9c78-165">Ad esempio, potresti voler assegnare un criterio a tutti gli utenti in un gruppo di sicurezza o di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c9c78-165">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="c9c78-166">A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c9c78-166">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="c9c78-167">In questo esempio viene assegnato un criterio denominato criteri di routing delle chiamate di emergenza HR a tutti gli utenti del gruppo contoso HR.</span><span class="sxs-lookup"><span data-stu-id="c9c78-167">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c9c78-168">Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="c9c78-168">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c9c78-169">Ottenere il GroupObjectId del gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="c9c78-169">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="c9c78-170">Ottenere i membri del gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="c9c78-170">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c9c78-171">Assegnare tutti gli utenti del gruppo a un determinato criterio teams.</span><span class="sxs-lookup"><span data-stu-id="c9c78-171">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="c9c78-172">In questo esempio si tratta di criteri di routing delle chiamate di emergenza HR.</span><span class="sxs-lookup"><span data-stu-id="c9c78-172">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="c9c78-173">A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9c78-173">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="c9c78-174">Assegnare criteri di routing delle chiamate di emergenza personalizzati a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="c9c78-174">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="c9c78-175">Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="c9c78-175">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="c9c78-176">Questo esempio Mostra come assegnare un criterio denominato criteri di routing delle chiamate di emergenza 1 al sito di Microsoft1.</span><span class="sxs-lookup"><span data-stu-id="c9c78-176">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="c9c78-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c9c78-177">Related topics</span></span>

- [<span data-ttu-id="c9c78-178">Gestire i criteri delle chiamate di emergenza in teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-178">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="c9c78-179">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="c9c78-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
