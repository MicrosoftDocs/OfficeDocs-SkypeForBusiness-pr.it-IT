---
title: Configurare le impostazioni di rete per il routing basato sulla posizione
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ed7f58489a43a1bd9e781cd7e8fb69bd6a6dc58
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36185017"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="8d308-103">Configurare le impostazioni di rete per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="8d308-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="8d308-104">Se non è già stato fatto, leggere il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) per esaminare gli altri passaggi che è necessario eseguire prima di configurare le impostazioni di rete per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8d308-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="8d308-105">Questo articolo descrive come configurare le impostazioni di rete per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8d308-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="8d308-106">Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="8d308-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="8d308-107">Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d308-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="8d308-108">Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8d308-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="8d308-109">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="8d308-109">Define network regions</span></span>
 <span data-ttu-id="8d308-110">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8d308-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="8d308-111">Usa il cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) per definire le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="8d308-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="8d308-112">Tieni presente che il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o &lt;restrizioni e&gt; il parametro ID sito CentralSite è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8d308-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="8d308-113">In questo esempio creiamo un'area di rete denominata India.</span><span class="sxs-lookup"><span data-stu-id="8d308-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="8d308-114">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="8d308-114">Define network sites</span></span>

<span data-ttu-id="8d308-115">Usare il cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) per definire i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="8d308-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="8d308-116">In questo esempio creiamo due nuovi siti di rete, Delhi e Hyderabad, nell'area dell'India.</span><span class="sxs-lookup"><span data-stu-id="8d308-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="8d308-117">Nella tabella seguente sono illustrati i siti di rete definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8d308-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="8d308-118">Sito 1</span><span class="sxs-lookup"><span data-stu-id="8d308-118">Site 1</span></span> |<span data-ttu-id="8d308-119">Sito 2</span><span class="sxs-lookup"><span data-stu-id="8d308-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8d308-120">ID sito</span><span class="sxs-lookup"><span data-stu-id="8d308-120">Site ID</span></span>    |    <span data-ttu-id="8d308-121">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="8d308-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="8d308-122">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8d308-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="8d308-123">ID area</span><span class="sxs-lookup"><span data-stu-id="8d308-123">Region ID</span></span>  |     <span data-ttu-id="8d308-124">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="8d308-124">Region 1 (India)</span></span>    |   <span data-ttu-id="8d308-125">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="8d308-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="8d308-126">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="8d308-126">Define network subnets</span></span>

<span data-ttu-id="8d308-127">Utilizzare il cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) per definire le subnet di rete e associarle ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="8d308-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="8d308-128">Ogni subnet interna può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="8d308-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="8d308-129">In questo esempio creiamo un'associazione tra subnet 192.168.0.0 e il sito di rete Delhi e tra subnet 2001:4898: E8:25:844E: 926f: 85AD: dd8e e il sito di rete di Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="8d308-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="8d308-130">La tabella seguente mostra le subnet definite in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8d308-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="8d308-131">Sito 1</span><span class="sxs-lookup"><span data-stu-id="8d308-131">Site 1</span></span> |<span data-ttu-id="8d308-132">Sito 2</span><span class="sxs-lookup"><span data-stu-id="8d308-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8d308-133">ID subnet</span><span class="sxs-lookup"><span data-stu-id="8d308-133">Subnet ID</span></span>   |    <span data-ttu-id="8d308-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="8d308-134">192.168.0.0</span></span>     |  <span data-ttu-id="8d308-135">2001:4898: E8:25:844E: 926f: 85AD: dd8e</span><span class="sxs-lookup"><span data-stu-id="8d308-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="8d308-136">Maschera</span><span class="sxs-lookup"><span data-stu-id="8d308-136">Mask</span></span>  |     <span data-ttu-id="8d308-137">24</span><span class="sxs-lookup"><span data-stu-id="8d308-137">24</span></span>    |   <span data-ttu-id="8d308-138">120</span><span class="sxs-lookup"><span data-stu-id="8d308-138">120</span></span>      |
|<span data-ttu-id="8d308-139">ID sito</span><span class="sxs-lookup"><span data-stu-id="8d308-139">Site ID</span></span>  | <span data-ttu-id="8d308-140">Sito (Delhi)</span><span class="sxs-lookup"><span data-stu-id="8d308-140">Site (Delhi)</span></span> | <span data-ttu-id="8d308-141">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8d308-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="8d308-142">Per più subnet, è possibile importare un file CSV usando uno script come il seguente.</span><span class="sxs-lookup"><span data-stu-id="8d308-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="8d308-143">In questo esempio, il file CSV ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8d308-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="8d308-144">Definire subnet esterne</span><span class="sxs-lookup"><span data-stu-id="8d308-144">Define external subnets</span></span>
<span data-ttu-id="8d308-145">Usa il cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) per definire subnet esterne e assegnarle al tenant.</span><span class="sxs-lookup"><span data-stu-id="8d308-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="8d308-146">Puoi definire un numero illimitato di subnet per un tenant.</span><span class="sxs-lookup"><span data-stu-id="8d308-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="8d308-147">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d308-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="8d308-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8d308-148">Next steps</span></span>
<span data-ttu-id="8d308-149">Accedere a [abilitare il routing basato sulla posizione per il routing diretto](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="8d308-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="8d308-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8d308-150">Related topics</span></span>
- [<span data-ttu-id="8d308-151">Pianificare il routing basato sulla posizione per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="8d308-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="8d308-152">Terminologia di routing basata sulla posizione</span><span class="sxs-lookup"><span data-stu-id="8d308-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
