---
title: 'Lync Server 2013: distribuzione di aree geografiche, siti e subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e22eb-102">Distribuzione di aree geografiche, siti e subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e22eb-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e22eb-103">_**Argomento Ultima modifica:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e22eb-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e22eb-104">Dopo aver distribuito Enterprise Voice, è necessario configurare:</span><span class="sxs-lookup"><span data-stu-id="e22eb-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="e22eb-105">Aree di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-105">Network regions</span></span>

  - <span data-ttu-id="e22eb-106">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-106">Network sites</span></span>

  - <span data-ttu-id="e22eb-107">Subnet di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="e22eb-108">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-108">Define Network Regions</span></span>

<span data-ttu-id="e22eb-109">Usare il comando Lync Server di Windows PowerShell, New-CsNetworkRegion o il pannello di controllo di Lync Server per definire le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e22eb-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="e22eb-110">Per altre informazioni, vedere [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="e22eb-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="e22eb-111">Per questo esempio, il comando di Windows PowerShell seguente illustra l'area geografica della rete, Region 1 (India), definita in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e22eb-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="e22eb-112">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-112">Define Network Sites</span></span>

<span data-ttu-id="e22eb-113">Usare il comando Lync Server di Windows PowerShell, New-CsNetworkSite o il pannello di controllo di Lync Server per definire i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="e22eb-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="e22eb-114">Per altre informazioni, vedere [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="e22eb-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="e22eb-115">Per questo esempio, la tabella seguente e il comando di Windows PowerShell di Lync Server illustrano i siti di rete definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e22eb-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="e22eb-116">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="e22eb-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e22eb-117">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e22eb-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e22eb-118">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e22eb-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e22eb-119">ID sito</span><span class="sxs-lookup"><span data-stu-id="e22eb-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e22eb-120">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e22eb-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e22eb-121">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e22eb-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e22eb-122">ID area</span><span class="sxs-lookup"><span data-stu-id="e22eb-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="e22eb-123">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="e22eb-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="e22eb-124">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="e22eb-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="e22eb-125">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="e22eb-125">Define Network Subnets</span></span>

<span data-ttu-id="e22eb-126">Usare il comando Lync Server di Windows PowerShell, New-CsNetworkSubnet o il pannello di controllo di Lync Server per definire le subnet di rete e assegnarle ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="e22eb-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="e22eb-127">Per altre informazioni, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="e22eb-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="e22eb-128">Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano l'assegnazione delle subnet di rete ai siti di rete, Delhi e Hyderabad, definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e22eb-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="e22eb-129">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="e22eb-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e22eb-130">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e22eb-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e22eb-131">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e22eb-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e22eb-132">ID subnet</span><span class="sxs-lookup"><span data-stu-id="e22eb-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="e22eb-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="e22eb-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="e22eb-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e22eb-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e22eb-135">Maschera</span><span class="sxs-lookup"><span data-stu-id="e22eb-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="e22eb-136">24</span><span class="sxs-lookup"><span data-stu-id="e22eb-136">24</span></span></p></td>
<td><p><span data-ttu-id="e22eb-137">24</span><span class="sxs-lookup"><span data-stu-id="e22eb-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e22eb-138">ID sito</span><span class="sxs-lookup"><span data-stu-id="e22eb-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e22eb-139">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="e22eb-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e22eb-140">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e22eb-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e22eb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e22eb-141">See Also</span></span>


[<span data-ttu-id="e22eb-142">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e22eb-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

