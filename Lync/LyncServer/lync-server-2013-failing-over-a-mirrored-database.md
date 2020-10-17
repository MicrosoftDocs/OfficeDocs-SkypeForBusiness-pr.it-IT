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
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Failover di un database con mirroring in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-14_

Se è stato configurato il database back-end per l'utilizzo del mirroring sincronizzato con un'istanza di controllo, il failover è automatico. Se il mirroring sincronizzato è stato configurato senza istanza di controllo, è possibile utilizzare le procedure seguenti per il failover e failback del database. Queste procedure sono valide inoltre per eseguire il failover e failback manuale dei database anche quando è stata configurata un'istanza di controllo.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Per eseguire il failover del database back-end

1.  Prima di eseguire il failover, determinare quale database back-end è quello principale, e quale è il mirror, utilizzando il seguente cmdlet:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Se l'archivio di gestione centrale è ospitato in questo pool, digitare il seguente cmdlet per determinare qual è il principale e che è il mirror dell'archivio di gestione centrale:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Eseguire il failover del database utente:
    
      - Se il database primario non ha avuto esito positivo e si esegue il failover del mirror, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Se il mirror non ha avuto esito positivo e si esegue il failover del database primario, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Se il pool ospita il server di gestione centrale, eseguire il failover dell'archivio di gestione centrale.
    
      - Se il database primario non ha avuto esito positivo e si esegue il failover del mirror, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Se il mirror non ha avuto esito positivo e si esegue il failover del database primario, digitare:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

