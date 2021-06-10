---
title: Abilitare l'instradamento basato sulla posizione per Instradamento diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come abilitare Location-Based routing diretto, inclusa l'abilitazione per utenti, siti di rete, configurazioni di gateway e criteri di chiamata.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120577"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="d2335-103">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="d2335-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="d2335-104">Prima di seguire i passaggi descritti in questo articolo, assicurarsi di aver letto Pianificare il routing [Location-Based per](location-based-routing-plan.md) il routing diretto e di aver completato i passaggi descritti in Configurare le impostazioni di rete per Location-Based [Routing](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d2335-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="d2335-105">Questo articolo descrive come abilitare il routing Location-Based routing diretto.</span><span class="sxs-lookup"><span data-stu-id="d2335-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="d2335-106">Dopo aver distribuito Sistema telefonico routing diretto e aver configurato aree di rete, siti e subnet, è possibile abilitare Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="d2335-107">Per completare i passaggi descritti in questo articolo, è necessaria una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2335-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="d2335-108">Per altre informazioni, vedere Teams [panoramica di PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d2335-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="d2335-109">È necessario abilitare Location-Based routing per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2335-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="d2335-110">Utenti</span><span class="sxs-lookup"><span data-stu-id="d2335-110">Users</span></span>
- <span data-ttu-id="d2335-111">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="d2335-111">Network sites</span></span>
- <span data-ttu-id="d2335-112">Configurazioni del gateway</span><span class="sxs-lookup"><span data-stu-id="d2335-112">Gateway configurations</span></span>
- <span data-ttu-id="d2335-113">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="d2335-113">Calling policies</span></span>

<span data-ttu-id="d2335-114">È possibile usare [l'interfaccia di amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d2335-115">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2335-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="d2335-116">Abilitare Location-Based routing per gli utenti</span><span class="sxs-lookup"><span data-stu-id="d2335-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="d2335-117">Creare un criterio di routing vocale e assegnare gli utilizzi PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="d2335-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="d2335-118">Quando si assegnano gli utilizzi PSTN a un criterio, assicurarsi di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2335-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="d2335-119">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito.</span><span class="sxs-lookup"><span data-stu-id="d2335-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="d2335-120">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area Location-Based non sono necessarie restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="d2335-121">Assegnare i criteri di routing vocale agli utenti che richiedono l'applicazione di restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="d2335-122">Per altre informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere Gestire i criteri di routing vocale [in Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d2335-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="d2335-123">Abilitare il routing Location-Based per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="d2335-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="d2335-124">Abilitare Location-Based routing per i siti che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="d2335-125">A questo scopo, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Topologia di rete percorsi, selezionare un sito di rete, fare clic su Modifica e quindi attivare il routing basato sulla   >   **posizione.** </span><span class="sxs-lookup"><span data-stu-id="d2335-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="d2335-126">Per altre informazioni, vedere [Gestire la topologia di rete.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="d2335-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="d2335-127">Abilitare Location-Based routing per i gateway</span><span class="sxs-lookup"><span data-stu-id="d2335-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="d2335-128">Abilitare Location-Based routing ai gateway che instradare le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associare il sito di rete in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="d2335-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="d2335-129">Nel riquadro di spostamento sinistro passare a **Routing**  >  **diretto vocale** e quindi fare clic sulla scheda **SBC.**</span><span class="sxs-lookup"><span data-stu-id="d2335-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="d2335-130">Selezionare il valore SBC e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="d2335-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="d2335-131">In **Routing basato sulla posizione e ottimizzazione multimediale** attivare Abilita routing basato sulla **posizione.**</span><span class="sxs-lookup"><span data-stu-id="d2335-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="d2335-132">Specificare l'ID del sito gateway e quindi impostare la modalità di bypass.</span><span class="sxs-lookup"><span data-stu-id="d2335-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="d2335-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d2335-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="d2335-134">Abilitare Location-Based routing per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="d2335-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="d2335-135">Per applicare Location-Based routing per utenti specifici, configurare i criteri di chiamata dell'utente in modo da evitare il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2335-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="d2335-136">A questo scopo, attivare l'impostazione **Impedisci bypass** a pedaggio nel criterio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d2335-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="d2335-137">Per altre informazioni, vedere [Criteri di chiamata in Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d2335-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="d2335-138">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2335-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="d2335-139">Abilitare Location-Based routing per gli utenti</span><span class="sxs-lookup"><span data-stu-id="d2335-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="d2335-140">Usare il cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2335-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="d2335-141">Per più utilizzi, separare ogni utilizzo con una virgola.</span><span class="sxs-lookup"><span data-stu-id="d2335-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="d2335-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2335-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="d2335-143">Usare il cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli utilizzi PSTN appropriati.</span><span class="sxs-lookup"><span data-stu-id="d2335-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="d2335-144">Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, assicurarsi di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2335-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="d2335-145">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito</span><span class="sxs-lookup"><span data-stu-id="d2335-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="d2335-146">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area Location-Based non sono necessarie restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="d2335-147">In questo esempio vengono creati due nuovi criteri di routing vocale e vengono assegnati gli utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2335-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="d2335-148">La tabella seguente mostra i criteri di routing vocale definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d2335-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="d2335-149">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="d2335-149">Voice routing policy 1</span></span>|<span data-ttu-id="d2335-150">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="d2335-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="d2335-151">ID dei criteri vocali online</span><span class="sxs-lookup"><span data-stu-id="d2335-151">Online voice policy ID</span></span>   |<span data-ttu-id="d2335-152">Criteri di routing vocale online di Delhi</span><span class="sxs-lookup"><span data-stu-id="d2335-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="d2335-153">Criteri di routing vocale online di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d2335-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="d2335-154">Utilizzi PSTN online</span><span class="sxs-lookup"><span data-stu-id="d2335-154">Online PSTN usages</span></span>  |<span data-ttu-id="d2335-155">Lunga distanza</span><span class="sxs-lookup"><span data-stu-id="d2335-155">Long Distance</span></span>  |<span data-ttu-id="d2335-156">Interurbana, Locale, Interna</span><span class="sxs-lookup"><span data-stu-id="d2335-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="d2335-157">Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono l'applicazione di restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="d2335-158">Abilitare il routing Location-Based per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="d2335-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="d2335-159">Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare Location-Based routing e associare criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="d2335-160">In questo esempio viene abilitato Location-Based routing per il sito di Delhi e il sito di Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d2335-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="d2335-161">La tabella seguente mostra i siti abilitati per Location-Based routing in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d2335-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="d2335-162">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d2335-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="d2335-163">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d2335-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="d2335-164">Nome del sito</span><span class="sxs-lookup"><span data-stu-id="d2335-164">Site name</span></span>    |<span data-ttu-id="d2335-165">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d2335-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="d2335-166">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d2335-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="d2335-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="d2335-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="d2335-168">Vero</span><span class="sxs-lookup"><span data-stu-id="d2335-168">True</span></span>    |<span data-ttu-id="d2335-169">Vero</span><span class="sxs-lookup"><span data-stu-id="d2335-169">True</span></span>    |
    |<span data-ttu-id="d2335-170">Subnet</span><span class="sxs-lookup"><span data-stu-id="d2335-170">Subnets</span></span>     |<span data-ttu-id="d2335-171">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d2335-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="d2335-172">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d2335-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="d2335-173">Abilitare Location-Based routing per i gateway</span><span class="sxs-lookup"><span data-stu-id="d2335-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="d2335-174">Usare il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni gateway o sito di rete.</span><span class="sxs-lookup"><span data-stu-id="d2335-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="d2335-175">Se a un sistema sono associati più gateway, ad esempio Gateway o PBX, modificare ogni gateway per abilitare Location-Based di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="d2335-176">In questo esempio viene creata una configurazione del gateway per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="d2335-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="d2335-177">Per altre informazioni, vedere [Configurare il routing diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="d2335-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="d2335-178">Usare il cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing Location-Based per i gateway che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="d2335-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="d2335-179">Abilitare Location-Based routing ai gateway che instradare le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associare il sito di rete in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="d2335-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="d2335-180">In questo esempio viene abilitato Location-Based routing per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad.In this example, we enable Location-Based routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span><span class="sxs-lookup"><span data-stu-id="d2335-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="d2335-181">Non abilitare il Location-Based routing per i gateway che non instradare le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2335-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="d2335-182">Tuttavia, è comunque necessario associare il gateway al sito di rete in cui si trova il sistema.</span><span class="sxs-lookup"><span data-stu-id="d2335-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="d2335-183">Questo avviene perché Location-Based restrizioni di routing devono essere applicate per le chiamate PSTN che raggiungono gli endpoint connessi tramite questo gateway.</span><span class="sxs-lookup"><span data-stu-id="d2335-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="d2335-184">In questo esempio, Location-Based routing non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="d2335-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="d2335-185">Abilitare Location-Based routing per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="d2335-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="d2335-186">Per applicare Location-Based routing per utenti specifici, configurare i criteri vocali degli utenti in modo da impedire il bypass a pedaggio PTSN.</span><span class="sxs-lookup"><span data-stu-id="d2335-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="d2335-187">Usare il cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare Location-Based il routing dei messaggi impedendo il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2335-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="d2335-188">In questo esempio viene impedito il bypass a pedaggio PSTN ai criteri di chiamata dell'utente1.</span><span class="sxs-lookup"><span data-stu-id="d2335-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="d2335-189">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d2335-189">Related topics</span></span>

- [<span data-ttu-id="d2335-190">Impostazioni di rete per le funzionalità vocali cloud in Teams</span><span class="sxs-lookup"><span data-stu-id="d2335-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)