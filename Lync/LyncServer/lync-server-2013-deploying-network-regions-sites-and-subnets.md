---
title: 'Lync Server 2013: distribuzione di aree di rete, siti e subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 188b2a85e8961a0460bee819e3281d33a6069ddd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="79323-102">Distribuzione di aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79323-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79323-103">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="79323-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="79323-104">Dopo la distribuzione di VoIP aziendale, è necessario configurare:</span><span class="sxs-lookup"><span data-stu-id="79323-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="79323-105">Aree di rete</span><span class="sxs-lookup"><span data-stu-id="79323-105">Network regions</span></span>

  - <span data-ttu-id="79323-106">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="79323-106">Network sites</span></span>

  - <span data-ttu-id="79323-107">Subnet di rete</span><span class="sxs-lookup"><span data-stu-id="79323-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="79323-108">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="79323-108">Define Network Regions</span></span>

<span data-ttu-id="79323-109">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkRegion o il pannello di controllo di Lync Server per definire le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="79323-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="79323-110">Per ulteriori informazioni, vedere [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="79323-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="79323-111">In questo esempio, il comando di Windows PowerShell seguente illustra l'area di rete, Region 1 (India), definita in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="79323-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="79323-112">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="79323-112">Define Network Sites</span></span>

<span data-ttu-id="79323-113">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite o il pannello di controllo di Lync Server per definire i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="79323-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="79323-114">Per ulteriori informazioni, vedere [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="79323-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="79323-115">Per questo esempio, nella tabella seguente e nel comando di Windows PowerShell di Lync Server vengono illustrati i siti di rete definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="79323-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="79323-116">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="79323-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="79323-117">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="79323-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="79323-118">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79323-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79323-119">ID sito</span><span class="sxs-lookup"><span data-stu-id="79323-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="79323-120">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="79323-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="79323-121">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79323-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79323-122">ID area</span><span class="sxs-lookup"><span data-stu-id="79323-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="79323-123">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="79323-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="79323-124">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="79323-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="79323-125">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="79323-125">Define Network Subnets</span></span>

<span data-ttu-id="79323-126">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSubnet o il pannello di controllo di Lync Server per definire le subnet di rete e assegnarle a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="79323-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="79323-127">Per ulteriori informazioni, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="79323-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="79323-128">Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell viene illustrata l'assegnazione delle subnet di rete ai siti di rete, Delhi e Hyderabad, definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="79323-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="79323-129">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="79323-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="79323-130">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="79323-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="79323-131">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79323-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79323-132">ID subnet</span><span class="sxs-lookup"><span data-stu-id="79323-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="79323-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="79323-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="79323-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="79323-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79323-135">Maschera</span><span class="sxs-lookup"><span data-stu-id="79323-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="79323-136">24</span><span class="sxs-lookup"><span data-stu-id="79323-136">24</span></span></p></td>
<td><p><span data-ttu-id="79323-137">24</span><span class="sxs-lookup"><span data-stu-id="79323-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79323-138">ID sito</span><span class="sxs-lookup"><span data-stu-id="79323-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="79323-139">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="79323-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="79323-140">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79323-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79323-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79323-141">See Also</span></span>


[<span data-ttu-id="79323-142">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79323-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

