---
title: 'Lync Server 2013: cmdlet di routing statico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a5c5dcefa5c4650c6bbfabf940840f22fc5df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b9080-102">Cmdlet di routing statici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9080-102">Static routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9080-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b9080-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b9080-104">Con le route statiche, gli amministratori possono predeterminare le route di rete eseguite dai messaggi SIP.</span><span class="sxs-lookup"><span data-stu-id="b9080-104">With static routes, administrators can predetermine the network routes taken by SIP messages.</span></span> <span data-ttu-id="b9080-105">Quando un messaggio viene ricevuto da un server, il server controlla l'indirizzo del messaggio e quindi inoltra il messaggio al server hop successivo preconfigurato da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="b9080-105">When a message is received by a server, the server checks the message address and then forwards the message to the next hop server preconfigured by an administrator.</span></span> <span data-ttu-id="b9080-106">Se la configurazione è corretta, le route statiche aiutano a garantire un recapito tempestivo e accurato dei messaggi, applicando un sovraccarico minimo sui server.</span><span class="sxs-lookup"><span data-stu-id="b9080-106">If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers.</span></span>

<div>

## <a name="static-routing-cmdlets"></a><span data-ttu-id="b9080-107">Cmdlet di routing statici</span><span class="sxs-lookup"><span data-stu-id="b9080-107">Static Routing Cmdlets</span></span>

<span data-ttu-id="b9080-108">Se non diversamente indicato dal personale del supporto tecnico Microsoft, le route statiche configurate per Microsoft Lync Server 2013 devono essere create usando il cmdlet [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="b9080-108">Unless otherwise instructed by Microsoft support personnel, static routes configured for Microsoft Lync Server 2013 should be created using the [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="b9080-109">Dopo aver creato una route, è possibile usare i cmdlet CsStaticRoutingConfiguration per aggiungere la route a una raccolta di routing statica.</span><span class="sxs-lookup"><span data-stu-id="b9080-109">After a route has been created, you can then use the CsStaticRoutingConfiguration cmdlets to add that route to a static routing collection.</span></span>

<span data-ttu-id="b9080-110">**Routing statico**</span><span class="sxs-lookup"><span data-stu-id="b9080-110">**Static Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-115">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-115">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9080-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-120">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-120">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-121">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-121">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-122">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-122">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-123">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-123">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-124">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-124">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9080-127">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9080-127">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9080-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9080-128">See Also</span></span>


[<span data-ttu-id="b9080-129">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="b9080-129">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

