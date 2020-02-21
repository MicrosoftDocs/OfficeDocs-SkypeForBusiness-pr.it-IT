---
title: 'Lync Server 2013: disponibilità elevata del server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335f7680a98eb53414a8b438975d79327b515946
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="8579c-102">Disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8579c-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8579c-103">_**Ultimo argomento modificato:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="8579c-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="8579c-104">Per garantire una disponibilità elevata per i server back-end, è possibile utilizzare il mirroring SQL sincrono o il clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="8579c-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="8579c-105">L'utilizzo di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8579c-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="8579c-106">Il mirroring asincrono SQL non è supportato per la disponibilità elevata del server back-end in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8579c-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="8579c-107">In questo documento qualsiasi riferimento al mirroring SQL sottintende il mirroring SQL sincrono, a meno che non venga specificato diversamente.</span><span class="sxs-lookup"><span data-stu-id="8579c-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="8579c-108">È possibile configurare facilmente il mirroring SQL con generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8579c-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="8579c-109">Per il clustering di failover SQL, è necessario utilizzare SQL Server per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="8579c-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="8579c-110">Se si utilizza il mirroring SQL o il clustering SQL in un pool che è associato a un altro pool Front end per il ripristino di emergenza, è consigliabile utilizzare la stessa soluzione di disponibilità elevata back-end in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="8579c-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="8579c-111">Non è necessario accoppiare un pool utilizzando il mirroring SQL con un pool che utilizza il clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="8579c-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="8579c-112">Quando si distribuisce il mirroring SQL, tutti i database di Lync Server nel pool vengono sottoposti a mirroring, incluso l'archivio di gestione centrale, se si trova in questo pool, nonché il database dell'applicazione Response Group e il database dell'applicazione Parcheggio di chiamata, se tali applicazioni sono in esecuzione nel pool.</span><span class="sxs-lookup"><span data-stu-id="8579c-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="8579c-p104">Con il mirroring SQL, non è necessario utilizzare l'archiviazione condivisa per i server. Ogni server mantiene la propria copia dei database nello spazio di archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="8579c-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="8579c-p105">È possibile scegliere di distribuire il mirroring SQL con o senza controllo. È consigliabile utilizzare un server di controllo poiché consente il failover automatico del server back-end. In caso contrario, un amministratore deve richiamare manualmente il failover. Se noti che anche se è distribuito un server di controllo, un amministratore può comunque richiamare manualmente il failover del server back-end, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8579c-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="8579c-p106">Se si dispone di un server di controllo, è possibile utilizzare un singolo server di controllo per più coppie di server back-end. Non esiste una corrispondenza esatta tra server di controllo e coppie di server back-end. Le distribuzioni in cui viene utilizzato un singolo server di controllo per più coppie di server back-end non sono resilienti quanto le topologie con un server di controllo separato per ogni coppia di server back-end.</span><span class="sxs-lookup"><span data-stu-id="8579c-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="8579c-122">Per ulteriori informazioni sul supporto del clustering SQL, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="8579c-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="8579c-123">Per informazioni dettagliate sulla distribuzione del clustering SQL, vedere [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="8579c-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="8579c-124">Tempo di ripristino per il failover automatico del server back-end con il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="8579c-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="8579c-125">Per il failover automatico del back-end con il mirroring SQL, la destinazione ingegneristica per l'obiettivo del tempo di ripristino (RTO) è di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="8579c-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="8579c-126">A causa del mirroring SQL sincrono, non è prevista una perdita di dati in caso di errori di server back-end, eccetto in rari casi in cui si verifica un problema simultaneo dei Front End Server e del server back-end durante il trasferimento di dati tra i server.</span><span class="sxs-lookup"><span data-stu-id="8579c-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="8579c-127">L'obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="8579c-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="8579c-128">Esperienza utente durante un errore del server back-end con il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="8579c-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="8579c-129">L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="8579c-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="8579c-130">Se si utilizza il mirroring SQL e si dispone di un controllo configurato e l'entità ha esito negativo, il failover del server back-end avviene automaticamente e rapidamente.</span><span class="sxs-lookup"><span data-stu-id="8579c-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="8579c-131">Gli utenti attivi non dovrebbero osservare un'interruzione delle sessioni in corso.</span><span class="sxs-lookup"><span data-stu-id="8579c-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="8579c-132">Se invece non è configurato alcun server di controllo, l'amministratore necessiterà del tempo previsto per richiamare manualmente il failover.</span><span class="sxs-lookup"><span data-stu-id="8579c-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="8579c-133">Durante questo intervallo è possibile che gli utenti attivi subiscano alcuni disagi.</span><span class="sxs-lookup"><span data-stu-id="8579c-133">During that time, active users may be affected.</span></span> <span data-ttu-id="8579c-134">Continueranno a utilizzare normalmente le sessioni per circa 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="8579c-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="8579c-135">Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono passati alla modalità di resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica permanente su Lync Server, ad esempio l'aggiunta di un contatto.</span><span class="sxs-lookup"><span data-stu-id="8579c-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="8579c-p111">Se si verifica un errore sia del server principale che dei server back-end mirror oppure di uno di questi server e del server di controllo, il server back-end non sarà disponibile (anche se il server principale è ancora in funzione). In questo caso, gli utenti attivi passano alla modalità resilienza dopo un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8579c-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

