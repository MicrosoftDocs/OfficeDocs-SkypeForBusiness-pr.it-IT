---
title: "Lync Server 2013: cmdlet per l'applicazione Parcheggio di chiamata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f5fd4a1b679c0ca43acb5ad8a96cbaa18085137
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533413"
---
# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="57f6b-102">Cmdlet per l'applicazione Parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f6b-102">Call Park application cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57f6b-103">_**Ultimo argomento modificato:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="57f6b-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="57f6b-104">L'applicazione Parcheggio di chiamata consente a un utente di effettuare una chiamata in attesa, quindi di recuperare la chiamata da un telefono diverso.</span><span class="sxs-lookup"><span data-stu-id="57f6b-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="57f6b-105">Utilizzare questi cmdlet per configurare le impostazioni per le orbite del parcheggio di chiamata e l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="57f6b-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="57f6b-106">Cmdlet per l'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="57f6b-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="57f6b-107">I cmdlet seguenti possono essere utilizzati per gestire l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="57f6b-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="57f6b-108">**Applicazione Parcheggio di chiamata**</span><span class="sxs-lookup"><span data-stu-id="57f6b-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="57f6b-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="57f6b-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="57f6b-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57f6b-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57f6b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57f6b-118">See Also</span></span>


[<span data-ttu-id="57f6b-119">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="57f6b-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

