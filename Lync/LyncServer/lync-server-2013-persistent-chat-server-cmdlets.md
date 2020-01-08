---
title: 'Lync Server 2013: cmdlet del server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f71b1f87c236384bd8ec22485981222c05bf4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="956c2-102">Cmdlet del server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="956c2-102">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="956c2-103">_**Argomento Ultima modifica:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="956c2-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="956c2-104">I cmdlet per la chat persistente consentono di gestire e configurare il servizio di chat persistente di Microsoft Lync Server 2013 (in precedenza noto come servizio chat di gruppo).</span><span class="sxs-lookup"><span data-stu-id="956c2-104">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="956c2-105">La chat persistente consente agli utenti di partecipare alle sessioni di messaggistica istantanea online.</span><span class="sxs-lookup"><span data-stu-id="956c2-105">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="956c2-106">Anche se queste sessioni possono avvenire in tempo reale, il contenuto di ogni sessione è persistente; Questo significa che queste conversazioni possono essere riprese da chiunque in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="956c2-106">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="956c2-107">Cmdlet per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="956c2-107">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="956c2-108">I cmdlet per la chat persistente consentono di gestire e configurare il servizio di chat persistente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="956c2-108">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="956c2-109">**Cmdlet per la chat persistente**</span><span class="sxs-lookup"><span data-stu-id="956c2-109">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="956c2-110">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-110">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-129">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-129">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="956c2-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="956c2-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="956c2-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

