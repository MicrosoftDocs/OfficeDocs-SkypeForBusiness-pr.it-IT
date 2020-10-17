---
title: 'Lync Server 2013: disponibilità elevata della condivisione di file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f58cd52da92e767357e7a0bee7f3584552c9868
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531983"
---
# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="7dd71-102">Disponibilità elevata della condivisione di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dd71-102">File sharing high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd71-103">_**Ultimo argomento modificato:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="7dd71-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="7dd71-104">Per garantire la disponibilità elevata per la condivisione dei file di Lync Server in un unico Data Center, è possibile utilizzare il file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="7dd71-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="7dd71-105">DFS supporta il failover da un file server a un altro all'interno dello stesso data center.</span><span class="sxs-lookup"><span data-stu-id="7dd71-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="7dd71-106">Per una distribuzione su larga scala, è consigliabile utilizzare file server dedicati accoppiati mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="7dd71-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="7dd71-107">A seconda delle dimensioni della rete e del grado di resilienza desiderato, è possibile utilizzare una coppia di server per ospitare tutte le condivisioni file in un sito oppure utilizzare una coppia per ogni pool Front End.</span><span class="sxs-lookup"><span data-stu-id="7dd71-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="7dd71-p102">DFS è un meccanismo che esegue la replica nel miglior modo possibile in base alle condizioni esistenti, senza alcun impegno pubblicato relativamente al raggiungimento degli obiettivi in termini di tempo di ripristino (RTO, Recovery Time Objective) o di punto di ripristino (RPO, Recovery Point Objective). Il failover tra i server DFS dovrebbe avvenire rapidamente, ma il ritardo della replica dei dati può impedire agli utenti di proseguire con il lavoro che stavano svolgendo quando si verifica il failover.</span><span class="sxs-lookup"><span data-stu-id="7dd71-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="7dd71-p103">Se si utilizza DFS e l'archivio dati nella condivisione file è importante, è consigliabile eseguire frequentemente il backup delle condivisioni file, ad esempio ogni 4-8 ore. Quando una condivisione file non è più attiva e la replica non è aggiornata, è possibile utilizzare il backup per ripristinare il contenuto del server con problemi nell'altro server accoppiato al server attualmente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="7dd71-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

