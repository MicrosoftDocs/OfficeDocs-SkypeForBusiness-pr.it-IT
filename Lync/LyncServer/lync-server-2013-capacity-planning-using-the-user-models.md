---
title: Lync Server 2013 Capacity Planning using the user Models
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
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="69ace-102">Pianificazione della capacità per Lync Server 2013 con i modelli utente</span><span class="sxs-lookup"><span data-stu-id="69ace-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69ace-103">_**Ultimo argomento modificato:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="69ace-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="69ace-104">In questa sezione vengono fornite informazioni su quanti server sono necessari in un sito per il numero di utenti di tale sito, in base all'utilizzo descritto in [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="69ace-105">Piattaforma hardware testata</span><span class="sxs-lookup"><span data-stu-id="69ace-105">Tested Hardware Platform</span></span>

<span data-ttu-id="69ace-106">Tutti i risultati delle prestazioni e i suggerimenti relativi alla distribuzione in questa sezione si basano sui test delle prestazioni nei server che eseguono l'hardware descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="69ace-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="69ace-107">È consigliabile utilizzare hardware analogo.</span><span class="sxs-lookup"><span data-stu-id="69ace-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="69ace-108">Se si utilizzano componenti hardware meno potenti, è possibile che si verifichino problemi funzionali o di prestazioni insufficienti.</span><span class="sxs-lookup"><span data-stu-id="69ace-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="69ace-109">Si noti che questi suggerimenti per l'hardware sono più alti rispetto a quelli delle versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="69ace-110">Hardware utilizzato nei test delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="69ace-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-111">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="69ace-111">Hardware component</span></span></th>
<th><span data-ttu-id="69ace-112">Consigliato</span><span class="sxs-lookup"><span data-stu-id="69ace-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-113">CPU</span><span class="sxs-lookup"><span data-stu-id="69ace-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="69ace-114">Processore doppio a 64 bit, hex core, 2,26 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="69ace-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="69ace-115">I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-116">Memoria</span><span class="sxs-lookup"><span data-stu-id="69ace-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="69ace-117">32 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="69ace-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-118">Disco</span><span class="sxs-lookup"><span data-stu-id="69ace-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="69ace-119">8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="69ace-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="69ace-120">Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.</span><span class="sxs-lookup"><span data-stu-id="69ace-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="69ace-121">-O</span><span class="sxs-lookup"><span data-stu-id="69ace-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="69ace-122">Unità SSD (Solid State Drive) con prestazioni simili a otto unità disco meccanico da 10.000 RPM.</span><span class="sxs-lookup"><span data-stu-id="69ace-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-123">Rete</span><span class="sxs-lookup"><span data-stu-id="69ace-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="69ace-124">Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="69ace-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="69ace-125">Riepilogo dei risultati</span><span class="sxs-lookup"><span data-stu-id="69ace-125">Summary of Results</span></span>

