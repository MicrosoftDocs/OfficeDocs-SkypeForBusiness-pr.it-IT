---
title: 'Lync Server 2013: risorse necessarie per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156a3ffef41782760124f0eb791cf2fdb71a1235
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511943"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="de7c8-102">Risorse necessarie per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7c8-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7c8-103">_**Ultimo argomento modificato:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="de7c8-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="de7c8-104">La disponibilità elevata e il ripristino di emergenza per il server Chat persistente richiedono ulteriori risorse oltre a ciò che in genere è necessario per l'operazione completa.</span><span class="sxs-lookup"><span data-stu-id="de7c8-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="de7c8-105">Prima di configurare il server Chat persistente per la disponibilità elevata e il ripristino di emergenza, verificare di disporre delle risorse seguenti oltre a quelle necessarie per l'operazione standard del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de7c8-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="de7c8-106">Per ulteriori informazioni sulla configurazione, vedere [Configuring Persistent Chat Server in Lync server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="de7c8-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="de7c8-107">Un'istanza di database dedicata che si trova nello stesso data center fisico in cui si trova l'Home Front-end del servizio server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de7c8-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="de7c8-108">Questo database fungerà da mirror di SQL Server per il database di Persistent Chat principale.</span><span class="sxs-lookup"><span data-stu-id="de7c8-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="de7c8-109">Facoltativamente, designare un ulteriore server SQL per fungere da controllo del mirroring se si desidera un failover automatizzato per il database mirror.</span><span class="sxs-lookup"><span data-stu-id="de7c8-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="de7c8-110">Un'istanza di database dedicata nell'altro data center fisico.</span><span class="sxs-lookup"><span data-stu-id="de7c8-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="de7c8-111">Questo database fungerà da database secondario di log shipping di SQL Server per il database nel data center principale.</span><span class="sxs-lookup"><span data-stu-id="de7c8-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="de7c8-112">Un'istanza di database dedicata che funge da mirror di SQL Server per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="de7c8-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="de7c8-113">Facoltativamente, è possibile designare un ulteriore SQL Server per il server come testimone del mirroring.</span><span class="sxs-lookup"><span data-stu-id="de7c8-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="de7c8-114">Entrambi devono trovarsi nello stesso data center fisico del database secondario.</span><span class="sxs-lookup"><span data-stu-id="de7c8-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="de7c8-115">Se è abilitata la conformità del server Chat persistente, sono necessarie altre tre istanze di database dedicate.</span><span class="sxs-lookup"><span data-stu-id="de7c8-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="de7c8-116">La distribuzione è identica a quella descritta in precedenza per il database di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="de7c8-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="de7c8-117">Sebbene sia possibile che il database di conformità condivida la stessa istanza di SQL Server del database di chat persistente, è consigliabile disporre di istanze autonome per la disponibilità elevata e il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="de7c8-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="de7c8-118">È necessario creare una condivisione file e designarla per i log delle transazioni di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de7c8-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="de7c8-119">Tutti i server SQL in entrambi i data center che eseguono i database di Persistent Chat devono avere accesso in lettura/scrittura alla condivisione di file.</span><span class="sxs-lookup"><span data-stu-id="de7c8-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="de7c8-120">Tale condivisione non è definita come parte di un ruolo FileStore.</span><span class="sxs-lookup"><span data-stu-id="de7c8-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="de7c8-121">Una condivisione file nel server di database secondario che funge da cartella di destinazione per i registri delle transazioni di SQL Server che vengono copiati dalla condivisione file del server primario.</span><span class="sxs-lookup"><span data-stu-id="de7c8-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de7c8-122">I server di chat persistente attivi in un pool di server Chat persistente devono risiedere nello stesso fuso orario del pool di Lync hop successivo definito nella topologia.</span><span class="sxs-lookup"><span data-stu-id="de7c8-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="de7c8-123">Nelle figure seguenti vengono forniti esempi di come è possibile configurare l'intero pool di server Chat persistente nelle due topologie di pool estese diverse:</span><span class="sxs-lookup"><span data-stu-id="de7c8-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="de7c8-124">Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.</span><span class="sxs-lookup"><span data-stu-id="de7c8-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="de7c8-125">Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.</span><span class="sxs-lookup"><span data-stu-id="de7c8-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="de7c8-126">Nella figura seguente viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con elevata larghezza di banda e bassa latenza.</span><span class="sxs-lookup"><span data-stu-id="de7c8-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="de7c8-127">**Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.**</span><span class="sxs-lookup"><span data-stu-id="de7c8-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="de7c8-128">![Esame di configurazione del pool di server Chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Esame di configurazione del pool di server Chat persistente HBW")</span><span class="sxs-lookup"><span data-stu-id="de7c8-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="de7c8-129">Nella figura seguente viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con una bassa larghezza di banda e un'elevata latenza</span><span class="sxs-lookup"><span data-stu-id="de7c8-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="de7c8-130">**Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.**</span><span class="sxs-lookup"><span data-stu-id="de7c8-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="de7c8-131">![Esame di configurazione del pool di server Chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Esame di configurazione del pool di server Chat persistente LBW")</span><span class="sxs-lookup"><span data-stu-id="de7c8-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

