---
title: 'Lync Server 2013: Failover di un database con mirroring'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Failover di un database con mirroring in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-14_

Se il database back-end è stato configurato per usare il mirroring sincronizzato con un testimone, il failover è automatico. Se è stato configurato il mirroring sincronizzato senza un testimone, è possibile usare le procedure seguenti per eseguire il failover e il failback del database. Puoi anche usare queste procedure per eseguire manualmente il failover e il failback dei database anche se hai configurato un testimone.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Per eseguire il failover del database back-end

1.  Prima di eseguire il failback, determinare quale database back-end è l'entità e quale mirror digitando il cmdlet seguente:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Se l'archivio di gestione centrale è ospitato in questo pool, digitare il cmdlet seguente per determinare quale è il principale e quale mirror per l'archivio di gestione centrale:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Eseguire il failover del database utente:
    
      - Se il principale non è riuscito e si esegue il failover verso il mirror, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Se il mirror non è riuscito e non si riesce a eseguire l'operazione principale, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Se il pool ospita il server di gestione centrale, eseguire il failover di Central Management store.
    
      - Se il principale non è riuscito e si esegue il failover verso il mirror, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Se il mirror non è riuscito e non si riesce a eseguire l'operazione principale, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

