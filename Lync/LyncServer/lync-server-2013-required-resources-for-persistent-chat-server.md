---
title: 'Lync Server 2013: Risorse necessarie per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d1a6c-102">Risorse necessarie per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1a6c-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1a6c-103">_**Argomento Ultima modifica:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="d1a6c-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="d1a6c-104">La disponibilità elevata e il ripristino di emergenza per il server di chat persistente richiedono risorse aggiuntive oltre a quelle in genere necessarie per l'operazione completa.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="d1a6c-105">Prima di configurare il server di chat persistente per l'elevata disponibilità e il ripristino di emergenza, verificare di disporre delle risorse seguenti, oltre a quelle necessarie per l'operazione standard del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="d1a6c-106">Per altre informazioni sulla configurazione, vedere [configurazione del server di chat persistente in Lync server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1a6c-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="d1a6c-107">Un'istanza di database dedicata situata nello stesso centro dati fisico in cui si trova la parte anteriore iniziale del servizio server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="d1a6c-108">Questo database fungerà da mirror di SQL Server per il database principale della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="d1a6c-109">Facoltativamente, è possibile designare un altro server SQL per fungere da Witness per il mirroring se si vuole un failover automatizzato nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="d1a6c-110">Un'istanza di database dedicata situata nell'altro centro dati fisico.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="d1a6c-111">Questo database fungerà da database secondario di SQL Server log shipping per il database nel centro dati principale.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="d1a6c-112">Un'istanza del database dedicata che funge da mirror di SQL Server per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="d1a6c-113">Facoltativamente, è possibile designare un altro server SQL in server come witness di mirroring.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="d1a6c-114">Entrambi devono essere situati nello stesso centro dati fisico del database secondario.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="d1a6c-115">Se è abilitata la conformità del server di chat persistente, sono necessarie altre tre istanze di database dedicate.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="d1a6c-116">La distribuzione è uguale a quelle descritte in precedenza per il database della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="d1a6c-117">Mentre è possibile che il database di conformità condivida la stessa istanza di SQL Server del database della chat persistente, consigliamo istanze autonome per l'elevata disponibilità e il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="d1a6c-118">Una condivisione file deve essere creata e designata per i registri delle transazioni di log di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="d1a6c-119">Tutti i server SQL in entrambi i centri dati che eseguono database di chat permanenti devono avere accesso in lettura/scrittura alla condivisione file.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="d1a6c-120">Questa condivisione non è definita come parte di un ruolo di filestore.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="d1a6c-121">Una condivisione file nel server di database secondario per fungere da cartella di destinazione per i registri delle transazioni di SQL Server copiati dalla condivisione file del server principale.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1a6c-122">I server di chat permanenti attivi in un pool di server di chat persistente devono trovarsi nello stesso fuso orario del pool di Lync hop successivo definito nella topologia.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="d1a6c-123">Le figure seguenti illustrano come configurare l'intero pool di server di chat persistente nelle due topologie di pool estese diverse:</span><span class="sxs-lookup"><span data-stu-id="d1a6c-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="d1a6c-124">Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda elevata/bassa latenza.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="d1a6c-125">Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda ridotta/alta latenza.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="d1a6c-126">La figura seguente mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda elevata/bassa</span><span class="sxs-lookup"><span data-stu-id="d1a6c-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="d1a6c-127">**Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda elevata/bassa latenza.**</span><span class="sxs-lookup"><span data-stu-id="d1a6c-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="d1a6c-128">![](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Esame di configurazione") del pool di HBW PERSISTEnt chat server HBW</span><span class="sxs-lookup"><span data-stu-id="d1a6c-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="d1a6c-129">La figura seguente mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda ridotta/elevata.</span><span class="sxs-lookup"><span data-stu-id="d1a6c-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="d1a6c-130">**Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda ridotta/alta latenza.**</span><span class="sxs-lookup"><span data-stu-id="d1a6c-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="d1a6c-131">![](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Esame di configurazione") del pool di LBW PERSISTEnt chat server LBW</span><span class="sxs-lookup"><span data-stu-id="d1a6c-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

