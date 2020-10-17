---
title: 'Lync Server 2013: distribuzione di aree di rete, siti e subnet'
description: 'Lync Server 2013: distribuzione di aree di rete, siti e subnet.'
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
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561092"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="6529b-103">Distribuzione di aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6529b-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6529b-104">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="6529b-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="6529b-105">Dopo la distribuzione di VoIP aziendale, è necessario configurare:</span><span class="sxs-lookup"><span data-stu-id="6529b-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="6529b-106">Aree di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-106">Network regions</span></span>

  - <span data-ttu-id="6529b-107">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-107">Network sites</span></span>

  - <span data-ttu-id="6529b-108">Subnet di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="6529b-109">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-109">Define Network Regions</span></span>

<span data-ttu-id="6529b-110">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkRegion o il pannello di controllo di Lync Server per definire le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="6529b-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="6529b-111">Per ulteriori informazioni, vedere [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="6529b-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="6529b-112">In questo esempio, il comando di Windows PowerShell seguente illustra l'area di rete, Region 1 (India), definita in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="6529b-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="6529b-113">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-113">Define Network Sites</span></span>

<span data-ttu-id="6529b-114">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite o il pannello di controllo di Lync Server per definire i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="6529b-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="6529b-115">Per ulteriori informazioni, vedere [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="6529b-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="6529b-116">Per questo esempio, nella tabella seguente e nel comando di Windows PowerShell di Lync Server vengono illustrati i siti di rete definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="6529b-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="6529b-117">Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="6529b-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="6529b-118">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6529b-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="6529b-119">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6529b-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6529b-120">ID sito</span><span class="sxs-lookup"><span data-stu-id="6529b-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="6529b-121">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6529b-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="6529b-122">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6529b-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6529b-123">ID area</span><span class="sxs-lookup"><span data-stu-id="6529b-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="6529b-124">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="6529b-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="6529b-125">Regione 1 (India)</span><span class="sxs-lookup"><span data-stu-id="6529b-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="6529b-126">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="6529b-126">Define Network Subnets</span></span>

<span data-ttu-id="6529b-127">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSubnet o il pannello di controllo di Lync Server per definire le subnet di rete e assegnarle a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="6529b-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="6529b-128">Per ulteriori informazioni, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="6529b-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="6529b-129">Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell viene illustrata l'assegnazione delle subnet di rete ai siti di rete, Delhi e Hyderabad, definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="6529b-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="6529b-130">Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="6529b-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="6529b-131">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6529b-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="6529b-132">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6529b-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6529b-133">ID subnet</span><span class="sxs-lookup"><span data-stu-id="6529b-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="6529b-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="6529b-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="6529b-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="6529b-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6529b-136">Maschera</span><span class="sxs-lookup"><span data-stu-id="6529b-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="6529b-137">24</span><span class="sxs-lookup"><span data-stu-id="6529b-137">24</span></span></p></td>
<td><p><span data-ttu-id="6529b-138">24</span><span class="sxs-lookup"><span data-stu-id="6529b-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6529b-139">ID sito</span><span class="sxs-lookup"><span data-stu-id="6529b-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="6529b-140">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="6529b-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="6529b-141">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="6529b-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6529b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6529b-142">See Also</span></span>


[<span data-ttu-id="6529b-143">Configurazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6529b-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

