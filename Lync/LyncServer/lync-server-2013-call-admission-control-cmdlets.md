---
title: "Lync Server 2013: cmdlet di controllo dell'ammissione alle chiamate"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3805a597cba993e8b50e006a198fdc693a1d595b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="99c75-102">Cmdlet di controllo dell'ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c75-102">Call admission control cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c75-103">_**Argomento Ultima modifica:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="99c75-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="99c75-104">Controllo di ammissione di chiamata (CAC) determina se la larghezza di banda della rete è sufficiente per stabilire una sessione audio o video in tempo reale di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="99c75-104">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="99c75-105">Puoi gestire CAC configurando limitazioni e impostazioni per reti, siti e subnet e le interazioni tra di esse.</span><span class="sxs-lookup"><span data-stu-id="99c75-105">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="99c75-106">Cmdlet per il controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="99c75-106">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="99c75-107">Usare i cmdlet seguenti per gestire CAC da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="99c75-107">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="99c75-108">**Servizio Controllo di ammissione di chiamata**</span><span class="sxs-lookup"><span data-stu-id="99c75-108">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="99c75-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="99c75-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="99c75-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99c75-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99c75-146">See Also</span></span>


[<span data-ttu-id="99c75-147">Panoramica del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c75-147">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="99c75-148">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="99c75-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

