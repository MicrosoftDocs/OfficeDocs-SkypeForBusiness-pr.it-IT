---
title: 'Lync Server 2013: topologie e componenti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e53116879e194bca7d0ea4066bc5f10de38f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="0aeb1-102">Topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0aeb1-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0aeb1-103">_**Ultimo argomento modificato:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="0aeb1-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="0aeb1-104">Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="0aeb1-p101">I Front End Server o i server Standard Edition dell'organizzazione. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-p101">Your organization’s Front End Servers or Standard Edition servers. IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="0aeb1-107">Un bilanciamento del carico, se si dispone di un pool Enterprise Edition front end.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="0aeb1-108">Per ulteriori informazioni, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="0aeb1-109">Pianificazione per la distribuzione di pool Front End</span><span class="sxs-lookup"><span data-stu-id="0aeb1-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="0aeb1-110">In Lync Server 2013, l'architettura del pool Front End è cambiata e queste modifiche influiscono su come pianificare e gestire i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="0aeb1-111">È consigliabile che tutti i pool Enterprise Edition front end includano almeno tre Front End Server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="0aeb1-112">In Lync Server, l'architettura dei pool Front end utilizza un modello di sistemi distribuiti, con i dati di ogni utente conservati su tre Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="0aeb1-113">Per ulteriori informazioni su questa nuova architettura, vedere [modifiche alla topologia in Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="0aeb1-114">Se non si desidera distribuire tre Front End Server Enterprise Edition e si desidera eseguire il ripristino di emergenza, è consigliabile utilizzare Lync Server Standard Edition e creare due pool con una relazione di backup associata.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="0aeb1-115">In questo modo verrà fornita una soluzione di ripristino di emergenza con solo due server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="0aeb1-116">Per ulteriori informazioni sulle topologie e le funzionalità di disponibilità elevata e ripristino di emergenza, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="0aeb1-117">Pianificazione per la gestione di pool Front End</span><span class="sxs-lookup"><span data-stu-id="0aeb1-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="0aeb1-118">Per i pool Front End, seguire le linee guida riportate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="0aeb1-119">Garantire che i pool siano funzionali</span><span class="sxs-lookup"><span data-stu-id="0aeb1-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="0aeb1-120">Con il nuovo modello distribuito per i pool Front End, è necessario che alcuni numeri dei server di un pool siano in esecuzione affinché il pool funzioni.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="0aeb1-121">Sono disponibili due modalità di perdita per un pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="0aeb1-122">Perdita di quorum a livello di gruppo di routing, causata da server di replica non sufficienti per un gruppo di routing specifico.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="0aeb1-123">Un gruppo di routing è un'aggregazione di un insieme di utenti ospitati nel pool.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="0aeb1-124">Ogni gruppo di routing ha tre repliche nel pool: una principale e due secondarie.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="0aeb1-125">Perdita di quorum a livello di pool, causata quando i server di seeding non sono sufficienti in esecuzione nel pool.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="0aeb1-126">Perdita di quorum a livello di gruppo di routing</span><span class="sxs-lookup"><span data-stu-id="0aeb1-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="0aeb1-127">La prima volta che si avvia un nuovo pool Front End, è essenziale che il 85% dei server sia attivo e in esecuzione, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="0aeb1-128">Se sono in esecuzione meno server, è possibile che i servizi siano bloccati nello stato iniziale e che il pool non venga avviato.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0aeb1-129">Numero totale di server nel pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="0aeb1-130">Numero di server che devono essere in esecuzione per l'avvio del pool per la prima volta</span><span class="sxs-lookup"><span data-stu-id="0aeb1-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-131">2 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-131">2</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-132">1 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-133">3 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-133">3</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-134">3 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-135">4 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-135">4</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-136">3 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-137">5 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-137">5</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-138">4 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-139">6 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-139">6</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-140">5 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-141">7 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-141">7</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-142">5 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-143">8 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-143">8</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-144">6 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-145">9 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-145">9</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-146">7 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-147">10 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-147">10</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-148">8 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-149">11 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-149">11</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-150">9 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-151">12</span><span class="sxs-lookup"><span data-stu-id="0aeb1-151">12</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-152">10 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0aeb1-153">Ogni volta che viene avviato il pool, 85% dei server devono essere avviati (come illustrato nella tabella precedente).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="0aeb1-154">Se non è possibile avviare questo numero di server, ma è possibile avviare server sufficienti in modo che non si trovino perdite di quorum a livello di pool, è possibile utilizzare il cmdlet **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** per consentire al pool di eseguire il ripristino dalla perdita del quorum a livello di gruppo di routing e progredire.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="0aeb1-155">Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0aeb1-156">Poiché Lync Server utilizza il database SQL primario come server di controllo, se si arresta il database primario e si passa alla copia del mirror e si arresta un numero sufficiente di front end server in modo che non sia sufficiente eseguire in base alla tabella precedente, l'intero pool passerà.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="0aeb1-157">Per ulteriori informazioni, vedere <A href="http://go.microsoft.com/fwlink/?linkid=393672">database mirroring witness</A>.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="0aeb1-158">Perdita di quorum a livello di pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-158">Pool-level quorum loss</span></span>

<span data-ttu-id="0aeb1-159">Affinché un pool Front end funzioni a tutti, non può essere in perdita di quorum a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="0aeb1-160">Se il numero di server in esecuzione scende al di sotto del livello di funzionalità, come illustrato nella tabella seguente, i server rimanenti del pool interromperanno tutti i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="0aeb1-161">Si noti che i numeri nella tabella seguente presuppongono che i server back-end del pool siano in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0aeb1-162">Numero totale di Front End Server nel pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="0aeb1-163">Numero minimo di server attivi per il funzionamento del pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-164">2 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-164">2</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-165">1 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-166">3-4</span><span class="sxs-lookup"><span data-stu-id="0aeb1-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-167">Qualsiasi 2</span><span class="sxs-lookup"><span data-stu-id="0aeb1-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-168">5-6</span><span class="sxs-lookup"><span data-stu-id="0aeb1-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-169">Qualsiasi 3</span><span class="sxs-lookup"><span data-stu-id="0aeb1-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-170">7 </span><span class="sxs-lookup"><span data-stu-id="0aeb1-170">7</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-171">Qualsiasi 4</span><span class="sxs-lookup"><span data-stu-id="0aeb1-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aeb1-172">8-9</span><span class="sxs-lookup"><span data-stu-id="0aeb1-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-173">Qualsiasi 4 dei primi 7 Server</span><span class="sxs-lookup"><span data-stu-id="0aeb1-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aeb1-174">10-12</span><span class="sxs-lookup"><span data-stu-id="0aeb1-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="0aeb1-175">Qualsiasi 5 dei primi 9 server</span><span class="sxs-lookup"><span data-stu-id="0aeb1-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0aeb1-176">Nella tabella precedente, i "First Server" sono i server che sono stati portati in primo luogo, in ordine cronologico, quando il pool è stato avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="0aeb1-177">Per determinare questi server, è possibile utilizzare il cmdlet **Get-CsComputer** con l'opzione **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="0aeb1-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="0aeb1-178">Questo cmdlet mostrerà i server nell'ordine in cui vengono visualizzati nella topologia e quelli nella parte superiore dell'elenco sono i primi server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="0aeb1-179">Pool Front End con due Front End Server</span><span class="sxs-lookup"><span data-stu-id="0aeb1-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="0aeb1-p112">Non è consigliabile distribuire un pool Front End contenente due soli Front End Server. Se fosse necessario distribuire questo tipo di pool, seguire queste indicazioni:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-p112">We do not recommend deploying a Front End pool that contains only two Front End Servers. If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="0aeb1-p113">Se uno dei due Front End Server si arresta, riattivarlo al più presto. Analogamente, se occorre aggiornare uno dei due server, riportarlo online subito dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-p113">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="0aeb1-184">Se per qualche ragione si rende necessario arrestare entrambi i server contemporaneamente, al termine dell'intervento procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="0aeb1-185">La procedura consigliata consiste nel riavviare entrambi i front end server contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="0aeb1-186">Se non è possibile riavviare entrambi i server contemporaneamente, riattivarli in ordine inverso rispetto a quello di arresto.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="0aeb1-187">Se non è possibile riattivarli nell'ordine consigliato, prima di riattivare il pool, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="0aeb1-188">Passaggi aggiuntivi per garantire che i pool siano funzionali</span><span class="sxs-lookup"><span data-stu-id="0aeb1-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="0aeb1-189">È consigliabile guardare un paio di altri fattori per garantire che i pool Front End rimangano funzionali.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="0aeb1-190">Quando si spostano gli utenti nel pool per la prima volta, assicurarsi che siano in esecuzione almeno tre Front End Server.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="0aeb1-191">Se si stabilisce una relazione di abbinamento tra questo pool e un altro pool ai fini del ripristino di emergenza, dopo aver stabilito la relazione è necessario verificare che in un determinato momento questo pool disponga di tre Front End Server in esecuzione simultanea per sincronizzare correttamente i dati con il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="0aeb1-192">Per ulteriori informazioni sulle funzionalità di abbinamento dei pool e ripristino di emergenza, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="0aeb1-193">Migliorare l'affidabilità degli aggiornamenti del pool</span><span class="sxs-lookup"><span data-stu-id="0aeb1-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="0aeb1-194">Quando è necessario aggiornare o applicare la patch ai server in un pool Front End, seguire il flusso di lavoro mostrato in [upgrade or Update Front End Servers in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="0aeb1-195">Quando si passa da un dominio di aggiornamento a un altro per gli aggiornamenti (dopo il flusso di lavoro in fase di [aggiornamento o aggiornamento dei front end server in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), si utilizzerà il cmdlet **Get-CsPoolUpgradeReadinessState** e si verificherà lo stato pronto.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="0aeb1-196">L'aggiunta di un'attesa di 20 minuti tra ogni dominio di aggiornamento dopo che raggiunge "Ready" renderà gli aggiornamenti più affidabili.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="0aeb1-197">Se non si è **pronti** durante questo periodo di 20 minuti, riavviare il timer di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="0aeb1-198">È inoltre possibile eseguire il cmdlet **Get-CsPoolFabricState** prima e dopo l'avvio dell'intervallo di 20 minuti e verificare che non siano presenti modifiche alle primarie e alle secondarie dei gruppi di routing.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="0aeb1-199">Non passare al dominio di aggiornamento successivo se uno qualsiasi dei server nell'ultimo dominio di aggiornamento con patch è bloccato o non riavviato.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="0aeb1-200">Questo si applica anche se non è possibile avviare uno dei server all'interno di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="0aeb1-201">Eseguire **Get-CsPoolFabricState** per verificare che tutti i gruppi di routing abbiano un primario e almeno un secondario; Ciò consentirà di verificare se tutti gli utenti dispongono di un servizio.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="0aeb1-202">Se alcuni utenti dispongono di un servizio e altri non lo fanno, eseguire **Get-CsPoolFabricState** con l'opzione – verbose per controllare i gruppi di routing che dispongono di repliche mancanti.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="0aeb1-203">Non riavviare l'intero pool come primo passaggio di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="0aeb1-204">Per ulteriori informazioni su questo cmdlet, vedere [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="0aeb1-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="0aeb1-205">Assicurarsi che tutte le istanze del Visualizzatore eventi o delle finestre di monitoraggio delle prestazioni siano chiuse per le installazioni/disinstallazioni di Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="0aeb1-206">Modifica della configurazione di un pool Front End</span><span class="sxs-lookup"><span data-stu-id="0aeb1-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="0aeb1-207">Quando si aggiungono o si rimuovono Front End Server da un pool e quindi si pubblica la nuova topologia, seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="0aeb1-208">Dopo la pubblicazione della nuova topologia, è necessario riavviare ogni Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="0aeb1-209">Riavviarli uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="0aeb1-210">Se durante le modifiche della configurazione è stato arrestato l'intero pool, dopo la pubblicazione della topologia eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0aeb1-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="0aeb1-p119">Se un Front End Server si guasta e si prevede che non verrà sostituito entro pochi giorni, rimuovere il server dalla topologia. Aggiungere il nuovo Front End Server alla topologia quando sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="0aeb1-p119">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

