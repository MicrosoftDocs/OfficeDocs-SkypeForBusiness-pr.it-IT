---
title: 'Lync Server 2013: cmdlet per il controllo di ammissione di chiamata'
description: 'Lync Server 2013: cmdlet per il controllo di ammissione di chiamata.'
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
ms.openlocfilehash: 2d841273ef57c53b5bfa70ca5f2e54e679f70b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569202"
---
# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e5404-103">Cmdlet per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5404-103">Call admission control cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5404-104">_**Ultimo argomento modificato:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="e5404-104">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="e5404-105">Il controllo di ammissione di chiamata determina se la larghezza di banda di rete è sufficiente per stabilire una sessione audio o video in tempo reale di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="e5404-105">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="e5404-106">È possibile gestire il servizio di controllo di ammissione configurando le limitazioni e le impostazioni per reti, siti e subnet e le interazioni tra di essi.</span><span class="sxs-lookup"><span data-stu-id="e5404-106">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="e5404-107">Cmdlet per il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e5404-107">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="e5404-108">Utilizzare i seguenti cmdlet per gestire il servizio di controllo di ammissione di servizio da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e5404-108">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="e5404-109">**Servizio Controllo di ammissione di chiamata**</span><span class="sxs-lookup"><span data-stu-id="e5404-109">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-110">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-110">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-111">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-111">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-112">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-112">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-113">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-113">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-114">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-114">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-115">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-115">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-116">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-116">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-117">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-117">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-118">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-118">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-119">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-119">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-120">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-120">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-121">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-121">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-122">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-122">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-123">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-123">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-124">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-124">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-125">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-125">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-126">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-126">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-127">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-127">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-128">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-128">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-129">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-129">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-130">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-130">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-131">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-131">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-132">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-132">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-133">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-133">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-134">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-134">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-135">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-135">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-136">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-136">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-137">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-137">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-138">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-138">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-139">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-139">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-140">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-140">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-141">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-141">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-142">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-142">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5404-143">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-143">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-144">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-144">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-145">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-145">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5404-146">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5404-146">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5404-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5404-147">See Also</span></span>


[<span data-ttu-id="e5404-148">Panoramica del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5404-148">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="e5404-149">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5404-149">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

