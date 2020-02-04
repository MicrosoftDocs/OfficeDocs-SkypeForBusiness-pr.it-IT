---
title: Pianificazione della capacità di Lync Server 2013 con i modelli utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="60139-102">Pianificazione della capacità per Lync Server 2013 con i modelli utente</span><span class="sxs-lookup"><span data-stu-id="60139-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60139-103">_**Argomento Ultima modifica:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="60139-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="60139-104">In questa sezione vengono fornite indicazioni su quanti server sono necessari in un sito per il numero di utenti in tale sito, in base all'uso descritto nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="60139-105">Piattaforma hardware testata</span><span class="sxs-lookup"><span data-stu-id="60139-105">Tested Hardware Platform</span></span>

<span data-ttu-id="60139-106">Tutti i risultati delle prestazioni e i suggerimenti per la distribuzione in questa sezione sono basati sul test delle prestazioni nei server che usano l'hardware descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="60139-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="60139-107">Ti consigliamo di usare hardware simile.</span><span class="sxs-lookup"><span data-stu-id="60139-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="60139-108">Se usi hardware meno potente, potresti riscontrare problemi di funzionalità o prestazioni scarse.</span><span class="sxs-lookup"><span data-stu-id="60139-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="60139-109">Tieni presente che queste raccomandazioni hardware sono superiori a quelle delle versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60139-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="60139-110">Hardware usato nei test delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="60139-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-111">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="60139-111">Hardware component</span></span></th>
<th><span data-ttu-id="60139-112">Consigliato</span><span class="sxs-lookup"><span data-stu-id="60139-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-113">CPU</span><span class="sxs-lookup"><span data-stu-id="60139-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="60139-114">processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore</span><span class="sxs-lookup"><span data-stu-id="60139-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="60139-115">I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</span><span class="sxs-lookup"><span data-stu-id="60139-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-116">Memoria</span><span class="sxs-lookup"><span data-stu-id="60139-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="60139-117">32 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="60139-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-118">Disco</span><span class="sxs-lookup"><span data-stu-id="60139-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60139-119">8 o più unità disco rigido di 10.000-RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="60139-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="60139-120">Due dischi dovrebbero usare RAID 1 e sei dovrebbero usare RAID 10.</span><span class="sxs-lookup"><span data-stu-id="60139-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="60139-121">-O</span><span class="sxs-lookup"><span data-stu-id="60139-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="60139-122">SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 8 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="60139-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-123">Rete</span><span class="sxs-lookup"><span data-stu-id="60139-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60139-124">1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="60139-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="60139-125">Riepilogo dei risultati</span><span class="sxs-lookup"><span data-stu-id="60139-125">Summary of Results</span></span>

