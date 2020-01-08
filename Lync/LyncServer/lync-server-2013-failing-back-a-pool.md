---
title: 'Lync Server 2013: Failback di un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Failback di un pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Dopo che il pool che ha sperimentato il disastro è di nuovo online, ovvero pool1 in questo esempio, eseguire la procedura seguente per ripristinare lo stato di lavoro normale.

Tieni presente che il processo di failback richiede diversi minuti per il completamento.Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.

1.  Non è possibile eseguire il failover degli utenti che erano stati originariamente ospitati in pool1 e che non hanno eseguito il failover di Pool2 digitando il cmdlet seguente:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Nessun altro passaggio è necessario. Se non è stato superato il server di gestione centrale, è possibile lasciarlo in Pool2.

</div>

<span> </span>

</div>

</div>

</div>

