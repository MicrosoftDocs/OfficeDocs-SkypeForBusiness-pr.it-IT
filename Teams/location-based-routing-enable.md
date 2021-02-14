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
description: Informazioni su come abilitare il routing Location-Based per il routing diretto, incluso l'abilitazione per utenti, siti di rete, configurazioni di gateway e criteri di chiamata.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822916"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="50163-103">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="50163-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="50163-104">Prima di eseguire i passaggi descritti in questo articolo, assicurarsi di aver letto Pianificare il [routing Location-Based](location-based-routing-plan.md) per il routing diretto e di aver completato la procedura descritta in Configurare le impostazioni di rete per il [routing Location-Based.](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="50163-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="50163-105">Questo articolo descrive come abilitare il routing Location-Based per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="50163-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="50163-106">Dopo aver distribuito l'instradamento diretto del sistema telefonico e aver configurato le aree geografiche, i siti e le subnet di rete, sei pronto per abilitare il routing Location-Based rete.</span><span class="sxs-lookup"><span data-stu-id="50163-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="50163-107">Per completare i passaggi descritti in questo articolo, è necessaria una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50163-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="50163-108">Per altre informazioni, vedere [Panoramica di Teams su PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="50163-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="50163-109">È necessario abilitare il routing Location-Based per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50163-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="50163-110">Utenti</span><span class="sxs-lookup"><span data-stu-id="50163-110">Users</span></span>
- <span data-ttu-id="50163-111">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="50163-111">Network sites</span></span>
- <span data-ttu-id="50163-112">Configurazioni di gateway</span><span class="sxs-lookup"><span data-stu-id="50163-112">Gateway configurations</span></span>
- <span data-ttu-id="50163-113">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="50163-113">Calling policies</span></span>

