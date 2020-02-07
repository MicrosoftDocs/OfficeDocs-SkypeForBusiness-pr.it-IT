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
description: Informazioni su come abilitare il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 734a2354e81dc88430e8f880c46b0f97862158b5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836556"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="6ad81-103">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="6ad81-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="6ad81-104">Prima di eseguire la procedura descritta in questo articolo, verificare di aver letto il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) ed è stata completata la procedura descritta in [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6ad81-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="6ad81-105">Questo articolo descrive come abilitare il routing basato sulla posizione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="6ad81-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="6ad81-106">Dopo aver distribuito il routing diretto del sistema telefonico e configurato le aree geografiche, i siti e le subnet della rete, è possibile abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6ad81-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="6ad81-107">Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ad81-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="6ad81-108">Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6ad81-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="6ad81-109">È necessario abilitare il routing basato sulla posizione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad81-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="6ad81-110">Utenti</span><span class="sxs-lookup"><span data-stu-id="6ad81-110">Users</span></span>
- <span data-ttu-id="6ad81-111">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="6ad81-111">Network sites</span></span>
- <span data-ttu-id="6ad81-112">Configurazioni gateway</span><span class="sxs-lookup"><span data-stu-id="6ad81-112">Gateway configurations</span></span>
- <span data-ttu-id="6ad81-113">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="6ad81-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="6ad81-114">Abilitare il routing basato sulla posizione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="6ad81-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="6ad81-115">Usa il cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare gli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="6ad81-116">Per più usi, separare ogni utilizzo con una virgola.</span><span class="sxs-lookup"><span data-stu-id="6ad81-116">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="6ad81-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ad81-117">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="6ad81-118">Usa il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli usi appropriati della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="6ad81-119">Quando si assegnano gli usi PSTN a un criterio di routing vocale, verificare di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ad81-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="6ad81-120">Usare gli utilizzi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito</span><span class="sxs-lookup"><span data-stu-id="6ad81-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="6ad81-121">USA gli usi PSTN associati alle route vocali che usano un gateway PSTN situato in un'area geografica in cui le restrizioni di routing basate sulla posizione non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="6ad81-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="6ad81-122">In questo esempio creiamo due nuovi criteri di routing vocale e li assegniamo agli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="6ad81-123">Nella tabella seguente sono illustrati i criteri di routing vocale definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6ad81-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="6ad81-124">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="6ad81-124">Voice routing policy 1</span></span>|<span data-ttu-id="6ad81-125">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="6ad81-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="6ad81-126">ID criterio vocale online</span><span class="sxs-lookup"><span data-stu-id="6ad81-126">Online voice policy ID</span></span>   |<span data-ttu-id="6ad81-127">Politica di routing vocale Delhi online</span><span class="sxs-lookup"><span data-stu-id="6ad81-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="6ad81-128">Criteri di routing vocale di Hyderabad online</span><span class="sxs-lookup"><span data-stu-id="6ad81-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="6ad81-129">Usi PSTN online</span><span class="sxs-lookup"><span data-stu-id="6ad81-129">Online PSTN usages</span></span>  |<span data-ttu-id="6ad81-130">Lunga distanza</span><span class="sxs-lookup"><span data-stu-id="6ad81-130">Long Distance</span></span>  |<span data-ttu-id="6ad81-131">Lunga distanza, locale, interno</span><span class="sxs-lookup"><span data-stu-id="6ad81-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="6ad81-132">Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono restrizioni di routing per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6ad81-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="6ad81-133">Abilitare il routing basato sulla posizione per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="6ad81-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="6ad81-134">Usa il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="6ad81-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="6ad81-135">In questo esempio, consentiamo il routing basato sulla posizione per il sito Delhi e il sito Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="6ad81-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="6ad81-136">La tabella seguente mostra i siti abilitati per il routing basato sulla posizione in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6ad81-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="6ad81-137">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6ad81-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="6ad81-138">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6ad81-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="6ad81-139">Nome sito</span><span class="sxs-lookup"><span data-stu-id="6ad81-139">Site name</span></span>    |<span data-ttu-id="6ad81-140">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6ad81-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="6ad81-141">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6ad81-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="6ad81-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="6ad81-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="6ad81-143">True</span><span class="sxs-lookup"><span data-stu-id="6ad81-143">True</span></span>    |<span data-ttu-id="6ad81-144">True</span><span class="sxs-lookup"><span data-stu-id="6ad81-144">True</span></span>    |
    |<span data-ttu-id="6ad81-145">Subnet</span><span class="sxs-lookup"><span data-stu-id="6ad81-145">Subnets</span></span>     |<span data-ttu-id="6ad81-146">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6ad81-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="6ad81-147">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6ad81-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="6ad81-148">Abilitare il routing basato sulla posizione per i gateway</span><span class="sxs-lookup"><span data-stu-id="6ad81-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="6ad81-149">Usa il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni sito di gateway o di rete.</span><span class="sxs-lookup"><span data-stu-id="6ad81-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="6ad81-150">Se più gateway sono associati a un sistema, ad esempio gateway o PBX, modifica ogni gateway per abilitare le restrizioni di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6ad81-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="6ad81-151">In questo esempio creiamo una configurazione di gateway per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="6ad81-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="6ad81-152">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="6ad81-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="6ad81-153">Usa il cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing basato sulla posizione per i gateway che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="6ad81-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="6ad81-154">Abilitare il routing basato sulla posizione ai gateway che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="6ad81-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="6ad81-155">In questo esempio, consentiamo il routing basato sulla posizione per ogni gateway associato ai gateway PSTN nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="6ad81-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="6ad81-156">Non abilitare il routing basato sulla posizione per i gateway che non instradano le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="6ad81-157">Tuttavia, devi comunque associare il gateway al sito di rete in cui si trova il sistema.</span><span class="sxs-lookup"><span data-stu-id="6ad81-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="6ad81-158">Questo perché le restrizioni di routing basate sul percorso devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="6ad81-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="6ad81-159">In questo esempio, il routing basato sulla posizione non è abilitato per ogni gateway associato ai sistemi PBX nei siti di Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="6ad81-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="6ad81-160">Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ad esempio, un PBX) avranno restrizioni simili agli endpoint degli utenti di teams abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6ad81-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="6ad81-161">Ciò significa che questi utenti possono effettuare e ricevere chiamate da e verso utenti di teams indipendentemente dalla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ad81-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="6ad81-162">Possono anche effettuare e ricevere chiamate da e verso altri sistemi che non instradano le chiamate alla rete PSTN, ad esempio un endpoint connesso a un PBX diverso, indipendentemente dal sito di rete a cui è associato il sistema.</span><span class="sxs-lookup"><span data-stu-id="6ad81-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="6ad81-163">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti delle chiamate e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti a imposte di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6ad81-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="6ad81-164">Queste chiamate devono usare solo gateway PSTN definiti come locali per tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="6ad81-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="6ad81-165">La tabella seguente mostra la configurazione del gateway di quattro gateway in due diversi siti di rete: due collegati a gateway PSTN e due collegati a sistemi PBX.</span><span class="sxs-lookup"><span data-stu-id="6ad81-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="6ad81-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="6ad81-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="6ad81-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="6ad81-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="6ad81-168">PstnGateway: Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6ad81-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="6ad81-169">True</span><span class="sxs-lookup"><span data-stu-id="6ad81-169">True</span></span>     |   <span data-ttu-id="6ad81-170">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6ad81-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="6ad81-171">PstnGateway: Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6ad81-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="6ad81-172">True</span><span class="sxs-lookup"><span data-stu-id="6ad81-172">True</span></span>      |      <span data-ttu-id="6ad81-173">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6ad81-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="6ad81-174">PstnGateway: Gateway 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6ad81-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="6ad81-175">False</span><span class="sxs-lookup"><span data-stu-id="6ad81-175">False</span></span>     |     <span data-ttu-id="6ad81-176">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6ad81-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="6ad81-177">PstnGateway: Gateway 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="6ad81-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="6ad81-178">False</span><span class="sxs-lookup"><span data-stu-id="6ad81-178">False</span></span>     |    <span data-ttu-id="6ad81-179">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6ad81-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="6ad81-180">Abilitare il routing basato sulla posizione per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="6ad81-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="6ad81-181">Per applicare il routing basato sulla posizione per gli utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione dei pedaggi di PTSN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="6ad81-182">Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare il routing basato sulla posizione impedendo l'esclusione di pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ad81-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="6ad81-183">In questo esempio viene impedito l'esclusione del pedaggio PSTN ai criteri di chiamata di Utente1.</span><span class="sxs-lookup"><span data-stu-id="6ad81-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a><span data-ttu-id="6ad81-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6ad81-184">Related topics</span></span>

- [<span data-ttu-id="6ad81-185">Impostazioni di rete per le funzionalità vocali di cloud in teams</span><span class="sxs-lookup"><span data-stu-id="6ad81-185">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
