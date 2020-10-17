---
title: 'Lync Server 2013: cmdlet di Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9102adc17b5177264cc3e4daa1329cced5d9fe4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529723"
---
# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5de1f-102">Cmdlet di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de1f-102">Active Directory cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de1f-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5de1f-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5de1f-104">I cmdlet per Active Directory in genere vengono utilizzati dal programma di installazione e di rado vengono chiamati direttamente da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="5de1f-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="5de1f-105">Tuttavia, gli amministratori possono utilizzare questi cmdlet per preparare (o Depreparare) un dominio o una foresta per Microsoft Lync Server 2013 e per installare i file di schema di Active Directory necessari.</span><span class="sxs-lookup"><span data-stu-id="5de1f-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="5de1f-106">Cmdlet per Active Directory</span><span class="sxs-lookup"><span data-stu-id="5de1f-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="5de1f-107">Di seguito è riportato un elenco di cmdlet che si riferiscono direttamente alla gestione delle impostazioni di Active Directory di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5de1f-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="5de1f-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="5de1f-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-109">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-109">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-110">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-110">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-111">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-111">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5de1f-112">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-112">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-113">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-113">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-114">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-114">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5de1f-115">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-115">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5de1f-116">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5de1f-116">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5de1f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de1f-117">See Also</span></span>


[<span data-ttu-id="5de1f-118">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="5de1f-118">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

