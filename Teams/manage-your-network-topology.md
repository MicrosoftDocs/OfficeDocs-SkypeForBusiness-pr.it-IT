---
title: Gestire la topologia di rete per le funzionalità vocali di cloud in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come configurare le impostazioni di rete per le funzionalità vocali di cloud in Microsoft teams.
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802576"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="f2d40-103">Gestire la topologia di rete per le funzionalità vocali di cloud in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2d40-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="f2d40-104">Se l'organizzazione sta distribuendo il [routing basato sulla posizione per il routing diretto](location-based-routing-plan.md) o per le [chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md), è necessario configurare le impostazioni di rete per l'uso con queste funzionalità di cloud Voice in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f2d40-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="f2d40-105">Le impostazioni di rete vengono usate per determinare la posizione di un client teams e includere aree di rete, siti di rete, subnet e indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="f2d40-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="f2d40-106">A seconda della funzionalità cloud Voice e della funzionalità che si sta distribuendo, è possibile configurare alcune o tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f2d40-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="f2d40-107">Per altre informazioni su questi termini, vedere [impostazioni di rete per le caratteristiche vocali del cloud](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f2d40-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f2d40-108">Le impostazioni di rete vengono configurate nella pagina della **topologia di rete** dell'interfaccia di amministrazione di Microsoft teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2d40-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f2d40-109">Configurare le impostazioni di rete nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2d40-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="f2d40-110">Si definiscono aree di rete, siti di rete e subnet nella scheda **siti di rete** della pagina della **topologia** di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d40-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="f2d40-111">In questo caso, è possibile creare o modificare un sito di rete, associare un sito a un'area di rete, associare una subnet al sito, attivare il routing basato sulla posizione e assegnare criteri di emergenza al sito.</span><span class="sxs-lookup"><span data-stu-id="f2d40-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="f2d40-112">È anche possibile aggiungere aree di rete che possono essere usate globalmente per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="f2d40-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="f2d40-113">Aggiungere e configurare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f2d40-113">Add and configure a network site</span></span>

1. <span data-ttu-id="f2d40-114">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams , vai alla  >  **topologia di rete** locations e quindi fai clic sulla scheda **siti di rete** .</span><span class="sxs-lookup"><span data-stu-id="f2d40-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="f2d40-115">Fare clic su **Aggiungi** e quindi immettere un nome e una descrizione per il sito.</span><span class="sxs-lookup"><span data-stu-id="f2d40-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Screenshot della pagina Aggiungi sito di rete](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="f2d40-117">Per associare il sito a un'area di rete, fare clic su **Aggiungi area di rete**, selezionare un'area geografica esistente o fare clic su **Aggiungi** per aggiungere un'area geografica e quindi fare clic su **collega**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="f2d40-118">Per abilitare Location-Based routing per il sito, attivare il **routing basato sulla posizione**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="f2d40-119">Per assegnare i criteri dei servizi di emergenza al sito, eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2d40-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="f2d40-120">Se l'organizzazione usa un piano di chiamata o un routing diretto del sistema telefonico, in criteri per le **chiamate di emergenza** selezionare i criteri desiderati.</span><span class="sxs-lookup"><span data-stu-id="f2d40-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="f2d40-121">Se l'organizzazione ha distribuito il routing diretto del sistema telefonico, in **criteri di routing delle chiamate di emergenza** selezionare i criteri desiderati.</span><span class="sxs-lookup"><span data-stu-id="f2d40-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="f2d40-122">Per associare una subnet al sito, fare clic su **Aggiungi subnet** in **subnet**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="f2d40-123">Specificare la versione IP, l'indirizzo IP, l'intervallo di rete, aggiungere una descrizione e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="f2d40-124">Ogni subnet deve essere associata a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="f2d40-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="f2d40-125">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="f2d40-126">Modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f2d40-126">Modify a network site</span></span>

1. <span data-ttu-id="f2d40-127">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams , vai alla  >  **topologia di rete** locations e quindi fai clic sulla scheda **siti di rete** .</span><span class="sxs-lookup"><span data-stu-id="f2d40-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="f2d40-128">Selezionare il sito facendo clic a sinistra del nome del sito, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f2d40-129">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="f2d40-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="f2d40-130">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="f2d40-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="f2d40-131">Gli indirizzi IP attendibili esterni vengono gestiti nella scheda **IPS attendibile** nella pagina **topologia di rete** dell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f2d40-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="f2d40-132">È possibile aggiungere un numero illimitato di indirizzi IP attendibili esterni.</span><span class="sxs-lookup"><span data-stu-id="f2d40-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="f2d40-133">Aggiungere un indirizzo IP attendibile</span><span class="sxs-lookup"><span data-stu-id="f2d40-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="f2d40-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams , vai alla  >  **topologia di rete** locations e quindi fai clic sulla scheda **IPS attendibile** .</span><span class="sxs-lookup"><span data-stu-id="f2d40-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="f2d40-135">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-135">Click **New**.</span></span>
3. <span data-ttu-id="f2d40-136">Nel riquadro **Aggiungi indirizzo IP attendibile** specificare la versione IP, l'indirizzo IP, l'intervallo di rete, aggiungere una descrizione e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Screenshot del riquadro Aggiungi indirizzo IP attendibile](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="f2d40-138">Modificare un indirizzo IP attendibile</span><span class="sxs-lookup"><span data-stu-id="f2d40-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="f2d40-139">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams , vai alla  >  **topologia di rete** locations e quindi fai clic sulla scheda **IPS attendibile** .</span><span class="sxs-lookup"><span data-stu-id="f2d40-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="f2d40-140">Selezionare l'indirizzo IP facendo clic a sinistra, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="f2d40-141">Nel riquadro **modifica indirizzo IP attendibile** apportare le modifiche desiderate e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f2d40-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="f2d40-142">Configurare le impostazioni di rete tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2d40-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="f2d40-143">Per completare la procedura descritta in questa sezione, è necessaria una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2d40-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f2d40-144">Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f2d40-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="f2d40-145">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="f2d40-145">Define network regions</span></span>

 <span data-ttu-id="f2d40-146">Usa il cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) per definire le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d40-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="f2d40-147">Tieni presente che il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni e il &lt; parametro ID sito CentralSite &gt; è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f2d40-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="f2d40-148">In questo esempio creiamo un'area di rete denominata India.</span><span class="sxs-lookup"><span data-stu-id="f2d40-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="f2d40-149">Vedere anche [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="f2d40-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="f2d40-150">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="f2d40-150">Define network sites</span></span>

