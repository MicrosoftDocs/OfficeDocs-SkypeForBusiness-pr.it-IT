---
title: 'Lync Server 2013: Failover di un database con mirroring'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="55c9c-102">Failover di un database con mirroring in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c9c-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55c9c-103">_**Argomento Ultima modifica:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="55c9c-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="55c9c-104">Se il database back-end è stato configurato per usare il mirroring sincronizzato con un testimone, il failover è automatico.</span><span class="sxs-lookup"><span data-stu-id="55c9c-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="55c9c-105">Se è stato configurato il mirroring sincronizzato senza un testimone, è possibile usare le procedure seguenti per eseguire il failover e il failback del database.</span><span class="sxs-lookup"><span data-stu-id="55c9c-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="55c9c-106">Puoi anche usare queste procedure per eseguire manualmente il failover e il failback dei database anche se hai configurato un testimone.</span><span class="sxs-lookup"><span data-stu-id="55c9c-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="55c9c-107">Per eseguire il failover del database back-end</span><span class="sxs-lookup"><span data-stu-id="55c9c-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="55c9c-108">Prima di eseguire il failback, determinare quale database back-end è l'entità e quale mirror digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="55c9c-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="55c9c-109">Se l'archivio di gestione centrale è ospitato in questo pool, digitare il cmdlet seguente per determinare quale è il principale e quale mirror per l'archivio di gestione centrale:</span><span class="sxs-lookup"><span data-stu-id="55c9c-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="55c9c-110">Eseguire il failover del database utente:</span><span class="sxs-lookup"><span data-stu-id="55c9c-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="55c9c-111">Se il principale non è riuscito e si esegue il failover verso il mirror, digitare:</span><span class="sxs-lookup"><span data-stu-id="55c9c-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="55c9c-112">Se il mirror non è riuscito e non si riesce a eseguire l'operazione principale, digitare:</span><span class="sxs-lookup"><span data-stu-id="55c9c-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="55c9c-113">Se il pool ospita il server di gestione centrale, eseguire il failover di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="55c9c-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="55c9c-114">Se il principale non è riuscito e si esegue il failover verso il mirror, digitare:</span><span class="sxs-lookup"><span data-stu-id="55c9c-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="55c9c-115">Se il mirror non è riuscito e non si riesce a eseguire l'operazione principale, digitare:</span><span class="sxs-lookup"><span data-stu-id="55c9c-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