<span data-ttu-id="60139-126">Nella tabella seguente vengono riepilogati questi suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="60139-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-127">Ruolo del server</span><span class="sxs-lookup"><span data-stu-id="60139-127">Server role</span></span></th>
<th><span data-ttu-id="60139-128">Numero massimo di utenti supportati</span><span class="sxs-lookup"><span data-stu-id="60139-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-129">Pool Front end con dodici server front-end e un server back-end o una coppia speculare di server back-end.</span><span class="sxs-lookup"><span data-stu-id="60139-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="60139-130">80.000 utenti univoci collegati contemporaneamente, più 50% più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 152.000 endpoint.</span><span class="sxs-lookup"><span data-stu-id="60139-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-131">Servizi di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="60139-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="60139-132">Il servizio di conferenza A/V fornito da un pool di front-end supporta le conferenze del pool che presuppongono una dimensione massima per la conferenza di 250 utenti e una sola Conferenza di grandi dimensioni in esecuzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="60139-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="60139-133">È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front-end separato con due server front-end per ospitare le conferenze di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="60139-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="60139-134">Per informazioni dettagliate, vedere <A href="lync-server-2013-supporting-large-meetings.md">supporto di riunioni di grandi dimensioni tramite Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="60139-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-135">Un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="60139-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="60139-136">12.000 utenti remoti simultanei</span><span class="sxs-lookup"><span data-stu-id="60139-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-137">Un amministratore</span><span class="sxs-lookup"><span data-stu-id="60139-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="60139-138">12.000 utenti remoti simultanei</span><span class="sxs-lookup"><span data-stu-id="60139-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-139">Monitoraggio e archiviazione</span><span class="sxs-lookup"><span data-stu-id="60139-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="60139-140">In Lync Server 2013 i servizi front end di monitoraggio e archiviazione vengono ora eseguiti in ogni server front-end, anziché in ruoli server distinti.</span><span class="sxs-lookup"><span data-stu-id="60139-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="60139-141">Il monitoraggio e l'archiviazione di ognuno richiede ancora i propri archivi di database.</span><span class="sxs-lookup"><span data-stu-id="60139-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="60139-142">Se si esegue anche Exchange 2013, è possibile conservare i dati di archiviazione in Exchange, anziché in un database SQL dedicato.</span><span class="sxs-lookup"><span data-stu-id="60139-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-143">Un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="60139-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="60139-144">Mediation Server collocato con Front End Server viene eseguito in tutti i server front-end di un pool e dovrebbe avere sufficiente capacità per gli utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="60139-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="60139-145">Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="60139-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-146">Un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="60139-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="60139-147">Se si usano Server Standard Edition per ospitare gli utenti, è consigliabile usare sempre due server, abbinati con i suggerimenti <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">per la pianificazione della disponibilità elevata e il ripristino di emergenza in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="60139-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="60139-148">Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server non riesce, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.</span><span class="sxs-lookup"><span data-stu-id="60139-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="60139-149">Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono avere più di 2.500 utenti per server.</span><span class="sxs-lookup"><span data-stu-id="60139-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="60139-150">In questo caso, è consigliabile aggiungere più server Standard Edition o passare a Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="60139-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="60139-151">Server front-end</span><span class="sxs-lookup"><span data-stu-id="60139-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-152">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="60139-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="60139-153">In un pool Front-End è necessario disporre di un server front-end per ogni utente di 6.660 ospitato nel pool, presupponendo che l'Hyper-Threading sia abilitato in tutti i server del pool e che l'hardware del server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="60139-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="60139-154">Il numero massimo di utenti in un pool Front-End è 80.000, presupponendo che l'Hyper-Threading sia abilitato in tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="60139-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="60139-155">Se si hanno più di 80.000 utenti in un sito, è possibile distribuire più di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="60139-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="60139-156">Quando si tiene conto del numero di utenti in un pool Front-End, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a questo pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="60139-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="60139-157">Quando un server attivo non è disponibile, le connessioni vengono trasferite automaticamente agli altri server del pool.</span><span class="sxs-lookup"><span data-stu-id="60139-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="60139-158">Ad esempio, se si hanno 30.000 utenti e cinque server front-end, se un server non è disponibile, le connessioni degli utenti di 6000 devono essere trasferite agli altri quattro server.</span><span class="sxs-lookup"><span data-stu-id="60139-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="60139-159">I quattro server rimanenti avranno tutti gli utenti di 7500, che è un numero più grande di quello raccomandato.</span><span class="sxs-lookup"><span data-stu-id="60139-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="60139-160">Se invece si è iniziato con sei server front-end per gli utenti di 30.000 e in seguito non è più disponibile, per un totale di 5000 gli utenti verranno spostati nei cinque server rimanenti.</span><span class="sxs-lookup"><span data-stu-id="60139-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="60139-161">Questi cinque server conterranno tutti gli utenti di 6000, che si trova nell'intervallo consigliato.</span><span class="sxs-lookup"><span data-stu-id="60139-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="60139-162">Il numero massimo di utenti in un pool Front-End è 80.000.</span><span class="sxs-lookup"><span data-stu-id="60139-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="60139-163">Il numero massimo di server front-end in un pool è 12.</span><span class="sxs-lookup"><span data-stu-id="60139-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="60139-164">Per un pool Front-end con gli utenti di 80.000, dodici server front-end sono sufficienti per le prestazioni, in distribuzioni tipiche che seguono i [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="60139-165">Le distribuzioni progettate per supportare il failover del ripristino di emergenza presuppongono che un massimo di 40.000 utenti possano essere ospitati in ognuno dei due pool Front-End associati, in cui ogni pool ha sufficienti server front-end per ospitare gli utenti in entrambi i pool in caso di necessità di un pool non riuscito verso l'altro.</span><span class="sxs-lookup"><span data-stu-id="60139-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="60139-166">Il numero di utenti supportati con prestazioni ottimali per un determinato pool Front-end può essere diverso da questi numeri per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="60139-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="60139-167">L'hardware per i server front-end non soddisfa le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="60139-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="60139-168">L'utilizzo dell'organizzazione differisce in modo significativo dai modelli utente, ad esempio il traffico di conferenze più significativo.</span><span class="sxs-lookup"><span data-stu-id="60139-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60139-169">In Lync Server 2013 i database di presenza sono ora ospitati nei server front-end, a differenza di Lync Server 2010 in cui erano ospitati nel server back-end.</span><span class="sxs-lookup"><span data-stu-id="60139-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="60139-170">Ciò significa che le prestazioni del disco e la capacità dei server front-end non devono essere compromesse dalle raccomandazioni elencate in precedenza in questa sezione e nelle <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware del server per Lync server 2013</A>, indipendentemente dal numero di utenti ospitati dai server front-end.</span><span class="sxs-lookup"><span data-stu-id="60139-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="60139-171">La tabella seguente mostra la larghezza di banda media per la messaggistica istantanea e la presenza, dato il modello utente, come definito nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-172">Larghezza di banda media per utente</span><span class="sxs-lookup"><span data-stu-id="60139-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="60139-173">Requisiti di larghezza di banda per server front-end con utenti di 6.660</span><span class="sxs-lookup"><span data-stu-id="60139-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-174">1,3 kpbs</span><span class="sxs-lookup"><span data-stu-id="60139-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="60139-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="60139-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="60139-176">Per migliorare le prestazioni multimediali della funzionalità di conferenza A/V Conferencing e Mediation Server co-ubicata nei server front-end, è necessario abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="60139-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="60139-177">RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server.</span><span class="sxs-lookup"><span data-stu-id="60139-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="60139-178">Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60139-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="60139-179">Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="60139-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="60139-180">Massimali per le conferenze</span><span class="sxs-lookup"><span data-stu-id="60139-180">Conferencing Maximums</span></span>

<span data-ttu-id="60139-181">Considerato il modello utente in cui il 5% degli utenti di un pool può partecipare a una conferenza in qualsiasi momento, un pool di utenti di 80.000 potrebbe avere circa 4.000 utenti in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="60139-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="60139-182">Queste conferenze dovrebbero essere una combinazione di elementi multimediali (alcuni messaggi istantanei, alcuni messaggi istantanei con audio, alcuni audio/video, ad esempio) e il numero di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="60139-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="60139-183">Non esiste alcun limite per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive.</span><span class="sxs-lookup"><span data-stu-id="60139-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="60139-184">Ad esempio, se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end o A/V Conferencing Server rispetto ai suggerimenti di questo documento.</span><span class="sxs-lookup"><span data-stu-id="60139-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="60139-185">Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="60139-186">La dimensione massima della conferenza supportata ospitata da un normale pool di front end di Lync Server 2013 che ospita anche utenti è di 250 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="60139-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="60139-187">Mentre è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che un totale del 5% degli utenti del pool si trovi in conferenze simultanee.</span><span class="sxs-lookup"><span data-stu-id="60139-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="60139-188">Ad esempio, in un pool di dodici server front-end e utenti di 80.000, mentre la conferenza per utenti di 250 sta accadendo, Lync Server supporta 3.750 altri utenti che partecipano a conferenze più piccole.</span><span class="sxs-lookup"><span data-stu-id="60139-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="60139-189">Indipendentemente dal numero di utenti ospitati nel pool Front-end o in un server Standard Edition, Lync Server supporta un minimo di 125 di altri utenti che partecipano a conferenze più piccole nello stesso pool o server in cui è in uso una conferenza di 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="60139-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="60139-190">Per abilitare le conferenze tra gli utenti di 250 e 1000, è possibile configurare un pool Front-end separato solo per ospitare tali conferenze.</span><span class="sxs-lookup"><span data-stu-id="60139-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="60139-191">Questo pool Front-end non ospiterà alcun utente.</span><span class="sxs-lookup"><span data-stu-id="60139-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="60139-192">Per informazioni dettagliate, vedere [supporto di riunioni di grandi dimensioni tramite Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="60139-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="60139-193">Se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end rispetto alle raccomandazioni del documento (fino a un massimo di 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="60139-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="60139-194">Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="60139-195">Edge Server</span><span class="sxs-lookup"><span data-stu-id="60139-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-196">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="60139-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="60139-197">Devi distribuire un server perimetrale per ogni utente remoto di 12.000 che accede simultaneamente a un sito.</span><span class="sxs-lookup"><span data-stu-id="60139-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="60139-198">È consigliabile almeno due server Edge per una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="60139-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="60139-199">Queste raccomandazioni presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="60139-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="60139-200">Quando si tiene conto del numero di utenti per gli Edge Server, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.</span><span class="sxs-lookup"><span data-stu-id="60139-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-201">Per migliorare le prestazioni del servizio A/V Conferencing Edge in un server perimetrale, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete degli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="60139-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="60139-202">RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server.</span><span class="sxs-lookup"><span data-stu-id="60139-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="60139-203">Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60139-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="60139-204">Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="60139-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="60139-205">Director</span><span class="sxs-lookup"><span data-stu-id="60139-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-206">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="60139-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="60139-207">Se si distribuisce il ruolo Director Server, è consigliabile distribuire un amministratore per ogni utente remoto di 12.000 che accede contemporaneamente a un sito.</span><span class="sxs-lookup"><span data-stu-id="60139-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="60139-208">Consigliamo almeno due direttori per una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="60139-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="60139-209">Queste raccomandazioni presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="60139-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="60139-210">Quando si tiene conto del numero di utenti per gli amministratori, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.</span><span class="sxs-lookup"><span data-stu-id="60139-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="60139-211">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="60139-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-212">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="60139-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="60139-213">Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i server front-end del pool e deve avere sufficiente capacità per gli utenti del pool.</span><span class="sxs-lookup"><span data-stu-id="60139-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="60139-214">Se si distribuisce un pool di Mediation Server autonomo, il numero di server di mediazione da distribuire dipende da molti fattori, tra cui l'hardware usato per Mediation Server, il numero di utenti VoIP che si ha, la quantità di peer del gateway che ogni pool di Mediation Server controlli, il traffico ora occupato attraverso i gateway e la percentuale di chiamate con elementi multimediali che ignorano il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="60139-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="60139-215">Le tabelle seguenti includono una linea guida per il numero di chiamate simultanee che possono essere gestite da un Mediation Server, presupponendo che l'hardware per i server di mediazione soddisfi i requisiti delle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) e che l'Hyper-Threading sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="60139-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="60139-216">Per informazioni dettagliate sulla scalabilità di Mediation Server, vedere [stima dell'uso delle voci e del traffico per Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="60139-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="60139-217">Tutte le tabelle seguenti presuppongono l'utilizzo come riepilogato nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="60139-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="60139-218">Capacità di mediazione del server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non bypass (transcodifica multimediale eseguita da Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="60139-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-219">Hardware del server</span><span class="sxs-lookup"><span data-stu-id="60139-219">Server hardware</span></span></th>
<th><span data-ttu-id="60139-220">Numero massimo di chiamate</span><span class="sxs-lookup"><span data-stu-id="60139-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="60139-221">Numero massimo di righe T1</span><span class="sxs-lookup"><span data-stu-id="60139-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="60139-222">Numero massimo di righe E1</span><span class="sxs-lookup"><span data-stu-id="60139-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-223">Processore duale, hex core, CPU Hyper-Threading a 2,26 GHz <strong>con Hyper-Threading disabilitato</strong>, con memoria di 32 GB e una scheda di rete a doppia porta.</span><span class="sxs-lookup"><span data-stu-id="60139-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="60139-224">1100</span><span class="sxs-lookup"><span data-stu-id="60139-224">1100</span></span></p></td>
<td><p><span data-ttu-id="60139-225">46</span><span class="sxs-lookup"><span data-stu-id="60139-225">46</span></span></p></td>
<td><p><span data-ttu-id="60139-226">35</span><span class="sxs-lookup"><span data-stu-id="60139-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-227">Processore dual, hex core, CPU Hyper-Threaded da 2,26 GHz, con memoria 32 GB e una scheda di rete a doppia porta.</span><span class="sxs-lookup"><span data-stu-id="60139-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="60139-228">1500</span><span class="sxs-lookup"><span data-stu-id="60139-228">1500</span></span></p></td>
<td><p><span data-ttu-id="60139-229">63</span><span class="sxs-lookup"><span data-stu-id="60139-229">63</span></span></p></td>
<td><p><span data-ttu-id="60139-230">47</span><span class="sxs-lookup"><span data-stu-id="60139-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="60139-231">Anche se i server con 32 GB di memoria sono stati usati per il test delle prestazioni, i server con 16 GB di memoria sono supportati per Mediation Server autonomo e sono sufficienti per dare le prestazioni illustrate in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="60139-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="60139-232">Capacità Mediation Server (Mediation Server con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non bypass (elaborazione multimediale eseguita da Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="60139-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-233">Hardware del server</span><span class="sxs-lookup"><span data-stu-id="60139-233">Server hardware</span></span></th>
<th><span data-ttu-id="60139-234">Numero massimo di chiamate</span><span class="sxs-lookup"><span data-stu-id="60139-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-235">Processore duale, hex core, CPU Hyper-Threaded da 2,26 GHz, con memoria di 32 GB e schede di rete da 2 GB.</span><span class="sxs-lookup"><span data-stu-id="60139-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="60139-236">150</span><span class="sxs-lookup"><span data-stu-id="60139-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="60139-237">Questo numero è molto più piccolo dei numeri per il server di mediazione autonomo perché il server front-end deve gestire altre funzionalità e funzioni per gli utenti di 6600 ospitati, oltre alla transcodifica necessaria per le chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="60139-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="60139-238">Per migliorare le prestazioni del Mediation Server, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei media server.</span><span class="sxs-lookup"><span data-stu-id="60139-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="60139-239">RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server.</span><span class="sxs-lookup"><span data-stu-id="60139-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="60139-240">Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60139-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="60139-241">Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="60139-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="60139-242">Server back-end</span><span class="sxs-lookup"><span data-stu-id="60139-242">Back End Server</span></span>

<span data-ttu-id="60139-243">In Lync Server 2013 i database di presenza si trovano nei server front-end anziché nel server back-end.</span><span class="sxs-lookup"><span data-stu-id="60139-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="60139-244">Ciò ha comportato un requisito molto più semplice per ogni server back-end in Lync Server 2013, equivalente al requisito hardware per il server front-end.</span><span class="sxs-lookup"><span data-stu-id="60139-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="60139-245">In confronto a Lync Server 2010, in cui è necessario che il server back-end sia un server di qualità molto più elevato con 25 dischi.</span><span class="sxs-lookup"><span data-stu-id="60139-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="60139-246">Tuttavia, il carico di lavoro dei server back-end è ancora tale che non è necessario soddisfare le raccomandazioni hardware elencate in precedenza in questa sezione e nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="60139-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="60139-247">Per ottenere una disponibilità elevata del server back-end, è consigliabile distribuire il mirroring del server.</span><span class="sxs-lookup"><span data-stu-id="60139-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="60139-248">Per altre informazioni, vedere [back-end server high availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="60139-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="60139-249">Monitoraggio e archiviazione</span><span class="sxs-lookup"><span data-stu-id="60139-249">Monitoring and Archiving</span></span>

<span data-ttu-id="60139-250">In Lync Server 2013, se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei server front-end, anziché in ruoli server distinti.</span><span class="sxs-lookup"><span data-stu-id="60139-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="60139-251">Il monitoraggio e l'archiviazione di ogni nuovo uso di un proprio archivio database, separato dallo Store back-end.</span><span class="sxs-lookup"><span data-stu-id="60139-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="60139-252">In alternativa, se è stato distribuito Exchange 2013, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.</span><span class="sxs-lookup"><span data-stu-id="60139-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="60139-253">La tabella seguente indica approssimativamente la quantità di spazio di archiviazione del database necessaria per ogni utente per giorno per il monitoraggio e l'archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="60139-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="60139-254"><strong>CDR (monitoraggio)</strong></span><span class="sxs-lookup"><span data-stu-id="60139-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="60139-255"><strong>QoE (monitoraggio)</strong></span><span class="sxs-lookup"><span data-stu-id="60139-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="60139-256"><strong>Archiviazione</strong></span><span class="sxs-lookup"><span data-stu-id="60139-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-257">Spazio su disco richiesto per ogni utente per giorno</span><span class="sxs-lookup"><span data-stu-id="60139-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="60139-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="60139-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="60139-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="60139-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="60139-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="60139-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="60139-261">Microsoft ha usato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il test delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="60139-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="60139-262">Il test ha raccolto i dati di due pool Front-End, ognuno dei quali conteneva gli utenti di 80.000.</span><span class="sxs-lookup"><span data-stu-id="60139-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="60139-263">Hardware usato per il monitoraggio e l'archiviazione del test delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="60139-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60139-264">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="60139-264">Hardware component</span></span></th>
<th><span data-ttu-id="60139-265">Consigliato</span><span class="sxs-lookup"><span data-stu-id="60139-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-266">CPU</span><span class="sxs-lookup"><span data-stu-id="60139-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="60139-267">processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore</span><span class="sxs-lookup"><span data-stu-id="60139-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-268">Memoria</span><span class="sxs-lookup"><span data-stu-id="60139-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="60139-269">48 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="60139-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-270">Disco</span><span class="sxs-lookup"><span data-stu-id="60139-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="60139-271">25 10.000-RPM unità disco rigido con 300 GB su ogni disco, con la configurazione seguente</span><span class="sxs-lookup"><span data-stu-id="60139-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60139-272"><strong>Unità</strong></span><span class="sxs-lookup"><span data-stu-id="60139-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="60139-273"><strong>Configurazione RAID</strong></span><span class="sxs-lookup"><span data-stu-id="60139-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="60139-274"><strong>Numero di dischi</strong></span><span class="sxs-lookup"><span data-stu-id="60139-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-275">CDR, QoE e archiviazione dei file di dati del database in un'unica unità</span><span class="sxs-lookup"><span data-stu-id="60139-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="60139-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="60139-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="60139-277">16</span><span class="sxs-lookup"><span data-stu-id="60139-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-278">File di log del database CDR</span><span class="sxs-lookup"><span data-stu-id="60139-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="60139-279">1</span><span class="sxs-lookup"><span data-stu-id="60139-279">1</span></span></p></td>
<td><p><span data-ttu-id="60139-280">2</span><span class="sxs-lookup"><span data-stu-id="60139-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-281">File di log del database QoE</span><span class="sxs-lookup"><span data-stu-id="60139-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="60139-282">1</span><span class="sxs-lookup"><span data-stu-id="60139-282">1</span></span></p></td>
<td><p><span data-ttu-id="60139-283">2</span><span class="sxs-lookup"><span data-stu-id="60139-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60139-284">File di log del database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="60139-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="60139-285">1</span><span class="sxs-lookup"><span data-stu-id="60139-285">1</span></span></p></td>
<td><p><span data-ttu-id="60139-286">2</span><span class="sxs-lookup"><span data-stu-id="60139-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60139-287">Rete</span><span class="sxs-lookup"><span data-stu-id="60139-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60139-288">1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="60139-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60139-289">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="60139-289">In This Section</span></span>

  - [<span data-ttu-id="60139-290">Stima dell'utilizzo e del traffico vocale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60139-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="60139-291">Linee guida per la distribuzione di Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60139-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

