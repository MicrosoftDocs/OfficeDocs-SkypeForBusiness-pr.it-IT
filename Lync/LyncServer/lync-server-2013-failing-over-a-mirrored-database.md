---
title: 'Lync Server 2013: failover di un database con mirroring'
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
ms.openlocfilehash: 853dfdd6786b4e30513cb57be219edff8d8c1b9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530973"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="da483-102">Failover di un database con mirroring in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da483-102">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da483-103">_**Ultimo argomento modificato:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="da483-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="da483-p101">Se è stato configurato il database back-end per l'utilizzo del mirroring sincronizzato con un'istanza di controllo, il failover è automatico. Se il mirroring sincronizzato è stato configurato senza istanza di controllo, è possibile utilizzare le procedure seguenti per il failover e failback del database. Queste procedure sono valide inoltre per eseguire il failover e failback manuale dei database anche quando è stata configurata un'istanza di controllo.</span><span class="sxs-lookup"><span data-stu-id="da483-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="da483-107">Per eseguire il failover del database back-end</span><span class="sxs-lookup"><span data-stu-id="da483-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="da483-108">Prima di eseguire il failover, determinare quale database back-end è quello principale, e quale è il mirror, utilizzando il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da483-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="da483-109">Se l'archivio di gestione centrale è ospitato in questo pool, digitare il seguente cmdlet per determinare qual è il principale e che è il mirror dell'archivio di gestione centrale:</span><span class="sxs-lookup"><span data-stu-id="da483-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="da483-110">Eseguire il failover del database utente:</span><span class="sxs-lookup"><span data-stu-id="da483-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="da483-111">Se il database primario non ha avuto esito positivo e si esegue il failover del mirror, digitare:</span><span class="sxs-lookup"><span data-stu-id="da483-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="da483-112">Se il mirror non ha avuto esito positivo e si esegue il failover del database primario, digitare:</span><span class="sxs-lookup"><span data-stu-id="da483-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="da483-113">Se il pool ospita il server di gestione centrale, eseguire il failover dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="da483-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="da483-114">Se il database primario non ha avuto esito positivo e si esegue il failover del mirror, digitare:</span><span class="sxs-lookup"><span data-stu-id="da483-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="da483-115">Se il mirror non ha avuto esito positivo e si esegue il failover del database primario, digitare:</span><span class="sxs-lookup"><span data-stu-id="da483-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

