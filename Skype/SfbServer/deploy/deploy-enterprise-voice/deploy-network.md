---
title: Distribuire aree di rete, siti e subnet in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Creare o modificare aree di rete, siti di rete e associare le subnet di rete in Skype for Business Server. Tutti questi sono utilizzati per le funzionalità di VoIP aziendale avanzate: bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione.'
ms.openlocfilehash: 408715cb1baa31e1fe864827a2b2a14d8e4788c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812436"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="f1613-104">Distribuire aree di rete, siti e subnet in Skype for business</span><span class="sxs-lookup"><span data-stu-id="f1613-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="f1613-105">Creare o modificare aree di rete, siti di rete e associare le subnet di rete in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="f1613-106">Tutti questi sono utilizzati per le funzionalità di VoIP aziendale avanzate: bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f1613-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="f1613-107">Le funzionalità avanzate di VoIP aziendale [sono controllo di ammissione di chiamata](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [bypass multimediale](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [routing basato sulla posizione](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)e [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1613-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="f1613-108">Tutte queste funzionalità richiedono la creazione di aree di rete, siti di rete e subnet.</span><span class="sxs-lookup"><span data-stu-id="f1613-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="f1613-109">Ad esempio, tutte queste funzionalità richiedono che ogni subnet della topologia sia associata a un sito di rete specifico e che ogni sito di rete sia associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="f1613-110">Per ulteriori informazioni su questi termini, vedere [impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="f1613-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="f1613-111">Per il controllo di ammissione di chiamata e il servizio E9-1-1 sono previsti ulteriori requisiti di configurazione per i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="f1613-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="f1613-112">Per il controllo di ammissione di chiamata è necessario specificare un profilo di criteri di larghezza di banda per ogni sito vincolato da limitazioni della larghezza di banda WAN.</span><span class="sxs-lookup"><span data-stu-id="f1613-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="f1613-113">Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario [creare profili di criteri di larghezza di banda in Skype for Business Server prima di](create-bandwidth-policy-profiles.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="f1613-114">Per il servizio E9-1-1 è necessario specificare criteri di percorso per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="f1613-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="f1613-115">Se si prevede di distribuire il servizio E9-1-1, è necessario [creare criteri percorso in Skype for Business Server prima di](create-location-policies.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="f1613-116">Creare o modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="f1613-116">Create or modify a Network Region</span></span>

<span data-ttu-id="f1613-117">Se sono già state create aree di rete per una di queste funzionalità, non è necessario creare nuove aree di rete. altre funzionalità di VoIP aziendale avanzate utilizzeranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="f1613-118">Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="f1613-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f1613-119">Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="f1613-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f1613-120">Per creare un'area di rete con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1613-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f1613-121">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1613-122">Eseguire il cmdlet New-CsNetworkRegion per creare le aree di rete:</span><span class="sxs-lookup"><span data-stu-id="f1613-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="f1613-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1613-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="f1613-124">In questo esempio, è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito di CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="f1613-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="f1613-125">Per completare la creazione delle aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f1613-126">Per creare un'area di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1613-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f1613-127">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f1613-128">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f1613-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="f1613-129">Fare clic su **Area**.</span><span class="sxs-lookup"><span data-stu-id="f1613-129">Click **Region**.</span></span>

4. <span data-ttu-id="f1613-130">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1613-130">Click **New**.</span></span>

5. <span data-ttu-id="f1613-131">Nella pagina **Nuova area** fare clic su **Nome** e quindi digitare un nome per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="f1613-132">Fare clic su **Sito centrale** e quindi fare clic su un sito centrale nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1613-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="f1613-133">Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="f1613-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1613-134">Click **Commit**.</span></span>

9. <span data-ttu-id="f1613-135">Per completare la creazione delle aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="f1613-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f1613-136">Per modificare un'area di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1613-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f1613-137">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1613-138">Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:</span><span class="sxs-lookup"><span data-stu-id="f1613-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="f1613-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1613-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="f1613-140">In questo esempio, è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata utilizzando le procedure descritte in precedenza in questo argomento) modificando la descrizione.</span><span class="sxs-lookup"><span data-stu-id="f1613-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="f1613-141">Se esiste una descrizione per l'area "NorthAmerica", il comando lo sovrascrive con questo valore. Se non è stata impostata alcuna descrizione, questo comando lo imposta.</span><span class="sxs-lookup"><span data-stu-id="f1613-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="f1613-142">Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="f1613-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f1613-143">Per modificare un'area di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1613-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f1613-144">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f1613-145">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f1613-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="f1613-146">Fare clic sul pulsante di spostamento **Area**.</span><span class="sxs-lookup"><span data-stu-id="f1613-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="f1613-147">Nella tabella fare clic sull'area di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f1613-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="f1613-148">Fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1613-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="f1613-149">Nella pagina **modifica area** modificare i valori per le impostazioni dell'area di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f1613-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="f1613-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1613-150">Click **Commit**.</span></span>

8. <span data-ttu-id="f1613-151">Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="f1613-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="f1613-152">Creare o modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f1613-152">Create or modify a network site</span></span>

<span data-ttu-id="f1613-153">Se sono già stati creati siti di rete per una di queste funzionalità, non è necessario creare nuovi siti di rete. altre funzionalità di VoIP aziendale avanzate utilizzeranno gli stessi siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="f1613-154">Tuttavia, è possibile modificare una definizione di sito di rete esistente per applicare le impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="f1613-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="f1613-155">Ad esempio, se è stato creato un sito di rete per il servizio E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione di chiamata per applicare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f1613-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f1613-156">Per creare un sito di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1613-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f1613-157">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1613-158">Eseguire il cmdlet New-CsNetworkSite per creare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="f1613-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="f1613-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1613-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="f1613-160">In questo esempio, è stato creato un sito di rete denominato "Chicago" nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="f1613-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1613-161">Per il corretto funzionamento di questo comando, l'area di rete NorthAmerica deve esistere già.</span><span class="sxs-lookup"><span data-stu-id="f1613-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="f1613-162">Per completare la creazione dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="f1613-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f1613-163">Per creare un sito di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1613-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f1613-164">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f1613-165">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f1613-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="f1613-166">Fare clic sul pulsante di spostamento **Sito**.</span><span class="sxs-lookup"><span data-stu-id="f1613-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="f1613-167">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1613-167">Click **New**.</span></span>

5. <span data-ttu-id="f1613-168">Nella pagina **Nuovo sito** fare clic su **Nome** e quindi digitare un nome per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="f1613-169">Fare clic su **Area** e quindi selezionare un'area nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1613-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="f1613-170">Facoltativamente, fare clic su **Criteri larghezza di banda** e quindi selezionare un criterio larghezza di banda nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1613-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1613-171">Il criterio larghezza di banda è necessario solo se nel sito viene distribuito il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1613-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="f1613-172">Facoltativamente, fare clic su **Criteri percorso** e quindi selezionare un criterio percorso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1613-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1613-173">Il criterio percorso è necessario solo se nel sito viene distribuito il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f1613-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="f1613-174">Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="f1613-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1613-175">Click **Commit**.</span></span>

11. <span data-ttu-id="f1613-176">Per completare la creazione dei siti di rete per la propria topologia, ripetere i passaggi da 4 a 10 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="f1613-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f1613-177">Per modificare un sito di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1613-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f1613-178">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1613-179">Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="f1613-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="f1613-180">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1613-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="f1613-181">In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="f1613-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="f1613-182">Per modificare la configurazione del sito di rete in modo da distribuire il controllo di ammissione di chiamata, il servizio E9-1-1 o il bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="f1613-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1613-p110">Anche se per il bypass multimediale esiste il parametro BypassID, è consigliabile non sostituire gli ID bypass generati automaticamente. Non è necessario specificare ulteriori parametri per configurare un sito di rete per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="f1613-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="f1613-185">Per completare la modifica dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="f1613-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f1613-186">Per modificare un sito di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1613-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f1613-187">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f1613-188">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f1613-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="f1613-189">Fare clic sul pulsante di spostamento **Sito**.</span><span class="sxs-lookup"><span data-stu-id="f1613-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="f1613-190">Nella tabella fare clic sul sito di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f1613-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="f1613-191">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f1613-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="f1613-192">Nella pagina **modifica sito** modificare i valori per le impostazioni del sito di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f1613-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="f1613-193">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1613-193">Click **Commit**.</span></span>

8. <span data-ttu-id="f1613-194">Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="f1613-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="f1613-195">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f1613-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="f1613-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="f1613-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="f1613-197">Ogni subnet della rete deve essere associata a un sito di rete specifico, perché le informazioni sulla subnet vengono utilizzate per determinare il sito di rete in cui si trova un endpoint durante l'avvio di una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="f1613-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="f1613-198">Quando la posizione di ogni parte di una sessione è nota, le funzionalità di VoIP aziendale avanzate possono applicare queste informazioni per determinare la modalità di gestione dell'installazione o del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="f1613-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="f1613-199">Tutti gli indirizzi IP pubblici configurati per i server perimetrali audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="f1613-200">Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32.</span><span class="sxs-lookup"><span data-stu-id="f1613-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="f1613-201">Il sito di rete associato deve corrispondere al sito di rete configurato appropriato.</span><span class="sxs-lookup"><span data-stu-id="f1613-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="f1613-202">Ad esempio, l'indirizzo IP pubblico che corrisponde al servizio a/V Edge nel sito centrale Chicago sarebbe NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="f1613-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f1613-203">Per associare una subnet a un sito di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1613-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f1613-204">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1613-205">Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:</span><span class="sxs-lookup"><span data-stu-id="f1613-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="f1613-206">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1613-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="f1613-207">In questo esempio viene creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".</span><span class="sxs-lookup"><span data-stu-id="f1613-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="f1613-208">Ripetere il passaggio 2 per tutte le subnet della topologia.</span><span class="sxs-lookup"><span data-stu-id="f1613-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="f1613-209">Per associare subnet a siti di rete mediante l'importazione di un file CSV</span><span class="sxs-lookup"><span data-stu-id="f1613-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="f1613-210">Creare un file CSV che includa tutte le subnet che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="f1613-210">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="f1613-211">Ad esempio, creare un file denominato **subnet.csv** con il seguente contenuto:</span><span class="sxs-lookup"><span data-stu-id="f1613-211">For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="f1613-212">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1613-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="f1613-213">Eseguire il cmdlet seguente per importare **subnet.csv** e quindi archiviarne il contenuto nell'archivio di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f1613-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f1613-214">Per associare una subnet a un sito di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1613-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f1613-215">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f1613-216">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f1613-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="f1613-217">Fare clic sul pulsante di spostamento della **subnet** .</span><span class="sxs-lookup"><span data-stu-id="f1613-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="f1613-218">Fare clic su **Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="f1613-218">Click **New**.</span></span>

5. <span data-ttu-id="f1613-219">Nella pagina **nuova subnet** fare clic su **ID Subnet** e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si desidera associare a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="f1613-220">Fare clic su **maschera** e quindi digitare la maschera di forma da applicare alla subnet.</span><span class="sxs-lookup"><span data-stu-id="f1613-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="f1613-221">Fare clic su **ID sito di rete** e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.</span><span class="sxs-lookup"><span data-stu-id="f1613-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1613-222">Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="f1613-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="f1613-223">Per informazioni dettagliate sulla procedura, vedere [creare o modificare un sito di rete](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="f1613-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="f1613-224">È inoltre possibile recuperare gli ID di sito per la distribuzione eseguendo il cmdlet **Get-CsNetworkSite** .</span><span class="sxs-lookup"><span data-stu-id="f1613-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="f1613-225">Per informazioni dettagliate, vedere la documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f1613-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="f1613-226">Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere la subnet.</span><span class="sxs-lookup"><span data-stu-id="f1613-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="f1613-227">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1613-227">Click **Commit**.</span></span>

<span data-ttu-id="f1613-228">Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="f1613-229">Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="f1613-230">Questo avviso non verrà generato più di una volta entro un periodo di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="f1613-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="f1613-231">Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:</span><span class="sxs-lookup"><span data-stu-id="f1613-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="f1613-232">**Origine**: Servizio criteri larghezza di banda LS (Core)</span><span class="sxs-lookup"><span data-stu-id="f1613-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="f1613-233">**Numero evento**: 36034</span><span class="sxs-lookup"><span data-stu-id="f1613-233">**Event number**: 36034</span></span>

 <span data-ttu-id="f1613-234">**Livello**: 2</span><span class="sxs-lookup"><span data-stu-id="f1613-234">**Level**: 2</span></span>

 <span data-ttu-id="f1613-235">**Descrizione**: le subnet per gli indirizzi IP seguenti: \<List of IP Addresses\> non sono configurate oppure non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="f1613-236">**Causa**: le subnet per gli indirizzi IP corrispondenti non sono presenti nelle impostazioni della configurazione di rete oppure non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="f1613-237">**Soluzione**: aggiungere le subnet corrispondenti all'elenco di indirizzi IP nelle impostazioni di configurazione di rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="f1613-238">Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-238">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="f1613-239">Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f1613-239">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="f1613-240">Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="f1613-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="f1613-241">Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f1613-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1613-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1613-242">See also</span></span>
<span data-ttu-id="f1613-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="f1613-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="f1613-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f1613-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="f1613-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f1613-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="f1613-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f1613-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="f1613-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f1613-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="f1613-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="f1613-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="f1613-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="f1613-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="f1613-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="f1613-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="f1613-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="f1613-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

