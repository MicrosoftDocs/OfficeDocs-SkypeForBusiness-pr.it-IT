---
title: 'Lync Server 2013: disponibilità elevata del server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f65ae3f476e81868619fa8d8d92ed60c71ce767d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="5e5ac-102">Disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e5ac-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e5ac-103">_**Argomento Ultima modifica:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="5e5ac-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="5e5ac-104">Per garantire una disponibilità elevata per i server back-end, è possibile usare il mirroring SQL sincrono o il clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="5e5ac-105">L'uso di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="5e5ac-106">Il mirroring asincrono di SQL non è supportato per la disponibilità elevata del server back-end in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="5e5ac-107">Nel resto di questo documento, il mirroring SQL indica il mirroring SQL sincrono, a meno che non sia specificato diversamente esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="5e5ac-108">È possibile configurare facilmente il mirroring SQL con generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="5e5ac-109">Per la configurazione del clustering di failover SQL, è necessario usare SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="5e5ac-110">Se si usa il mirroring SQL o il clustering SQL in un pool associato a un altro pool Front-end per il ripristino di emergenza, è consigliabile usare la stessa soluzione di disponibilità elevata di back-end in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="5e5ac-111">Non è consigliabile associare un pool tramite il mirroring SQL con un pool tramite il clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="5e5ac-112">Quando si distribuisce il mirroring SQL, tutti i database di Lync Server nel pool vengono speculati, incluso l'Central Management store, se si trova in questo pool, nonché il database dell'applicazione del gruppo di risposte e il database dell'applicazione Parcheggio di chiamata, se tali applicazioni vengono eseguiti nel pool.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="5e5ac-113">Con il mirroring SQL, non è necessario usare lo spazio di archiviazione condiviso per i server.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="5e5ac-114">Ogni server mantiene la copia dei database in uno spazio di archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="5e5ac-115">È possibile scegliere di distribuire il mirroring SQL con o senza un testimone.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="5e5ac-116">È consigliabile usare un testimone perché consente il failover del server back-end come automatico.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="5e5ac-117">In caso contrario, un amministratore deve richiamare manualmente il failover.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="5e5ac-118">Tieni presente che anche se viene distribuito un testimone, un amministratore può richiamare manualmente il failover del server di back-end, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="5e5ac-119">Se si usa un testimone, è possibile usare un solo testimone per più coppie di server back-end.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-119">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="5e5ac-120">Non esiste una stretta corrispondenza di 1:1 tra i testimoni e le coppie di server back-end.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-120">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="5e5ac-121">Le distribuzioni che usano un singolo Witness per più coppie di server back-end non sono abbastanza resilienti come le topologie con un testimone separato per ogni coppia di server back-end.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-121">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="5e5ac-122">Per altre informazioni sul supporto del clustering SQL, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="5e5ac-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="5e5ac-123">Per informazioni dettagliate sulla distribuzione del clustering SQL, vedere [configurare il clustering di SQL Server per Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="5e5ac-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="5e5ac-124">Tempo di recupero per il failover automatico del server back-end con il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="5e5ac-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="5e5ac-125">Per il failover automatico del back-end con il mirroring SQL, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="5e5ac-126">A causa del mirroring SQL sincrono, non anticipiamo la perdita di dati durante gli errori del server back-end, tranne in rare occasioni in cui entrambi i server front-end e il server back-end scendono contemporaneamente mentre i dati vengono spostati tra i server.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="5e5ac-127">La destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="5e5ac-128">Esperienza utente durante l'errore del server back-end con il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="5e5ac-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="5e5ac-129">L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="5e5ac-130">Se si usa il mirroring SQL e si configura un testimone e l'entità non riesce, il failover del server di back-end avviene automaticamente e rapidamente.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="5e5ac-131">Gli utenti attivi non dovrebbero notare molte interruzioni delle sessioni in corso.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="5e5ac-132">Se non sono configurati i testimoni, sarà necessario un po' di tempo prima che l'amministratore richiami manualmente il failover.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="5e5ac-133">Durante tale periodo gli utenti attivi potrebbero essere interessati.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-133">During that time, active users may be affected.</span></span> <span data-ttu-id="5e5ac-134">Continueranno le loro sessioni normalmente per circa 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="5e5ac-135">Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono convertiti in modalità resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica persistente in Lync Server, ad esempio l'aggiunta di un contatto.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="5e5ac-136">Se i server di back-end di Principal e mirror non riescono o se uno di questi server e il witness non riescono, il server back-end diventerà non disponibile (anche se è l'entità che sta ancora lavorando).</span><span class="sxs-lookup"><span data-stu-id="5e5ac-136">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="5e5ac-137">In questo caso, dopo qualche tempo, gli utenti attivi vengono convertiti in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="5e5ac-137">In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

