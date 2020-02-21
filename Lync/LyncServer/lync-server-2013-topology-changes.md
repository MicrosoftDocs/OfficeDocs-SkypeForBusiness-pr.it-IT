---
title: Modifiche alla topologia di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac7cf9fe1bdabcba4b0b5fc1134f1835407041a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="7c279-102">Modifiche alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c279-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c279-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7c279-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7c279-104">I requisiti e le considerazioni sulla topologia per Lync Server 2013 sono diversi da quelli relativi alle versioni precedenti, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="7c279-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="7c279-105">Nuova architettura di pool Front End</span><span class="sxs-lookup"><span data-stu-id="7c279-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="7c279-106">In Lync Server 2013, l'architettura di pool Enterprise Edition front end è stata modificata in un'architettura di sistemi distribuiti.</span><span class="sxs-lookup"><span data-stu-id="7c279-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="7c279-107">Con questa nuova architettura, il database back-end non è più l'archivio dati in tempo reale in un pool.</span><span class="sxs-lookup"><span data-stu-id="7c279-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="7c279-108">Le informazioni relative a un determinato utente vengono conservate su tre Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="7c279-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="7c279-109">Per ogni utente, un front end server funge da master per le informazioni dell'utente e altri due server front end fungono da repliche.</span><span class="sxs-lookup"><span data-stu-id="7c279-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="7c279-110">Se un front end server viene abbassato, un altro front end server che funge da replica viene automaticamente promosso come master.</span><span class="sxs-lookup"><span data-stu-id="7c279-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="7c279-111">Questo accade dietro le quinte e gli amministratori non hanno bisogno di sapere quali front end server sono i master per cui gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7c279-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="7c279-112">Questa distribuzione dell'archiviazione dei dati consente di migliorare le prestazioni e la scalabilità all'interno del pool ed Elimina il singolo punto di errore di un singolo server back-end.</span><span class="sxs-lookup"><span data-stu-id="7c279-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="7c279-113">Il server back-end funge da archivio di backup per i dati degli utenti e delle conferenze ed è anche lo spazio di archiviazione principale per altri database, ad esempio il database di Response Group.</span><span class="sxs-lookup"><span data-stu-id="7c279-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="7c279-114">Questi miglioramenti indicano anche che sono presenti modifiche al modo in cui si pianificano e gestiscono i pool.</span><span class="sxs-lookup"><span data-stu-id="7c279-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="7c279-115">È consigliabile che tutti i pool Enterprise Edition front end includano almeno tre Front End Server, per fornire il numero completo di repliche per cui è progettata l'architettura del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="7c279-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="7c279-116">Inoltre, è necessario seguire determinate procedure quando si aggiungono server a un pool Front End, si rimuovono i server da esso o si aggiornano i server.</span><span class="sxs-lookup"><span data-stu-id="7c279-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="7c279-117">Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="7c279-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="7c279-118">Modifiche alla topologia del ruolo del server</span><span class="sxs-lookup"><span data-stu-id="7c279-118">Server Role Topology Changes</span></span>

<span data-ttu-id="7c279-119">Alcuni ruoli del server precedentemente eseguiti su server distinti sono ora consolidati nel ruolo front end server, consentendo di risparmiare sui costi hardware</span><span class="sxs-lookup"><span data-stu-id="7c279-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="7c279-120">In Lync Server 2013, A/V Conferencing Server è sempre collocato con Front End Server.</span><span class="sxs-lookup"><span data-stu-id="7c279-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="7c279-121">I front-end sia per il monitoraggio che per l'archiviazione sono ora collocati in un server front endpoint.</span><span class="sxs-lookup"><span data-stu-id="7c279-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="7c279-122">Monitoring and Archiving each richiedono ancora un database back-end separato, che può essere collocato nello stesso server del database back-end del pool Front end oppure può essere ospitato in server back-end separati.</span><span class="sxs-lookup"><span data-stu-id="7c279-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="7c279-123">Il server Chat persistente è ora un ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="7c279-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="7c279-124">In Microsoft Lync Server 2010, Group Chat Server era un'applicazione attendibile di terze parti per Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7c279-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="7c279-125">In Lync Server 2013, la funzionalità del server Chat persistente viene implementata utilizzando tre nuovi ruoli del server:</span><span class="sxs-lookup"><span data-stu-id="7c279-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="7c279-126">**PersistentChatService:** Principali servizi del server Chat persistente implementati come ruolo front-end</span><span class="sxs-lookup"><span data-stu-id="7c279-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="7c279-127">**PersistentChatStore:** Ruolo del server back-end</span><span class="sxs-lookup"><span data-stu-id="7c279-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="7c279-128">**PersistentChatComplianceStore:** Ruolo del server back-end per la conformità della chat persistente</span><span class="sxs-lookup"><span data-stu-id="7c279-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

