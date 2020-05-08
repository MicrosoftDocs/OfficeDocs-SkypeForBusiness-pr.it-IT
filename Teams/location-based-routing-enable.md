---
title: Abilitare l'instradamento basato sulla posizione per Instradamento diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare il routing basato sulla posizione per il routing diretto, incluso l'abilitazione per gli utenti, i siti di rete, le configurazioni dei gateway e i criteri di chiamata.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158993"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="1706e-103">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="1706e-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1706e-104">Prima di eseguire la procedura descritta in questo articolo, verificare di aver letto il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) ed è stata completata la procedura descritta in [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="1706e-105">Questo articolo descrive come abilitare il routing basato sulla posizione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="1706e-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="1706e-106">Dopo aver distribuito il routing diretto del sistema telefonico e configurato le aree geografiche, i siti e le subnet della rete, è possibile abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1706e-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="1706e-107">Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1706e-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1706e-108">Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="1706e-109">È necessario abilitare il routing basato sulla posizione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1706e-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="1706e-110">Utenti</span><span class="sxs-lookup"><span data-stu-id="1706e-110">Users</span></span>
- <span data-ttu-id="1706e-111">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="1706e-111">Network sites</span></span>
- <span data-ttu-id="1706e-112">Configurazioni gateway</span><span class="sxs-lookup"><span data-stu-id="1706e-112">Gateway configurations</span></span>
- <span data-ttu-id="1706e-113">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="1706e-113">Calling policies</span></span>