<span data-ttu-id="69ace-126">Nella tabella riportata di seguito vengono riepilogate queste indicazioni.</span><span class="sxs-lookup"><span data-stu-id="69ace-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-127">Ruolo del server</span><span class="sxs-lookup"><span data-stu-id="69ace-127">Server role</span></span></th>
<th><span data-ttu-id="69ace-128">Numero massimo di utenti supportati</span><span class="sxs-lookup"><span data-stu-id="69ace-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-129">Pool Front end con dodici front end server e un server back-end o una coppia con mirroring dei server back-end.</span><span class="sxs-lookup"><span data-stu-id="69ace-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="69ace-130">80.000 utenti univoci connessi contemporaneamente, oltre al 50% di più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 152.000 endpoint.</span><span class="sxs-lookup"><span data-stu-id="69ace-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-131">A/V Conferencing</span><span class="sxs-lookup"><span data-stu-id="69ace-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="69ace-132">Il servizio A/V Conferencing fornito da un pool Front end supporta le conferenze del pool assumendo una dimensione massima per le conferenze di 250 utenti e solo una conferenza di questo tipo è in esecuzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="69ace-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69ace-133">È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front end separato con due front end server per ospitare le conferenze di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="69ace-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="69ace-134">Per informazioni dettagliate, vedere <A href="lync-server-2013-supporting-large-meetings.md">supporto di riunioni di grandi dimensioni con Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="69ace-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-135">Un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="69ace-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="69ace-136">12.000 utenti remoti simultanei</span><span class="sxs-lookup"><span data-stu-id="69ace-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-137">Un Director</span><span class="sxs-lookup"><span data-stu-id="69ace-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="69ace-138">12.000 utenti remoti simultanei</span><span class="sxs-lookup"><span data-stu-id="69ace-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-139">Monitoraggio e archiviazione</span><span class="sxs-lookup"><span data-stu-id="69ace-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="69ace-140">In Lync Server 2013, i servizi front end di monitoraggio e archiviazione ora vengono eseguiti su ogni Front End Server, anziché su ruoli server distinti.</span><span class="sxs-lookup"><span data-stu-id="69ace-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="69ace-141">Monitoring and Archiving each richiedono ancora i propri archivi di database.</span><span class="sxs-lookup"><span data-stu-id="69ace-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="69ace-142">Se si esegue anche Exchange 2013, è possibile mantenere i dati di archiviazione in Exchange anziché in un database SQL dedicato.</span><span class="sxs-lookup"><span data-stu-id="69ace-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-143">Un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69ace-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="69ace-144">Mediation Server collocato con Front End Server viene eseguito in tutti i front end server in un pool e deve fornire capacità sufficiente per gli utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="69ace-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="69ace-145">Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="69ace-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-146">Un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="69ace-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="69ace-147">Se si utilizzano i server Standard Edition per ospitare gli utenti, è consigliabile utilizzare sempre due server, abbinati con i suggerimenti per la <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">pianificazione della disponibilità elevata e del ripristino di emergenza in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="69ace-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="69ace-148">Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server ha esito negativo, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.</span><span class="sxs-lookup"><span data-stu-id="69ace-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="69ace-149">Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono subire più di 2.500 utenti per server.</span><span class="sxs-lookup"><span data-stu-id="69ace-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="69ace-150">In questo caso, è consigliabile aggiungere più server Standard Edition o passare a Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="69ace-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="69ace-151">Front End Server</span><span class="sxs-lookup"><span data-stu-id="69ace-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-152">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="69ace-153">In un pool Front End, è necessario disporre di un front end server per ogni 6.660 utenti ospitati nel pool, presupponendo che l'Hyper-Threading sia abilitato su tutti i server del pool e che l'hardware del server soddisfi le indicazioni riportate nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="69ace-154">Il numero massimo di utenti in un pool Front End è 80.000, presupponendo che l'Hyper-Threading sia abilitato su tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="69ace-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="69ace-155">Se in un sito sono presenti più di 80.000 utenti è possibile distribuire più pool Front End.</span><span class="sxs-lookup"><span data-stu-id="69ace-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="69ace-156">Quando si calcola il numero di utenti in un pool Front End, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a tale pool.</span><span class="sxs-lookup"><span data-stu-id="69ace-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="69ace-157">Quando un server attivo non è disponibile, le relative connessioni vengono trasferite automaticamente agli altri server del pool.</span><span class="sxs-lookup"><span data-stu-id="69ace-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="69ace-158">Ad esempio, se si dispone di 30.000 utenti e cinque front end server, se un server non è disponibile, le connessioni degli utenti di 6000 devono essere trasferite agli altri quattro server.</span><span class="sxs-lookup"><span data-stu-id="69ace-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="69ace-159">Gli altri quattro server avranno 7500 utenti, che è un numero maggiore di quello consigliato.</span><span class="sxs-lookup"><span data-stu-id="69ace-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="69ace-160">Se invece si è iniziato con sei front end server per gli utenti di 30.000 e successivamente non si è resi disponibili, per un totale di 5000 gli utenti verranno spostati nei cinque server rimanenti.</span><span class="sxs-lookup"><span data-stu-id="69ace-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="69ace-161">Questi cinque server avranno ogni host 6000 utenti, che si trova nell'intervallo consigliato.</span><span class="sxs-lookup"><span data-stu-id="69ace-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="69ace-162">Il numero massimo di utenti in un pool Front End è 80.000.</span><span class="sxs-lookup"><span data-stu-id="69ace-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="69ace-163">Il numero massimo di front end server in un pool è 12.</span><span class="sxs-lookup"><span data-stu-id="69ace-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="69ace-164">Per un pool Front end con 80.000 utenti, dodici front end server sono sufficienti per le prestazioni, nelle distribuzioni tipiche che seguono i [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="69ace-165">Le distribuzioni progettate per supportare il failover del ripristino di emergenza presumono che un massimo di 40.000 utenti possano essere ospitati in ognuno dei due pool Front End associati, in cui ogni pool disponga di front end server sufficienti per ospitare gli utenti in entrambi i pool in caso di errore di un pool all'altro.</span><span class="sxs-lookup"><span data-stu-id="69ace-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="69ace-166">Il numero di utenti supportati con prestazioni ottimali da parte di un pool Front end specifico potrebbe differire da questi numeri per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="69ace-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="69ace-167">L'hardware per i Front End Server non soddisfa gli elementi consigliati nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="69ace-168">L'utilizzo dell'organizzazione si discosta notevolmente dai modelli utente, ad esempio il traffico delle conferenze è molto superiore.</span><span class="sxs-lookup"><span data-stu-id="69ace-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69ace-169">In Lync Server 2013, i database di presenza sono ora ospitati nei Front End Server, a differenza di Lync Server 2010, in cui sono ospitati nel server back-end.</span><span class="sxs-lookup"><span data-stu-id="69ace-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="69ace-170">Questo significa che le prestazioni e la capacità del disco dei front end server non devono essere compromesse dalle raccomandazioni elencate in precedenza in questa sezione e nelle <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A>, indipendentemente dal numero di utenti ospitati dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="69ace-171">Nella tabella seguente viene illustrata la larghezza di banda media per la messaggistica istantanea e la presenza, in base al modello utente, come definito nei [modelli utente di Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-172">Larghezza di banda media per utente</span><span class="sxs-lookup"><span data-stu-id="69ace-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="69ace-173">Requisiti di larghezza di banda per front end server con 6.660 utenti</span><span class="sxs-lookup"><span data-stu-id="69ace-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-174">1,3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="69ace-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="69ace-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="69ace-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="69ace-176">Per migliorare le prestazioni multimediali delle funzionalità di A/V Conferencing e Mediation Server in base ai server front end, è necessario abilitare il riversamento sul lato ricezione (RSS) nelle schede di rete nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="69ace-177">RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="69ace-178">Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="69ace-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="69ace-179">Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="69ace-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="69ace-180">Valori massimi per le conferenze</span><span class="sxs-lookup"><span data-stu-id="69ace-180">Conferencing Maximums</span></span>

