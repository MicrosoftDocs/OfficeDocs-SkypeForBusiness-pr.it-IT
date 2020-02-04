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
ms.openlocfilehash: b7524098f256587820beaabe31a8162591ba595d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="c5800-102">Cmdlet di topologia JN Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5800-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5800-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="c5800-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="c5800-104">Molti cmdlet di topologia inclusi in Microsoft Lync Server 2013 sono progettati per l'uso con configurazione e generatore di topologie. a causa di questo, esistono diversi cmdlet di topologia che gli amministratori chiameranno raramente direttamente.</span><span class="sxs-lookup"><span data-stu-id="c5800-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="c5800-105">Ci saranno tuttavia momenti in cui gli amministratori dovranno usare questi cmdlet. Dopo aver creato nuovi account Kerberos, ad esempio, devi eseguire il cmdlet [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c5800-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="c5800-106">Inoltre, gli amministratori possono eseguire i cmdlet, ad esempio [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) e [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) , per garantire che Lync Server 2013 sia stato installato correttamente e funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="c5800-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="c5800-107">Cmdlet di topologia</span><span class="sxs-lookup"><span data-stu-id="c5800-107">Topology Cmdlets</span></span>

<span data-ttu-id="c5800-108">Di seguito è riportato un elenco di cmdlet che si riferiscano direttamente alla gestione della topologia di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="c5800-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="c5800-109">**Topologia**</span><span class="sxs-lookup"><span data-stu-id="c5800-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5800-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5800-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5800-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5800-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5800-125">See Also</span></span>


[<span data-ttu-id="c5800-126">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="c5800-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