<span data-ttu-id="50163-114">È possibile usare [l'interfaccia di amministrazione di Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l per abilitare Location-Based distribuzione.</span><span class="sxs-lookup"><span data-stu-id="50163-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="50163-115">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="50163-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="50163-116">Abilitare il Location-Based distribuzione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="50163-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="50163-117">Creare criteri di routing vocale e assegnare utilizzi PSTN al criterio.</span><span class="sxs-lookup"><span data-stu-id="50163-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="50163-118">Quando si assegnano utilizzi PSTN a un criterio, assicurarsi di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50163-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="50163-119">Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN locale nel sito.</span><span class="sxs-lookup"><span data-stu-id="50163-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="50163-120">Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN situato in un'area geografica Location-Based non sono necessarie limitazioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="50163-121">Assegnare il criterio di routing vocale agli utenti che richiedono l'applicazione di restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="50163-122">Per altre informazioni su come creare criteri di routing vocale e assegnarli agli utenti, vedere Gestire i criteri [di routing vocale in Microsoft Teams.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="50163-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="50163-123">Abilitare il routing Location-Based per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="50163-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="50163-124">Abilitare Location-Based routing dei siti che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="50163-125">A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a Topologia rete posizioni, selezionare un sito di rete, fare clic su Modifica e quindi attivare il routing basato sulla  >   **posizione.** </span><span class="sxs-lookup"><span data-stu-id="50163-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="50163-126">Per altre informazioni, vedere [Gestire la topologia della rete.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="50163-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="50163-127">Abilitare Location-Based per i gateway</span><span class="sxs-lookup"><span data-stu-id="50163-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="50163-128">Abilitare Location-Based routing ai gateway che instradino le chiamate a gateway PSTN che instradino le chiamate alla rete PSTN e associno il sito di rete in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="50163-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="50163-129">Nella barra di spostamento sinistra passare a **Voice** Direct Routing e quindi fare  >  clic sulla **scheda SBCs.**</span><span class="sxs-lookup"><span data-stu-id="50163-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="50163-130">Selezionare l'oggetto SBC e quindi fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="50163-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="50163-131">In **Routing basato sulla posizione e ottimizzazione multimediale** attivare Abilita routing basato sulla **posizione.**</span><span class="sxs-lookup"><span data-stu-id="50163-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="50163-132">Specificare l'ID del sito del gateway e quindi impostare la modalità bypass.</span><span class="sxs-lookup"><span data-stu-id="50163-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="50163-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="50163-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="50163-134">Abilitare il routing Location-Based chiamate per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="50163-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="50163-135">Per applicare Location-Based routing dei messaggi a utenti specifici, configurare il criterio di chiamata dell'utente per evitare il bypass a numero verde PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="50163-136">A tale scopo, attivare **l'impostazione Impedisci il bypass** a numero verde nel criterio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="50163-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="50163-137">Per ulteriori informazioni, consulta [Criteri per le chiamate in Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="50163-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="50163-138">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="50163-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="50163-139">Abilitare il Location-Based distribuzione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="50163-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="50163-140">Usa il [cmdlet Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) per impostare l'utilizzo di PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="50163-141">Per più utilizzi, separare ogni utilizzo con una virgola.</span><span class="sxs-lookup"><span data-stu-id="50163-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="50163-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50163-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="50163-143">Usare il cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) per creare un criterio di routing vocale per associare l'utente agli utilizzi appropriati di PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="50163-144">Quando si assegnano utilizzi PSTN a un criterio di routing vocale, assicurarsi di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50163-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="50163-145">Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN locale per il sito</span><span class="sxs-lookup"><span data-stu-id="50163-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="50163-146">Usare gli utilizzi PSTN associati ai percorsi vocali che usano un gateway PSTN situato in un'area geografica Location-Based non sono necessarie limitazioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="50163-147">In questo esempio vengono creati due nuovi criteri di routing vocale a cui vengono assegnati utilizzi di PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="50163-148">La tabella seguente mostra i criteri di routing vocale definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="50163-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="50163-149">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="50163-149">Voice routing policy 1</span></span>|<span data-ttu-id="50163-150">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="50163-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="50163-151">ID criteri vocali online</span><span class="sxs-lookup"><span data-stu-id="50163-151">Online voice policy ID</span></span>   |<span data-ttu-id="50163-152">Criteri di routing vocale online di Delhi</span><span class="sxs-lookup"><span data-stu-id="50163-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="50163-153">Criteri per l'instradamento vocale online di enorabad</span><span class="sxs-lookup"><span data-stu-id="50163-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="50163-154">Utilizzi di PSTN online</span><span class="sxs-lookup"><span data-stu-id="50163-154">Online PSTN usages</span></span>  |<span data-ttu-id="50163-155">Long Distance</span><span class="sxs-lookup"><span data-stu-id="50163-155">Long Distance</span></span>  |<span data-ttu-id="50163-156">Long Distance, Local, Internal</span><span class="sxs-lookup"><span data-stu-id="50163-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="50163-157">Usare il cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) per associare i criteri di routing vocale online agli utenti che richiedono l'applicazione di restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="50163-158">Abilitare il routing Location-Based per i siti di rete</span><span class="sxs-lookup"><span data-stu-id="50163-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="50163-159">Usare il cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) per abilitare il routing Location-Based e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="50163-160">In questo esempio viene abilitato il routing Location-Based per il sito di Delhi e per il sito di Arabad.</span><span class="sxs-lookup"><span data-stu-id="50163-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="50163-161">La tabella seguente mostra i siti abilitati per il routing Location-Based distribuzione in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="50163-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="50163-162">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="50163-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="50163-163">Sito 2 (Arabad)</span><span class="sxs-lookup"><span data-stu-id="50163-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="50163-164">Nome sito</span><span class="sxs-lookup"><span data-stu-id="50163-164">Site name</span></span>    |<span data-ttu-id="50163-165">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="50163-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="50163-166">Sito 2 (Arabad)</span><span class="sxs-lookup"><span data-stu-id="50163-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="50163-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="50163-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="50163-168">Vero</span><span class="sxs-lookup"><span data-stu-id="50163-168">True</span></span>    |<span data-ttu-id="50163-169">Vero</span><span class="sxs-lookup"><span data-stu-id="50163-169">True</span></span>    |
    |<span data-ttu-id="50163-170">Subnet</span><span class="sxs-lookup"><span data-stu-id="50163-170">Subnets</span></span>     |<span data-ttu-id="50163-171">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="50163-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="50163-172">Subnet 2 (Arabad)</span><span class="sxs-lookup"><span data-stu-id="50163-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="50163-173">Abilitare Location-Based per i gateway</span><span class="sxs-lookup"><span data-stu-id="50163-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="50163-174">Usare il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) per creare una configurazione del gateway per ogni gateway o sito di rete.</span><span class="sxs-lookup"><span data-stu-id="50163-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="50163-175">Se a un sistema sono associati più gateway, ad esempio Gateway o PBX, modificare ogni gateway per abilitare Location-Based di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="50163-176">In questo esempio viene creata una configurazione del gateway per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="50163-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="50163-177">Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="50163-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="50163-178">Usare il cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) per abilitare il routing Location-Based per i gateway che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="50163-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="50163-179">Abilitare Location-Based routing ai gateway che instradino le chiamate a gateway PSTN che instradino le chiamate alla rete PSTN e associno il sito di rete in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="50163-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="50163-180">In questo esempio viene abilitato il routing Location-Based per ogni gateway associato ai gateway PSTN nei siti di Delhi e Delrabad.</span><span class="sxs-lookup"><span data-stu-id="50163-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="50163-181">Non abilitare il routing Location-Based per i gateway che non instradno le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="50163-182">Tuttavia, è comunque necessario associare il gateway al sito di rete in cui si trova il sistema.</span><span class="sxs-lookup"><span data-stu-id="50163-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="50163-183">Questo è dovuto Location-Based che sia necessario applicare restrizioni di routing per le chiamate PSTN che raggiungono gli endpoint connessi tramite questo gateway.</span><span class="sxs-lookup"><span data-stu-id="50163-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="50163-184">In questo esempio, Location-Based routing non è abilitato per ogni gateway associato ai sistemi PBX nei siti del Delhi e di Pbxrabad.</span><span class="sxs-lookup"><span data-stu-id="50163-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="50163-185">Abilitare il routing Location-Based chiamate per i criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="50163-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="50163-186">Per applicare Location-Based routing a utenti specifici, configurare i criteri vocali degli utenti in modo da evitare il bypass a pedaggio PTSN.</span><span class="sxs-lookup"><span data-stu-id="50163-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="50163-187">Usare il cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) per abilitare Location-Based routing evitando il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="50163-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="50163-188">In questo esempio evitiamo il bypass a numero verde PSTN per i criteri di chiamata dell'Utente1.</span><span class="sxs-lookup"><span data-stu-id="50163-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="50163-189">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="50163-189">Related topics</span></span>

- [<span data-ttu-id="50163-190">Impostazioni di rete per le funzionalità vocali cloud in Teams</span><span class="sxs-lookup"><span data-stu-id="50163-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
