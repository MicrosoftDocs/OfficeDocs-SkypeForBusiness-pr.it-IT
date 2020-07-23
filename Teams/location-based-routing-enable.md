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
ms.openlocfilehash: e4cadbfb700c7478cb77c62f4597c9ae00164b0c
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372045"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="c337e-103">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="c337e-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="c337e-104">Prima di eseguire la procedura descritta in questo articolo, verificare di aver letto il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) ed è stata completata la procedura descritta in [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="c337e-105">Questo articolo descrive come abilitare il routing basato sulla posizione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="c337e-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="c337e-106">Dopo aver distribuito il routing diretto del sistema telefonico e configurato le aree geografiche, i siti e le subnet della rete, è possibile abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c337e-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="c337e-107">Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c337e-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="c337e-108">Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="c337e-109">È necessario abilitare il routing basato sulla posizione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c337e-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="c337e-110">Utenti</span><span class="sxs-lookup"><span data-stu-id="c337e-110">Users</span></span>
- <span data-ttu-id="c337e-111">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="c337e-111">Network sites</span></span>
- <span data-ttu-id="c337e-112">Configurazioni gateway</span><span class="sxs-lookup"><span data-stu-id="c337e-112">Gateway configurations</span></span>
- <span data-ttu-id="c337e-113">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="c337e-113">Calling policies</span></span>

<span data-ttu-id="c337e-114">Puoi usare l'interfaccia di [amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c337e-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c337e-115">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c337e-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c337e-116">Abilitare il routing basato sulla posizione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c337e-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c337e-117">Creare un criterio di routing vocale e assegnare gli usi PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="c337e-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="c337e-118">Quando si assegnano gli usi PSTN a un criterio, verificare di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c337e-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="c337e-119">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito.</span><span class="sxs-lookup"><span data-stu-id="c337e-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="c337e-120">USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="c337e-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="c337e-121">Assegnare i criteri di routing vocale agli utenti che richiedono restrizioni di routing per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c337e-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="c337e-122">Per ulteriori informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere [gestire i criteri di routing vocale in Microsoft teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c337e-123">Abilitare il routing basato sulla posizione per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="c337e-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="c337e-124">Abilitare il routing basato sulla posizione per i siti che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="c337e-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="c337e-125">A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Locations**, vai alla  >  **topologia di rete**locations, seleziona un sito di rete, fai clic su **modifica**e quindi attiva **routing basato sulla posizione**.</span><span class="sxs-lookup"><span data-stu-id="c337e-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="c337e-126">Per altre informazioni, vedere [gestire la topologia di rete](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c337e-127">Abilitare il routing basato sulla posizione per i gateway</span><span class="sxs-lookup"><span data-stu-id="c337e-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="c337e-128">Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="c337e-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="c337e-129">Nella barra di spostamento sinistra, passa a routing **vocale**  >  **diretto**e quindi fai clic sulla scheda **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="c337e-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="c337e-130">Selezionare l'SBC e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c337e-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="c337e-131">In **ottimizzazione di routing e media basato sulla posizione**attivare **Abilita routing basato sulla posizione**.</span><span class="sxs-lookup"><span data-stu-id="c337e-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="c337e-132">Specificare l'ID sito del gateway e quindi impostare la modalità di bypass.</span><span class="sxs-lookup"><span data-stu-id="c337e-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="c337e-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c337e-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c337e-134">Abilitare il routing basato sulla posizione per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="c337e-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c337e-135">Per applicare il routing basato sulla posizione per utenti specifici, configurare i criteri di chiamata dell'utente per evitare il bypass PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="c337e-136">A questo scopo, attiva l'impostazione **Impedisci esclusione di pedaggio** nel criterio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c337e-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="c337e-137">Per altre informazioni, vedere [chiamare i criteri in teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="c337e-138">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c337e-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c337e-139">Abilitare il routing basato sulla posizione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c337e-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c337e-140">Usa il cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="c337e-141">Per più usi, separare ogni utilizzo con una virgola.</span><span class="sxs-lookup"><span data-stu-id="c337e-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="c337e-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c337e-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="c337e-143">Usa il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli usi appropriati della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="c337e-144">Quando si assegnano gli usi PSTN a un criterio di routing vocale, verificare di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c337e-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="c337e-145">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito</span><span class="sxs-lookup"><span data-stu-id="c337e-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="c337e-146">USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="c337e-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="c337e-147">In questo esempio creiamo due nuovi criteri di routing vocale e li assegniamo agli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="c337e-148">Nella tabella seguente sono illustrati i criteri di routing vocale definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="c337e-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="c337e-149">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="c337e-149">Voice routing policy 1</span></span>|<span data-ttu-id="c337e-150">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="c337e-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="c337e-151">ID criterio vocale online</span><span class="sxs-lookup"><span data-stu-id="c337e-151">Online voice policy ID</span></span>   |<span data-ttu-id="c337e-152">Politica di routing vocale Delhi online</span><span class="sxs-lookup"><span data-stu-id="c337e-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="c337e-153">Criteri di routing vocale di Hyderabad online</span><span class="sxs-lookup"><span data-stu-id="c337e-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="c337e-154">Usi PSTN online</span><span class="sxs-lookup"><span data-stu-id="c337e-154">Online PSTN usages</span></span>  |<span data-ttu-id="c337e-155">Lunga distanza</span><span class="sxs-lookup"><span data-stu-id="c337e-155">Long Distance</span></span>  |<span data-ttu-id="c337e-156">Lunga distanza, locale, interno</span><span class="sxs-lookup"><span data-stu-id="c337e-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="c337e-157">Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono restrizioni di routing per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c337e-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c337e-158">Abilitare il routing basato sulla posizione per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="c337e-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="c337e-159">Usa il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="c337e-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="c337e-160">In questo esempio, consentiamo il routing basato sulla posizione per il sito Delhi e il sito Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="c337e-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="c337e-161">La tabella seguente mostra i siti abilitati per il routing basato sulla posizione in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="c337e-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="c337e-162">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c337e-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="c337e-163">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c337e-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="c337e-164">Nome sito</span><span class="sxs-lookup"><span data-stu-id="c337e-164">Site name</span></span>    |<span data-ttu-id="c337e-165">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c337e-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="c337e-166">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c337e-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="c337e-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="c337e-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="c337e-168">Vero</span><span class="sxs-lookup"><span data-stu-id="c337e-168">True</span></span>    |<span data-ttu-id="c337e-169">Vero</span><span class="sxs-lookup"><span data-stu-id="c337e-169">True</span></span>    |
    |<span data-ttu-id="c337e-170">Subnet</span><span class="sxs-lookup"><span data-stu-id="c337e-170">Subnets</span></span>     |<span data-ttu-id="c337e-171">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c337e-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="c337e-172">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c337e-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c337e-173">Abilitare il routing basato sulla posizione per i gateway</span><span class="sxs-lookup"><span data-stu-id="c337e-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="c337e-174">Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni sito di gateway o di rete.</span><span class="sxs-lookup"><span data-stu-id="c337e-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="c337e-175">Se più gateway sono associati a un sistema, ad esempio gateway o PBX, modifica ogni gateway per abilitare le restrizioni di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c337e-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="c337e-176">In questo esempio creiamo una configurazione di gateway per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="c337e-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="c337e-177">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c337e-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="c337e-178">Usa il cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing basato sulla posizione per i gateway che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="c337e-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="c337e-179">Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="c337e-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="c337e-180">In questo esempio, consentiamo il routing basato sulla posizione per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="c337e-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="c337e-181">Non abilitare il routing basato sulla posizione per i gateway che non instradano le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="c337e-182">Tuttavia, devi comunque associare il gateway al sito di rete in cui si trova il sistema.</span><span class="sxs-lookup"><span data-stu-id="c337e-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="c337e-183">Questo perché le restrizioni di routing basate sul percorso devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="c337e-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="c337e-184">In questo esempio, il routing basato sulla posizione non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="c337e-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c337e-185">Abilitare il routing basato sulla posizione per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="c337e-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c337e-186">Per applicare il routing basato sulla posizione per gli utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione dei pedaggi di PTSN.</span><span class="sxs-lookup"><span data-stu-id="c337e-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="c337e-187">Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare il routing basato sulla posizione impedendo l'esclusione di pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="c337e-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="c337e-188">In questo esempio viene impedito l'esclusione del pedaggio PSTN ai criteri di chiamata di Utente1.</span><span class="sxs-lookup"><span data-stu-id="c337e-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="c337e-189">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c337e-189">Related topics</span></span>

- [<span data-ttu-id="c337e-190">Impostazioni di rete per le funzionalità vocali di cloud in teams</span><span class="sxs-lookup"><span data-stu-id="c337e-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