<span data-ttu-id="f2d40-151">Usare il cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) per definire i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d40-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="f2d40-152">Ogni sito di rete deve essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d40-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="f2d40-153">In questo esempio creiamo due nuovi siti di rete, Delhi e Hyderabad, nell'area dell'India.</span><span class="sxs-lookup"><span data-stu-id="f2d40-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="f2d40-154">Nella tabella seguente sono illustrati i siti di rete definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f2d40-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="f2d40-155">Sito 1</span><span class="sxs-lookup"><span data-stu-id="f2d40-155">Site 1</span></span> |<span data-ttu-id="f2d40-156">Sito 2</span><span class="sxs-lookup"><span data-stu-id="f2d40-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f2d40-157">ID sito</span><span class="sxs-lookup"><span data-stu-id="f2d40-157">Site ID</span></span>    |    <span data-ttu-id="f2d40-158">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f2d40-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="f2d40-159">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f2d40-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="f2d40-160">ID area</span><span class="sxs-lookup"><span data-stu-id="f2d40-160">Region ID</span></span>  |     <span data-ttu-id="f2d40-161">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="f2d40-161">Region 1 (India)</span></span>    |   <span data-ttu-id="f2d40-162">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="f2d40-162">Region 1 (India)</span></span>      |

<span data-ttu-id="f2d40-163">Vedere anche [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="f2d40-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="f2d40-164">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="f2d40-164">Define network subnets</span></span>

<span data-ttu-id="f2d40-165">Utilizzare il cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) per definire le subnet di rete e associarle ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d40-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="f2d40-166">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="f2d40-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="f2d40-167">In questo esempio creiamo un'associazione tra subnet 192.168.0.0 e il sito di rete Delhi e tra subnet 2001:4898: E8:25:844E: 926f: 85AD: dd8e e il sito di rete di Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="f2d40-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="f2d40-168">La tabella seguente mostra le subnet definite in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f2d40-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="f2d40-169">Sito 1</span><span class="sxs-lookup"><span data-stu-id="f2d40-169">Site 1</span></span> |<span data-ttu-id="f2d40-170">Sito 2</span><span class="sxs-lookup"><span data-stu-id="f2d40-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f2d40-171">ID subnet</span><span class="sxs-lookup"><span data-stu-id="f2d40-171">Subnet ID</span></span>   |    <span data-ttu-id="f2d40-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="f2d40-172">192.168.0.0</span></span>     |  <span data-ttu-id="f2d40-173">2001:4898: E8:25:844E: 926f: 85AD: dd8e</span><span class="sxs-lookup"><span data-stu-id="f2d40-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="f2d40-174">Maschera</span><span class="sxs-lookup"><span data-stu-id="f2d40-174">Mask</span></span>  |     <span data-ttu-id="f2d40-175">24</span><span class="sxs-lookup"><span data-stu-id="f2d40-175">24</span></span>    |   <span data-ttu-id="f2d40-176">120</span><span class="sxs-lookup"><span data-stu-id="f2d40-176">120</span></span>      |
|<span data-ttu-id="f2d40-177">ID sito</span><span class="sxs-lookup"><span data-stu-id="f2d40-177">Site ID</span></span>  | <span data-ttu-id="f2d40-178">Sito (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f2d40-178">Site (Delhi)</span></span> | <span data-ttu-id="f2d40-179">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f2d40-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="f2d40-180">Per più subnet, è possibile importare un file CSV usando uno script come il seguente.</span><span class="sxs-lookup"><span data-stu-id="f2d40-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="f2d40-181">In questo esempio, il file CSV ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f2d40-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="f2d40-182">Vedere anche [set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="f2d40-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="f2d40-183">Definire subnet esterne (indirizzi IP attendibili esterni)</span><span class="sxs-lookup"><span data-stu-id="f2d40-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="f2d40-184">Usa il cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) per definire subnet esterne e assegnarle al tenant.</span><span class="sxs-lookup"><span data-stu-id="f2d40-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="f2d40-185">Puoi definire un numero illimitato di subnet esterne per un tenant.</span><span class="sxs-lookup"><span data-stu-id="f2d40-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="f2d40-186">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f2d40-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="f2d40-187">Vedere anche [set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="f2d40-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2d40-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2d40-188">Related topics</span></span>

- [<span data-ttu-id="f2d40-189">Impostazioni di rete per le funzionalità vocali di cloud in teams</span><span class="sxs-lookup"><span data-stu-id="f2d40-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
