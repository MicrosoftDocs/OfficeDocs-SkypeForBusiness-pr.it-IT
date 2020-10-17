---
title: 'Lync Server 2013: cmdlet per telefoni e dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d997b8a6c6dfc82943134d797ab2d98eb93d888
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524203"
---
# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a5b1c-102">Cmdlet per telefoni e dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5b1c-102">Phones and devices cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b1c-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="a5b1c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="a5b1c-104">Microsoft Lync Server 2013 offre numerosi cmdlet che consentono di gestire i telefoni e altri dispositivi hardware.</span><span class="sxs-lookup"><span data-stu-id="a5b1c-104">Microsoft Lync Server 2013 provides a number of cmdlets that enable you to manage telephones and other hardware devices.</span></span> <span data-ttu-id="a5b1c-105">Ciò include elementi quali telefoni VoIP (Voice over IP). telefoni delle aree comuni (ad esempio, un telefono in una lobby di edifici, una caffetteria o un'altra postazione pubblica); e persino telefoni analogici, telefoni che non sono in grado di eseguire Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a5b1c-105">This includes such things as Voice over IP (VoIP) phones; common area phones (for example, a phone in a building lobby, cafeteria, or other public location); and even analog phones, phones that are not capable of running Lync Phone Edition.</span></span>

<div>

## <a name="phones-and-devices-cmdlets"></a><span data-ttu-id="a5b1c-106">Cmdlet per telefoni e dispositivi</span><span class="sxs-lookup"><span data-stu-id="a5b1c-106">Phones and Devices Cmdlets</span></span>

<span data-ttu-id="a5b1c-107">I cmdlet di **CsDeviceUpdate** vengono utilizzati per gestire il servizio Web aggiornamento dispositivi, un componente di Lync Server che consente agli amministratori di distribuire gli aggiornamenti del firmware ai telefoni e ad altri dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a5b1c-107">The **CsDeviceUpdate** cmdlets are used to manage the Device Update Web service, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Phone Edition.</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-108">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-108">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-109">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-109">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-110">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-110">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-112">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-112">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-129">[Approva-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a5b1c-135">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-135">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-136">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-136">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-137">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-137">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a5b1c-138">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a5b1c-138">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5b1c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5b1c-139">See Also</span></span>


[<span data-ttu-id="a5b1c-140">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="a5b1c-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

