---
title: 'Lync Server 2013: cmdlet per le applicazioni attendibili'
description: 'Lync Server 2013: cmdlet per le applicazioni attendibili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c23eca9e64f464b88479373846fb397e63bdd4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548862"
---
# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0961f-103">Cmdlet per le applicazioni attendibili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0961f-103">Trusted applications cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0961f-104">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="0961f-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="0961f-105">Un'applicazione attendibile è un'applicazione sviluppata da terze parti a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Microsoft Lync Server 2013 ma che non è una parte incorporata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0961f-105">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="0961f-106">Lync Server 2013 fornisce cmdlet che possono essere utilizzati per configurare e gestire le applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="0961f-106">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="0961f-107">Cmdlet per le applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="0961f-107">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="0961f-108">Utilizzare i cmdlet seguenti per gestire le applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="0961f-108">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="0961f-109">**Applicazioni attendibili**</span><span class="sxs-lookup"><span data-stu-id="0961f-109">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-110">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-110">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-111">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-111">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-112">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-112">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-113">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-113">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0961f-114">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-114">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-115">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-115">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-116">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-116">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0961f-117">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-117">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-118">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-118">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-119">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-119">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-120">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-120">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0961f-121">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-121">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-122">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-122">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-123">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-123">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0961f-124">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0961f-124">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0961f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0961f-125">See Also</span></span>


[<span data-ttu-id="0961f-126">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="0961f-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

