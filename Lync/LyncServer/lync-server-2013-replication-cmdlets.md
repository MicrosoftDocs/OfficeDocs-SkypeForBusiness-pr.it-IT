---
title: 'Lync Server 2013: cmdlet di replica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8f5caecd5d80836f5abb5a4fef6ee4cf8a06494
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536343"
---
# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c68db-102">Cmdlet per la replica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c68db-102">Replication cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68db-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c68db-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c68db-104">I cmdlet di replica consentono di monitorare e gestire la replica di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c68db-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="c68db-105">È possibile utilizzare questi cmdlet per configurare le impostazioni della replica, monitorare lo stato della replica e forzare manualmente la replica in un server.</span><span class="sxs-lookup"><span data-stu-id="c68db-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="c68db-106">Cmdlet per la replica</span><span class="sxs-lookup"><span data-stu-id="c68db-106">Replication Cmdlets</span></span>

<span data-ttu-id="c68db-107">Di seguito è riportato un elenco di cmdlet direttamente correlati alla gestione della replica:</span><span class="sxs-lookup"><span data-stu-id="c68db-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="c68db-108">**Replica**</span><span class="sxs-lookup"><span data-stu-id="c68db-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="c68db-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c68db-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c68db-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c68db-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c68db-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c68db-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c68db-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c68db-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c68db-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c68db-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c68db-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c68db-118">See Also</span></span>


[<span data-ttu-id="c68db-119">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="c68db-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

