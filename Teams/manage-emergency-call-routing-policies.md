---
title: Gestire i criteri del routing delle chiamate di emergenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di routing delle chiamate di emergenza in Microsoft teams per configurare i numeri di emergenza e specificare la modalità di routing delle chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217697"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="f1464-103">Gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1464-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="f1464-104">Se è stato distribuito il [routing diretto del sistema telefonico](direct-routing-landing-page.md) nell'organizzazione, è possibile usare i criteri di routing delle chiamate di emergenza in Microsoft teams per configurare i numeri di emergenza e specificare il modo in cui le chiamate di emergenza vengono instradate.</span><span class="sxs-lookup"><span data-stu-id="f1464-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="f1464-105">I criteri di routing delle chiamate di emergenza determinano se i servizi di emergenza avanzati sono abilitati per gli utenti a cui sono assegnati i criteri, i numeri usati per chiamare i servizi di emergenza, ad esempio 911 negli Stati Uniti, e la modalità di routing delle chiamate ai servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="f1464-106">Puoi gestire i criteri di routing delle chiamate di **Voice**emergenza passando a  >  **criteri** per l'emergenza vocale nell'interfaccia di amministrazione di Microsoft teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1464-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="f1464-107">I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f1464-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f1464-108">Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1464-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="f1464-109">Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1464-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="f1464-110">Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle.</span><span class="sxs-lookup"><span data-stu-id="f1464-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="f1464-111">Per i siti di rete, è possibile creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1464-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="f1464-112">Se i criteri di routing delle chiamate di emergenza sono stati assegnati a un sito di rete e a un utente e, se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="f1464-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="f1464-113">Creare un criterio di routing delle chiamate di emergenza personalizzato</span><span class="sxs-lookup"><span data-stu-id="f1464-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1464-114">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1464-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f1464-115">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di routing delle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="f1464-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="f1464-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f1464-116">Click **Add**.</span></span>
3. <span data-ttu-id="f1464-117">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="f1464-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="f1464-118">Per abilitare le chiamate di emergenza dinamiche, attivare **chiamate dinamiche di emergenza**.</span><span class="sxs-lookup"><span data-stu-id="f1464-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="f1464-119">Quando è abilitata la chiamata di emergenza dinamica, i team recuperano le informazioni sui criteri e sulla posizione dal servizio e includono tali informazioni come parte della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="f1464-120">Definire uno o più numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="f1464-121">A tale scopo, in **numeri di emergenza**fare clic su **Aggiungi**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1464-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="f1464-122">**Stringa di chiamata di emergenza**: immettere la stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="f1464-123">Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="f1464-124">Per il routing diretto, ci si sta allontanando dai client di teams inviando chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="f1464-125">Finché la transizione non viene completata, il modello di route vocale in modo che corrisponda a una stringa di chiamata di emergenza dovrebbe garantire che venga eseguita una corrispondenza per le stringhe che hanno e non hanno un "+" precedente, ad esempio 911 e + 911.</span><span class="sxs-lookup"><span data-stu-id="f1464-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="f1464-126">Ad esempio, ^ \\ +? 911 o. \*.</span><span class="sxs-lookup"><span data-stu-id="f1464-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="f1464-127">**Maschera di chiamata di emergenza**: per ogni numero di emergenza è possibile specificare zero o più maschere di chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="f1464-128">Una maschera di chiamata è il numero che si vuole tradurre nel valore della stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="f1464-129">In questo modo, i numeri di emergenza alternativi possono essere chiamati e i servizi di emergenza raggiungono ancora la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1464-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="f1464-130">Ad esempio, Aggiungi 112 come maschera di chiamata di emergenza, che è il numero del servizio di emergenza per la maggior parte dell'Europa e 911 come stringa di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1464-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="f1464-131">Un utente di teams proveniente da Europa che sta visitando potrebbe non sapere che 911 è il numero di emergenza negli Stati Uniti e quando chiama 112, viene effettuata la chiamata a 911.</span><span class="sxs-lookup"><span data-stu-id="f1464-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="f1464-132">Per definire più maschere di chiamata, separare ogni valore con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="f1464-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="f1464-133">Ad esempio, 112; 212.</span><span class="sxs-lookup"><span data-stu-id="f1464-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="f1464-134">**Record utilizzo PSTN**: selezionare il record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f1464-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="f1464-135">Il record uso PSTN viene usato per determinare quale route viene usata per instradare chiamate di emergenza da utenti autorizzati ad usarle.</span><span class="sxs-lookup"><span data-stu-id="f1464-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="f1464-136">La route associata a questo uso deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al più vicino punto di risposta di sicurezza pubblica (PSAP).</span><span class="sxs-lookup"><span data-stu-id="f1464-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1464-137">Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio.</span><span class="sxs-lookup"><span data-stu-id="f1464-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="f1464-138">Questo significa che per un criterio puoi definire più numeri di emergenza ed è possibile impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata solo una volta.</span><span class="sxs-lookup"><span data-stu-id="f1464-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="f1464-139">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1464-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f1464-140">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1464-140">Using PowerShell</span></span>

<span data-ttu-id="f1464-141">Vedere [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f1464-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="f1464-142">Modificare i criteri di routing delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="f1464-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1464-143">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1464-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f1464-144">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="f1464-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="f1464-145">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di routing delle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="f1464-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="f1464-146">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f1464-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f1464-147">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1464-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f1464-148">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1464-148">Using PowerShell</span></span>

<span data-ttu-id="f1464-149">Vedere [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f1464-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="f1464-150">Assegnare criteri di routing delle chiamate di emergenza personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="f1464-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="f1464-151">Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="f1464-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="f1464-152">Assegnare criteri di routing delle chiamate di emergenza personalizzati a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f1464-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="f1464-153">Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1464-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="f1464-154">Questo esempio Mostra come assegnare un criterio denominato criteri di routing delle chiamate di emergenza 1 al sito di Microsoft1.</span><span class="sxs-lookup"><span data-stu-id="f1464-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="f1464-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1464-155">Related topics</span></span>

[<span data-ttu-id="f1464-156">Gestire i criteri delle chiamate di emergenza in teams</span><span class="sxs-lookup"><span data-stu-id="f1464-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="f1464-157">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="f1464-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="f1464-158">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="f1464-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
