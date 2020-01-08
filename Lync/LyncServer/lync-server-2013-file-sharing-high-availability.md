---
title: 'Lync Server 2013: disponibilità elevata della condivisione di file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="ef6f0-102">Disponibilità elevata della condivisione di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef6f0-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef6f0-103">_**Argomento Ultima modifica:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="ef6f0-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="ef6f0-104">Per garantire la disponibilità elevata per la condivisione di file di Lync Server all'interno di un singolo centro dati, è possibile usare il file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="ef6f0-105">DFS supporta il failover da un file server a un altro nello stesso centro dati.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="ef6f0-106">Per una distribuzione su larga scala, è consigliabile usare i file server dedicati abbinati tramite DFS.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="ef6f0-107">A seconda delle dimensioni della rete e della quantità di flessibilità desiderata, è possibile usare una coppia di server per ospitare tutte le condivisioni di file in un sito oppure usare una coppia per ogni pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="ef6f0-108">DFS è un meccanismo di replica dei file di massimo sforzo, senza l'impegno per i tempi di recupero pubblicato (RTO) o RPO (Recovery Point Objective).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="ef6f0-109">Il failover tra i server DFS deve essere completato in modo rapido, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando il failover si verifica.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="ef6f0-110">Se si usa DFS e archivio dati per la condivisione di file è fondamentale, è consigliabile eseguire il backup delle condivisioni, ad esempio ogni 4 o 8 ore.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="ef6f0-111">Quando si abbassa una condivisione file e la replica non è aggiornata, è possibile usare il backup per ripristinare il contenuto del server non riuscito con l'altro server associato al server che ora non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