<span data-ttu-id="1706e-114">Puoi usare l'interfaccia di [amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1706e-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1706e-115">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1706e-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1706e-116">Abilitare il routing basato sulla posizione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1706e-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1706e-117">Creare un criterio di routing vocale e assegnare gli usi PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="1706e-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="1706e-118">Quando si assegnano gli usi PSTN a un criterio, verificare di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1706e-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="1706e-119">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito.</span><span class="sxs-lookup"><span data-stu-id="1706e-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="1706e-120">USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="1706e-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="1706e-121">Assegnare i criteri di routing vocale agli utenti che richiedono restrizioni di routing per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1706e-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="1706e-122">Per ulteriori informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere [gestire i criteri di routing vocale in Microsoft teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1706e-123">Abilitare il routing basato sulla posizione per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="1706e-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="1706e-124">Abilitare il routing basato sulla posizione per i siti che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="1706e-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="1706e-125">A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alla**topologia di rete** **locations** > , seleziona un sito di rete, fai clic su **modifica**e quindi attiva **routing basato sulla posizione**.</span><span class="sxs-lookup"><span data-stu-id="1706e-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="1706e-126">Per altre informazioni, vedere [gestire la topologia di rete](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1706e-127">Abilitare il routing basato sulla posizione per i gateway</span><span class="sxs-lookup"><span data-stu-id="1706e-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="1706e-128">Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="1706e-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="1706e-129">Nella barra di spostamento sinistra, passa a routing **vocale** > **diretto**e quindi fai clic sulla scheda **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="1706e-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="1706e-130">Selezionare l'SBC e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="1706e-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="1706e-131">In **ottimizzazione di routing e media basato sulla posizione**attivare **Abilita routing basato sulla posizione**.</span><span class="sxs-lookup"><span data-stu-id="1706e-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="1706e-132">Specificare l'ID sito del gateway e quindi impostare la modalità di bypass.</span><span class="sxs-lookup"><span data-stu-id="1706e-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="1706e-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1706e-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1706e-134">Abilitare il routing basato sulla posizione per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="1706e-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1706e-135">Per applicare il routing basato sulla posizione per utenti specifici, configurare i criteri di chiamata dell'utente per evitare il bypass PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1706e-136">A questo scopo, attiva l'impostazione **Impedisci esclusione di pedaggio** nel criterio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1706e-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="1706e-137">Per altre informazioni, vedere [chiamare i criteri in teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="1706e-138">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1706e-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1706e-139">Abilitare il routing basato sulla posizione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1706e-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1706e-140">Usa il cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="1706e-141">Per più usi, separare ogni utilizzo con una virgola.</span><span class="sxs-lookup"><span data-stu-id="1706e-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="1706e-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1706e-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="1706e-143">Usa il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli usi appropriati della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="1706e-144">Quando si assegnano gli usi PSTN a un criterio di routing vocale, verificare di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1706e-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="1706e-145">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito</span><span class="sxs-lookup"><span data-stu-id="1706e-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="1706e-146">USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="1706e-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="1706e-147">In questo esempio creiamo due nuovi criteri di routing vocale e li assegniamo agli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="1706e-148">Nella tabella seguente sono illustrati i criteri di routing vocale definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="1706e-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="1706e-149">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="1706e-149">Voice routing policy 1</span></span>|<span data-ttu-id="1706e-150">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="1706e-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="1706e-151">ID criterio vocale online</span><span class="sxs-lookup"><span data-stu-id="1706e-151">Online voice policy ID</span></span>   |<span data-ttu-id="1706e-152">Politica di routing vocale Delhi online</span><span class="sxs-lookup"><span data-stu-id="1706e-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="1706e-153">Criteri di routing vocale di Hyderabad online</span><span class="sxs-lookup"><span data-stu-id="1706e-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="1706e-154">Usi PSTN online</span><span class="sxs-lookup"><span data-stu-id="1706e-154">Online PSTN usages</span></span>  |<span data-ttu-id="1706e-155">Lunga distanza</span><span class="sxs-lookup"><span data-stu-id="1706e-155">Long Distance</span></span>  |<span data-ttu-id="1706e-156">Lunga distanza, locale, interno</span><span class="sxs-lookup"><span data-stu-id="1706e-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="1706e-157">Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono restrizioni di routing per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1706e-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1706e-158">Abilitare il routing basato sulla posizione per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="1706e-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="1706e-159">Usa il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="1706e-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="1706e-160">In questo esempio, consentiamo il routing basato sulla posizione per il sito Delhi e il sito Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1706e-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="1706e-161">La tabella seguente mostra i siti abilitati per il routing basato sulla posizione in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="1706e-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="1706e-162">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1706e-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="1706e-163">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1706e-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="1706e-164">Nome sito</span><span class="sxs-lookup"><span data-stu-id="1706e-164">Site name</span></span>    |<span data-ttu-id="1706e-165">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1706e-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="1706e-166">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1706e-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="1706e-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="1706e-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="1706e-168">Vero</span><span class="sxs-lookup"><span data-stu-id="1706e-168">True</span></span>    |<span data-ttu-id="1706e-169">Vero</span><span class="sxs-lookup"><span data-stu-id="1706e-169">True</span></span>    |
    |<span data-ttu-id="1706e-170">Subnet</span><span class="sxs-lookup"><span data-stu-id="1706e-170">Subnets</span></span>     |<span data-ttu-id="1706e-171">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1706e-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="1706e-172">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1706e-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1706e-173">Abilitare il routing basato sulla posizione per i gateway</span><span class="sxs-lookup"><span data-stu-id="1706e-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="1706e-174">Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni sito di gateway o di rete.</span><span class="sxs-lookup"><span data-stu-id="1706e-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="1706e-175">Se più gateway sono associati a un sistema, ad esempio gateway o PBX, modifica ogni gateway per abilitare le restrizioni di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1706e-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="1706e-176">In questo esempio creiamo una configurazione di gateway per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="1706e-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="1706e-177">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1706e-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="1706e-178">Usa il cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing basato sulla posizione per i gateway che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="1706e-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="1706e-179">Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="1706e-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="1706e-180">In questo esempio, consentiamo il routing basato sulla posizione per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1706e-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="1706e-181">Non abilitare il routing basato sulla posizione per i gateway che non instradano le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="1706e-182">Tuttavia, devi comunque associare il gateway al sito di rete in cui si trova il sistema.</span><span class="sxs-lookup"><span data-stu-id="1706e-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="1706e-183">Questo perché le restrizioni di routing basate sul percorso devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="1706e-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="1706e-184">In questo esempio, il routing basato sulla posizione non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1706e-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="1706e-185">Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ad esempio, un PBX) avranno restrizioni simili agli endpoint degli utenti di teams abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1706e-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="1706e-186">Ciò significa che questi utenti possono effettuare e ricevere chiamate da e verso utenti di teams indipendentemente dalla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1706e-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="1706e-187">Possono anche effettuare e ricevere chiamate da e verso altri sistemi che non instradano le chiamate alla rete PSTN, ad esempio un endpoint connesso a un PBX diverso, indipendentemente dal sito di rete a cui è associato il sistema.</span><span class="sxs-lookup"><span data-stu-id="1706e-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="1706e-188">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti delle chiamate e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti a imposte di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1706e-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="1706e-189">Queste chiamate devono usare solo gateway PSTN definiti come locali per tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="1706e-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="1706e-190">La tabella seguente mostra la configurazione del gateway di quattro gateway in due diversi siti di rete: due collegati a gateway PSTN e due collegati a sistemi PBX.</span><span class="sxs-lookup"><span data-stu-id="1706e-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="1706e-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="1706e-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="1706e-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="1706e-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="1706e-193">PstnGateway: Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1706e-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="1706e-194">Vero</span><span class="sxs-lookup"><span data-stu-id="1706e-194">True</span></span>     |   <span data-ttu-id="1706e-195">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1706e-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="1706e-196">PstnGateway: Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1706e-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="1706e-197">Vero</span><span class="sxs-lookup"><span data-stu-id="1706e-197">True</span></span>      |      <span data-ttu-id="1706e-198">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1706e-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="1706e-199">PstnGateway: Gateway 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1706e-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="1706e-200">Falso</span><span class="sxs-lookup"><span data-stu-id="1706e-200">False</span></span>     |     <span data-ttu-id="1706e-201">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1706e-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="1706e-202">PstnGateway: Gateway 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1706e-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="1706e-203">Falso</span><span class="sxs-lookup"><span data-stu-id="1706e-203">False</span></span>     |    <span data-ttu-id="1706e-204">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1706e-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1706e-205">Abilitare il routing basato sulla posizione per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="1706e-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1706e-206">Per applicare il routing basato sulla posizione per gli utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione dei pedaggi di PTSN.</span><span class="sxs-lookup"><span data-stu-id="1706e-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="1706e-207">Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare il routing basato sulla posizione impedendo l'esclusione di pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="1706e-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="1706e-208">In questo esempio viene impedito l'esclusione del pedaggio PSTN ai criteri di chiamata di Utente1.</span><span class="sxs-lookup"><span data-stu-id="1706e-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="1706e-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1706e-209">Related topics</span></span>

- [<span data-ttu-id="1706e-210">Impostazioni di rete per le funzionalità vocali di cloud in teams</span><span class="sxs-lookup"><span data-stu-id="1706e-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
