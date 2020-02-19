---
title: 'Lync Server 2013: cmdlet di topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08d2a49e7f15885e8047ce45d4e0989f9ccec808
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="700c7-102">Cmdlet per la topologia JN Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="700c7-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="700c7-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="700c7-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="700c7-104">Molti dei cmdlet di topologia inclusi in Microsoft Lync Server 2013 sono stati creati per essere utilizzati con il programma di installazione e il generatore di topologie. per questo motivo, esistono diversi cmdlet di topologia che gli amministratori chiamano raramente direttamente.</span><span class="sxs-lookup"><span data-stu-id="700c7-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="700c7-105">In alcuni casi, tuttavia, saranno necessari gli amministratori per l'utilizzo di questi cmdlet. ad esempio, dopo la creazione di nuovi account Kerberos, è necessario eseguire il cmdlet [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="700c7-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="700c7-106">Inoltre, è probabile che gli amministratori eseguano cmdlet quali [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) e [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) per garantire che Lync Server 2013 sia stato installato correttamente e funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="700c7-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="700c7-107">Cmdlet per la topologia</span><span class="sxs-lookup"><span data-stu-id="700c7-107">Topology Cmdlets</span></span>

<span data-ttu-id="700c7-108">Di seguito è riportato un elenco di cmdlet che riguardano direttamente la gestione della topologia di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="700c7-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="700c7-109">**Topologia**</span><span class="sxs-lookup"><span data-stu-id="700c7-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-110">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-110">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-111">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-111">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-112">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-112">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-113">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-113">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-114">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-114">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-115">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-115">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-116">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-116">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-117">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-117">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-118">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-118">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-119">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-119">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-120">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-120">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-121">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-121">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-122">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-122">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="700c7-123">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-123">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="700c7-124">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="700c7-124">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="700c7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="700c7-125">See Also</span></span>


[<span data-ttu-id="700c7-126">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="700c7-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