<span data-ttu-id="69ace-181">Dato il modello utente che prevede che il 5% degli utenti di un pool possono essere in conferenza in qualsiasi momento, un pool di 80.000 utenti può avere circa 4.000 utenti in conferenza in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="69ace-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="69ace-182">Le conferenze saranno variabili nel tipo di contenuti multimediali (ad esempio alcune solo di messaggistica istantanea, altre di messaggistica istantanea e audio, altre audio/video) e nel numero di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="69ace-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="69ace-183">Non esiste un limite rigido per il numero effettivo di conferenze consentite e le prestazioni reali sono determinate dall'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="69ace-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="69ace-184">Se ad esempio il numero di conferenze in modalità mista dell'organizzazione è molto superiore a quello previsto nel modello utente, può essere necessario distribuire più Front End Server o A/V Conferencing Server rispetto a quanto consigliato in questo documento.</span><span class="sxs-lookup"><span data-stu-id="69ace-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="69ace-185">Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="69ace-186">Le dimensioni massime supportate per la conferenza ospitate da un pool di server front end normale di Lync 2013 che ospita anche gli utenti sono 250 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="69ace-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="69ace-187">Anche se è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che il 5% degli utenti del pool si trovi in conferenze simultanee.</span><span class="sxs-lookup"><span data-stu-id="69ace-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="69ace-188">Ad esempio, in un pool di dodici front end server e 80.000 utenti, mentre la conferenza di 250 utenti è in corso, Lync Server supporta 3.750 altri utenti che partecipano a conferenze di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="69ace-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="69ace-189">Indipendentemente dal numero di utenti che si trovano nel pool Front end o nel server Standard Edition, Lync Server supporta almeno 125 altri utenti che partecipano a conferenze di piccole dimensioni nello stesso pool o server che ospita una conferenza di 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="69ace-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="69ace-190">Per abilitare le conferenze tra gli utenti di 250 e 1000, è possibile configurare un pool Front end separato solo per ospitare tali conferenze.</span><span class="sxs-lookup"><span data-stu-id="69ace-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="69ace-191">Questo pool Front end non ospiterà alcun utente.</span><span class="sxs-lookup"><span data-stu-id="69ace-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="69ace-192">Per informazioni dettagliate, vedere [supporto di riunioni di grandi dimensioni con Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="69ace-193">Se nell'organizzazione sono presenti molte più conferenze in modalità miste rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più Front End Server rispetto ai consigli riportati in questo documento (fino a un massimo di 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="69ace-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="69ace-194">Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="69ace-195">Edge Server</span><span class="sxs-lookup"><span data-stu-id="69ace-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-196">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="69ace-197">È necessario distribuire un server perimetrale per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito.</span><span class="sxs-lookup"><span data-stu-id="69ace-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="69ace-198">Per la disponibilità elevata è consigliabile un minimo di due server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="69ace-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="69ace-199">Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="69ace-200">Quando si calcola il numero di utenti per i server perimetrali, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.</span><span class="sxs-lookup"><span data-stu-id="69ace-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-201">Per migliorare le prestazioni del servizio A/V Conferencing Edge nei server perimetrali è opportuno abilitare Receive-Side Scaling (RSS) nelle schede di rete dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="69ace-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="69ace-202">RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="69ace-203">Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="69ace-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="69ace-204">Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="69ace-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="69ace-205">Director</span><span class="sxs-lookup"><span data-stu-id="69ace-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-206">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="69ace-207">Se si distribuisce il ruolo server Director, è consigliabile distribuire un amministratore per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito.</span><span class="sxs-lookup"><span data-stu-id="69ace-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="69ace-208">Per la disponibilità elevata è consigliabile un minimo di due Director.</span><span class="sxs-lookup"><span data-stu-id="69ace-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="69ace-209">Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="69ace-210">Quando si calcola il numero di utenti per i Director, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.</span><span class="sxs-lookup"><span data-stu-id="69ace-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="69ace-211">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69ace-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-212">I pool allungati non sono supportati per questo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="69ace-213">Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i Front End Server nel pool e deve fornire una capacità sufficiente per gli utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="69ace-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="69ace-214">Se si distribuisce un pool di Mediation Server autonomo, il numero di Mediation Server da distribuire dipende da molti fattori, tra cui l'hardware utilizzato per Mediation Server, il numero di utenti di VoIP che si ha, la quantità di peer gateway che ogni pool di Mediation Server controlli, il traffico di ora occupato attraverso tali gateway e la percentuale di chiamate con supporto che ignora il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="69ace-215">Nelle tabelle seguenti vengono fornite linee guida per il numero di chiamate simultanee che un Mediation Server può gestire, presupponendo che l'hardware per i Mediation Server soddisfi i requisiti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) e che sia abilitato l'Hyper-Threading.</span><span class="sxs-lookup"><span data-stu-id="69ace-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="69ace-216">Per informazioni dettagliate sulla scalabilità dei Mediation Server, vedere [stima dell'utilizzo e del traffico vocale per Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="69ace-217">Tutte le tabelle seguenti presumono l'utilizzo come riepilogato nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="69ace-218">Capacità Mediation Server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non di bypass (transcodifica multimediale eseguita da Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="69ace-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-219">Hardware dei server</span><span class="sxs-lookup"><span data-stu-id="69ace-219">Server hardware</span></span></th>
<th><span data-ttu-id="69ace-220">Numero massimo di chiamate</span><span class="sxs-lookup"><span data-stu-id="69ace-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="69ace-221">Numero massimo di linee T1</span><span class="sxs-lookup"><span data-stu-id="69ace-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="69ace-222">Numero massimo di linee E1</span><span class="sxs-lookup"><span data-stu-id="69ace-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-223">Doppio processore, hex core, CPU Hyper-Threading da 2,26 GHz <strong>con Hyper-Threading disabilitato</strong>, con 32 GB di memoria e una scheda di rete a doppia porta.</span><span class="sxs-lookup"><span data-stu-id="69ace-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="69ace-224">1100</span><span class="sxs-lookup"><span data-stu-id="69ace-224">1100</span></span></p></td>
<td><p><span data-ttu-id="69ace-225">46</span><span class="sxs-lookup"><span data-stu-id="69ace-225">46</span></span></p></td>
<td><p><span data-ttu-id="69ace-226">35</span><span class="sxs-lookup"><span data-stu-id="69ace-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-227">Processore duale, Core esagonale, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e una scheda di rete a doppia porta.</span><span class="sxs-lookup"><span data-stu-id="69ace-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="69ace-228">1500</span><span class="sxs-lookup"><span data-stu-id="69ace-228">1500</span></span></p></td>
<td><p><span data-ttu-id="69ace-229">63</span><span class="sxs-lookup"><span data-stu-id="69ace-229">63</span></span></p></td>
<td><p><span data-ttu-id="69ace-230">47</span><span class="sxs-lookup"><span data-stu-id="69ace-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="69ace-231">Anche se nei test delle prestazioni sono stati utilizzati server con 32 GB di memoria, i server con 16 GB di memoria sono sono supportati in Mediation Server autonomo e sono sufficienti a garantire le prestazioni indicate in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="69ace-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="69ace-232">Capacità Mediation Server (Mediation Server collocato con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non di bypass (elaborazione multimediale eseguita da Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="69ace-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-233">Hardware dei server</span><span class="sxs-lookup"><span data-stu-id="69ace-233">Server hardware</span></span></th>
<th><span data-ttu-id="69ace-234">Numero massimo di chiamate</span><span class="sxs-lookup"><span data-stu-id="69ace-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-235">Processore duale, Core Hex, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e 2 schede di rete da 1 GB.</span><span class="sxs-lookup"><span data-stu-id="69ace-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="69ace-236">150</span><span class="sxs-lookup"><span data-stu-id="69ace-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="69ace-237">Questo numero è molto più piccolo dei numeri per il Mediation Server autonomo perché il front end server deve gestire altre caratteristiche e funzionalità per gli utenti di 6600 ospitati in esso, oltre alla transcoding necessaria per le chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="69ace-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="69ace-238">Per migliorare le prestazioni del Mediation Server, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete dei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69ace-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="69ace-239">RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="69ace-240">Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="69ace-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="69ace-241">Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="69ace-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="69ace-242">server back-end</span><span class="sxs-lookup"><span data-stu-id="69ace-242">Back End Server</span></span>

<span data-ttu-id="69ace-243">In Lync Server 2013, i database di presenza si trovano nei front end server invece che nel server back-end.</span><span class="sxs-lookup"><span data-stu-id="69ace-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="69ace-244">Questo ha determinato un requisito molto più semplice per ogni server back-end in Lync Server 2013, equivalente ai requisiti hardware per il front end server.</span><span class="sxs-lookup"><span data-stu-id="69ace-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="69ace-245">Contrapporre questo a Lync Server 2010, in cui il server back-end è stato richiesto per essere un server di grado molto più alto con 25 dischi.</span><span class="sxs-lookup"><span data-stu-id="69ace-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="69ace-246">Tuttavia, il carico di lavoro dei server back-end è ancora tale da non riuscire a rispondere alle raccomandazioni hardware elencate in precedenza in questa sezione e nelle [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="69ace-247">Per garantire la disponibilità elevata del server back-end, è consigliabile distribuire il mirroring del server.</span><span class="sxs-lookup"><span data-stu-id="69ace-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="69ace-248">Per ulteriori informazioni, vedere [disponibilità elevata del server back-end in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="69ace-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="69ace-249">Monitoraggio e archiviazione</span><span class="sxs-lookup"><span data-stu-id="69ace-249">Monitoring and Archiving</span></span>

<span data-ttu-id="69ace-250">In Lync Server 2013, se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei Front End Server, anziché in ruoli server distinti.</span><span class="sxs-lookup"><span data-stu-id="69ace-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="69ace-251">Monitoring and Archiving each utilizzano ancora un archivio di database separato dall'archivio di back-end.</span><span class="sxs-lookup"><span data-stu-id="69ace-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="69ace-252">In alternativa, se si dispone di Exchange 2013 distribuito, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.</span><span class="sxs-lookup"><span data-stu-id="69ace-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="69ace-253">La tabella seguente indica approssimativamente la quantità di spazio di archiviazione dei database necessaria per utente al giorno per il monitoraggio e l'archiviazione di dati.</span><span class="sxs-lookup"><span data-stu-id="69ace-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="69ace-254"><strong>CDR (monitoraggio)</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="69ace-255"><strong>QoE (monitoraggio)</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="69ace-256"><strong>Archiviazione</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-257">Spazio su disco necessario per utente per giorno</span><span class="sxs-lookup"><span data-stu-id="69ace-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="69ace-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="69ace-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="69ace-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="69ace-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="69ace-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="69ace-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69ace-261">Microsoft ha utilizzato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il testing delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="69ace-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="69ace-262">Il test ha raccolto i dati di due pool Front End, ognuno dei quali conteneva 80.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="69ace-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="69ace-263">Hardware utilizzato per il monitoraggio e il testing delle prestazioni di archiviazione</span><span class="sxs-lookup"><span data-stu-id="69ace-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ace-264">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="69ace-264">Hardware component</span></span></th>
<th><span data-ttu-id="69ace-265">Consigliato</span><span class="sxs-lookup"><span data-stu-id="69ace-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ace-266">CPU</span><span class="sxs-lookup"><span data-stu-id="69ace-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="69ace-267">Processore doppio a 64 bit, hex core, 2,26 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="69ace-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-268">Memoria</span><span class="sxs-lookup"><span data-stu-id="69ace-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="69ace-269">48 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="69ace-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-270">Disco</span><span class="sxs-lookup"><span data-stu-id="69ace-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="69ace-271">unità disco rigido 25 10.000-RPM con 300 GB su ogni disco, con la seguente configurazione</span><span class="sxs-lookup"><span data-stu-id="69ace-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="69ace-272"><strong>Unità</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="69ace-273"><strong>Configurazione RAID</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="69ace-274"><strong>Numero di dischi</strong></span><span class="sxs-lookup"><span data-stu-id="69ace-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-275">File di dati CDR, QoE e di archiviazione per database, in un'unica unità</span><span class="sxs-lookup"><span data-stu-id="69ace-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="69ace-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="69ace-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="69ace-277">16 </span><span class="sxs-lookup"><span data-stu-id="69ace-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-278">File di registro del database CDR</span><span class="sxs-lookup"><span data-stu-id="69ace-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="69ace-279">1 </span><span class="sxs-lookup"><span data-stu-id="69ace-279">1</span></span></p></td>
<td><p><span data-ttu-id="69ace-280">2 </span><span class="sxs-lookup"><span data-stu-id="69ace-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-281">File di registro del database QoE</span><span class="sxs-lookup"><span data-stu-id="69ace-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="69ace-282">1 </span><span class="sxs-lookup"><span data-stu-id="69ace-282">1</span></span></p></td>
<td><p><span data-ttu-id="69ace-283">2 </span><span class="sxs-lookup"><span data-stu-id="69ace-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ace-284">File di registro del database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="69ace-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="69ace-285">1 </span><span class="sxs-lookup"><span data-stu-id="69ace-285">1</span></span></p></td>
<td><p><span data-ttu-id="69ace-286">2 </span><span class="sxs-lookup"><span data-stu-id="69ace-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ace-287">Rete</span><span class="sxs-lookup"><span data-stu-id="69ace-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="69ace-288">Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="69ace-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69ace-289">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="69ace-289">In This Section</span></span>

  - [<span data-ttu-id="69ace-290">Stima dell'utilizzo e del traffico vocale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69ace-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="69ace-291">Linee guida per la distribuzione di Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69ace-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

