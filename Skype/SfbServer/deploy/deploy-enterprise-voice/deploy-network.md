---
title: Distribuire aree di rete, siti e subnet in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server. Tutti questi elementi vengono usati per le funzionalità vocali avanzate di Enterprise: bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione.'
ms.openlocfilehash: e181e8fffc431db67e0e597f3e8dccba710efdd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767519"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="8af7d-104">Distribuire aree di rete, siti e subnet in Skype for business</span><span class="sxs-lookup"><span data-stu-id="8af7d-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="8af7d-105">Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="8af7d-106">Tutti questi elementi vengono usati per le funzionalità vocali avanzate di Enterprise: bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8af7d-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="8af7d-107">Le funzionalità vocali avanzate per l'organizzazione sono [controllo di ammissione delle chiamate](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [bypass multimediale](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [routing basato sulla posizione](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)e [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="8af7d-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="8af7d-108">Queste funzionalità richiedono tutte la creazione di aree di rete, siti di rete e subnet.</span><span class="sxs-lookup"><span data-stu-id="8af7d-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="8af7d-109">Ad esempio, tutte queste funzionalità richiedono che ogni subnet della topologia sia associata a un sito di rete specifico e ogni sito di rete debba essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="8af7d-110">Per altre informazioni su questi termini, vedere [impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="8af7d-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="8af7d-111">Il controllo di ammissione alle chiamate e il E9-1-1 hanno requisiti di configurazione aggiuntivi per i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="8af7d-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="8af7d-112">Il controllo di ammissione alle chiamate richiede che venga specificato un profilo dei criteri di larghezza di banda per ogni sito vincolato dalle limitazioni della larghezza di banda WAN.</span><span class="sxs-lookup"><span data-stu-id="8af7d-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="8af7d-113">Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario [creare profili dei criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md) prima di configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="8af7d-114">E9-1-1 richiede l'impostazione di un criterio di posizione per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8af7d-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="8af7d-115">Se si prevede di distribuire E9-1-1, è necessario [creare criteri di posizione in Skype for Business Server prima di](create-location-policies.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="8af7d-116">Creare o modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="8af7d-116">Create or modify a Network Region</span></span>

<span data-ttu-id="8af7d-117">Se sono già state create aree di rete per una di queste funzionalità, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="8af7d-118">Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="8af7d-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="8af7d-119">Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="8af7d-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8af7d-120">Per creare un'area di rete con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8af7d-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8af7d-121">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8af7d-122">Eseguire il cmdlet New-CsNetworkRegion per creare aree di rete:</span><span class="sxs-lookup"><span data-stu-id="8af7d-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="8af7d-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="8af7d-124">In questo esempio è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito di CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="8af7d-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="8af7d-125">Per completare la creazione di aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8af7d-126">Per creare un'area di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8af7d-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8af7d-127">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8af7d-128">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="8af7d-129">Fare clic su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-129">Click **Region**.</span></span>

4. <span data-ttu-id="8af7d-130">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-130">Click **New**.</span></span>

5. <span data-ttu-id="8af7d-131">Nella pagina **nuova area** fare clic su **nome** e quindi digitare un nome per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="8af7d-132">Fare clic su **sito centrale**e quindi su un sito centrale nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8af7d-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="8af7d-133">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="8af7d-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-134">Click **Commit**.</span></span>

9. <span data-ttu-id="8af7d-135">Per completare la creazione di aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8af7d-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8af7d-136">Per modificare un'area di rete con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8af7d-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8af7d-137">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8af7d-138">Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:</span><span class="sxs-lookup"><span data-stu-id="8af7d-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="8af7d-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="8af7d-140">In questo esempio è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata usando le procedure descritte più indietro in questo argomento) modificando la descrizione.</span><span class="sxs-lookup"><span data-stu-id="8af7d-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="8af7d-141">Se esiste una descrizione per l'area "NorthAmerica", questo comando lo sovrascrive con questo valore; Se non è stata impostata alcuna descrizione, questo comando lo imposta.</span><span class="sxs-lookup"><span data-stu-id="8af7d-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="8af7d-142">Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8af7d-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8af7d-143">Per modificare un'area di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8af7d-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8af7d-144">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8af7d-145">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="8af7d-146">Fare clic sul pulsante di spostamento dell' **area geografica** .</span><span class="sxs-lookup"><span data-stu-id="8af7d-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="8af7d-147">Nella tabella fare clic sull'area di rete che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="8af7d-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="8af7d-148">Fare clic su **modifica**e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="8af7d-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="8af7d-149">Nella pagina **Edit Region** modificare i valori delle impostazioni dell'area di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8af7d-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="8af7d-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-150">Click **Commit**.</span></span>

8. <span data-ttu-id="8af7d-151">Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8af7d-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="8af7d-152">Creare o modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="8af7d-152">Create or modify a network site</span></span>

<span data-ttu-id="8af7d-153">Se sono già stati creati siti di rete per una di queste funzionalità, non è necessario creare nuovi siti di rete. altre funzionalità vocali avanzate di Enterprise useranno gli stessi siti di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="8af7d-154">Può tuttavia essere necessario modificare una definizione di sito di rete esistente per applicare impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="8af7d-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="8af7d-155">Se ad esempio è stato creato un sito di rete per E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione delle chiamate per applicare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="8af7d-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8af7d-156">Per creare un sito di rete usando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8af7d-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8af7d-157">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8af7d-158">Eseguire il cmdlet New-CsNetworkSite per creare siti di rete:</span><span class="sxs-lookup"><span data-stu-id="8af7d-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="8af7d-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="8af7d-160">In questo esempio è stato creato un sito di rete denominato "Chicago" che si trova nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="8af7d-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8af7d-161">L'area di rete NorthAmerica deve esistere già affinché il comando venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8af7d-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="8af7d-162">Per completare la creazione di siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="8af7d-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8af7d-163">Per creare un sito di rete usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8af7d-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8af7d-164">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8af7d-165">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="8af7d-166">Fare clic sul pulsante di spostamento del **sito** .</span><span class="sxs-lookup"><span data-stu-id="8af7d-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="8af7d-167">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-167">Click **New**.</span></span>

5. <span data-ttu-id="8af7d-168">Nella pagina **nuovo sito** fare clic su **nome** e quindi digitare un nome per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="8af7d-169">Fare clic su **area geografica**e quindi fare clic su un'area nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8af7d-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="8af7d-170">Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi fare clic su un criterio di larghezza di banda nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8af7d-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8af7d-171">I criteri di larghezza di banda sono necessari solo se si distribuisce il controllo di ammissione delle chiamate nel sito.</span><span class="sxs-lookup"><span data-stu-id="8af7d-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="8af7d-172">Facoltativamente, fare clic su **criteri posizione**e quindi fare clic su un criterio di posizione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8af7d-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8af7d-173">I criteri di posizione sono necessari solo se si distribuisce E9-1-1 nel sito.</span><span class="sxs-lookup"><span data-stu-id="8af7d-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="8af7d-174">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="8af7d-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-175">Click **Commit**.</span></span>

11. <span data-ttu-id="8af7d-176">Per completare la creazione di siti di rete per la topologia, ripetere i passaggi da 4 a 10 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="8af7d-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8af7d-177">Per modificare un sito di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8af7d-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8af7d-178">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8af7d-179">Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="8af7d-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="8af7d-180">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="8af7d-181">In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="8af7d-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="8af7d-182">Per modificare la configurazione del sito di rete per distribuire il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="8af7d-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8af7d-183">Anche se il parametro BypassID esiste per il bypass multimediale, ti consigliamo vivamente di non eseguire l'override degli ID di bypass generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8af7d-183">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="8af7d-184">Non è necessario specificare parametri aggiuntivi per configurare un sito di rete per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="8af7d-184">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="8af7d-185">Per completare la modifica dei siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="8af7d-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8af7d-186">Per modificare un sito di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8af7d-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8af7d-187">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8af7d-188">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="8af7d-189">Fare clic sul pulsante di spostamento del **sito** .</span><span class="sxs-lookup"><span data-stu-id="8af7d-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="8af7d-190">Nella tabella fare clic sul sito di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="8af7d-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="8af7d-191">Fare clic su **modifica**e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="8af7d-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="8af7d-192">Nella pagina **modifica sito** modificare i valori delle impostazioni del sito di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8af7d-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="8af7d-193">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-193">Click **Commit**.</span></span>

8. <span data-ttu-id="8af7d-194">Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="8af7d-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="8af7d-195">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="8af7d-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="8af7d-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="8af7d-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="8af7d-197">Ogni subnet della rete deve essere associata a un sito di rete specifico, poiché le informazioni di subnet vengono usate per determinare il sito di rete in cui si trova un endpoint mentre viene avviata una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="8af7d-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="8af7d-198">Quando si conosce la posizione di ogni parte di una sessione, le funzionalità vocali avanzate di Enterprise possono applicare tali informazioni per determinare come gestire la configurazione o il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="8af7d-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="8af7d-199">Tutti gli indirizzi IP pubblici configurati per i server Edge audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="8af7d-200">Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32.</span><span class="sxs-lookup"><span data-stu-id="8af7d-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="8af7d-201">Il sito di rete associato deve corrispondere al sito di rete configurato appropriato.</span><span class="sxs-lookup"><span data-stu-id="8af7d-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="8af7d-202">Ad esempio, l'indirizzo IP pubblico che corrisponde al servizio a/V Edge nel sito centrale di Chicago sarebbe NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="8af7d-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8af7d-203">Per associare una subnet a un sito di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8af7d-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8af7d-204">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8af7d-205">Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:</span><span class="sxs-lookup"><span data-stu-id="8af7d-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="8af7d-206">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="8af7d-207">In questo esempio è stata creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".</span><span class="sxs-lookup"><span data-stu-id="8af7d-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="8af7d-208">Ripetere il passaggio 2 per tutte le subnet della topologia.</span><span class="sxs-lookup"><span data-stu-id="8af7d-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="8af7d-209">Per associare subnet a siti di rete mediante l'importazione di un file CSV</span><span class="sxs-lookup"><span data-stu-id="8af7d-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="8af7d-210">Creare un file CSV che includa tutte le subnet che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="8af7d-210">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="8af7d-211">Ad esempio, crea un file denominato **subnet. csv** con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="8af7d-211">For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="8af7d-212">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="8af7d-213">Eseguire il cmdlet seguente per importare **subnet. csv**e quindi archiviarne il contenuto in Lync Server Management store:</span><span class="sxs-lookup"><span data-stu-id="8af7d-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8af7d-214">Per associare una subnet a un sito di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8af7d-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8af7d-215">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8af7d-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8af7d-216">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="8af7d-217">Fare clic sul pulsante di spostamento **subnet** .</span><span class="sxs-lookup"><span data-stu-id="8af7d-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="8af7d-218">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-218">Click **New**.</span></span>

5. <span data-ttu-id="8af7d-219">Nella pagina **nuova subnet** fare clic su **ID Subnet**e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si vuole associare a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="8af7d-220">Fare clic su **maschera**e quindi digitare la maschera di forma da applicare alla subnet.</span><span class="sxs-lookup"><span data-stu-id="8af7d-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="8af7d-221">Fare clic su **ID sito di rete**e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.</span><span class="sxs-lookup"><span data-stu-id="8af7d-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8af7d-222">Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="8af7d-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="8af7d-223">Per informazioni dettagliate sulla procedura, vedere [creare o modificare un sito di rete](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="8af7d-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="8af7d-224">È anche possibile recuperare gli ID sito per la distribuzione eseguendo il cmdlet **Get-CsNetworkSite** .</span><span class="sxs-lookup"><span data-stu-id="8af7d-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="8af7d-225">Per informazioni dettagliate, vedi la documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8af7d-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="8af7d-226">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere la subnet.</span><span class="sxs-lookup"><span data-stu-id="8af7d-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="8af7d-227">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8af7d-227">Click **Commit**.</span></span>

<span data-ttu-id="8af7d-228">Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="8af7d-229">Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="8af7d-230">Questo avviso non verrà generato più di una volta all'interno di un periodo di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="8af7d-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="8af7d-231">Di seguito sono riportate le informazioni relative agli avvisi e un esempio:</span><span class="sxs-lookup"><span data-stu-id="8af7d-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="8af7d-232">**Origine**: CS Bandwidth Policy Service (Core)</span><span class="sxs-lookup"><span data-stu-id="8af7d-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="8af7d-233">**Numero evento**: 36034</span><span class="sxs-lookup"><span data-stu-id="8af7d-233">**Event number**: 36034</span></span>

 <span data-ttu-id="8af7d-234">**Livello**: 2</span><span class="sxs-lookup"><span data-stu-id="8af7d-234">**Level**: 2</span></span>

 <span data-ttu-id="8af7d-235">**Descrizione**: le subnet per gli indirizzi IP seguenti: \<l'elenco di indirizzi\> IP non è configurato o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="8af7d-236">**Causa**: le subnet per gli indirizzi IP corrispondenti mancano alle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="8af7d-237">**Risoluzione**: aggiungere subnet che corrispondono all'elenco di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="8af7d-238">Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-238">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="8af7d-239">Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue:</span><span class="sxs-lookup"><span data-stu-id="8af7d-239">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="8af7d-240">Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="8af7d-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="8af7d-241">Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="8af7d-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="8af7d-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af7d-242">See also</span></span>
<span data-ttu-id="8af7d-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="8af7d-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="8af7d-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8af7d-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="8af7d-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8af7d-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="8af7d-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8af7d-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="8af7d-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8af7d-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="8af7d-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8af7d-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="8af7d-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8af7d-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="8af7d-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8af7d-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="8af7d-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8af7d-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

