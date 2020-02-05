---
title: 'Lync Server 2013: Piattaforme hardware server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="62124-102">Piattaforme hardware server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62124-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62124-103">_**Argomento Ultima modifica:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="62124-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="62124-104">I ruoli server e i computer di Lync Server 2013 che eseguono gli strumenti di amministrazione di Lync Server richiedono hardware a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="62124-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="62124-105">L'hardware specifico usato per la distribuzione di Lync Server 2013 può variare a seconda delle dimensioni e dei requisiti di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="62124-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="62124-106">Questa sezione descrive l'hardware consigliato.</span><span class="sxs-lookup"><span data-stu-id="62124-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="62124-107">Anche se si tratta di raccomandazioni, non di requisiti, l'uso di hardware che non soddisfa questi suggerimenti può causare problemi di prestazioni significativi e altri problemi.</span><span class="sxs-lookup"><span data-stu-id="62124-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="62124-108">Piattaforma hardware consigliata</span><span class="sxs-lookup"><span data-stu-id="62124-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="62124-109">Per ottenere prestazioni ottimali, è consigliabile eseguire Lync Server nei server con hardware che soddisfi i requisiti della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="62124-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="62124-110">Se usi hardware meno potente, potresti riscontrare problemi di funzionalità o prestazioni scarse.</span><span class="sxs-lookup"><span data-stu-id="62124-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="62124-111">Si noti che questi requisiti hardware sono superiori a quelli delle versioni precedenti di Lync Server, principalmente perché in Lync Server 2013 tutti i server front-end eseguono SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62124-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62124-112">Il teaming di NIC è supportato e deve essere trasparente per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62124-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="62124-113">Per informazioni dettagliate, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server o Lync Server e Network Adapter Teaming</A>.</span><span class="sxs-lookup"><span data-stu-id="62124-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="62124-114">Hardware consigliato per i server front-end, i server di back-end, i server Standard Edition, i server di chat persistenti e l'Archivio Chat persistente e lo Store di conformità della chat persistente (ruoli del server back-end per il server</span><span class="sxs-lookup"><span data-stu-id="62124-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62124-115">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="62124-115">Hardware component</span></span></th>
<th><span data-ttu-id="62124-116">Consigliato</span><span class="sxs-lookup"><span data-stu-id="62124-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62124-117">CPU</span><span class="sxs-lookup"><span data-stu-id="62124-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="62124-118">64-bit Dual Processor, hex-core, 2,26 gigahertz (GHz) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="62124-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="62124-119">I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</span><span class="sxs-lookup"><span data-stu-id="62124-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62124-120">Memoria</span><span class="sxs-lookup"><span data-stu-id="62124-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="62124-121">32 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="62124-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62124-122">Disco</span><span class="sxs-lookup"><span data-stu-id="62124-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="62124-123">8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="62124-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="62124-124">Due dischi dovrebbero usare RAID 1 e sei dovrebbero usare RAID 10.</span><span class="sxs-lookup"><span data-stu-id="62124-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="62124-125">-O</span><span class="sxs-lookup"><span data-stu-id="62124-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="62124-126">SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 8 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="62124-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62124-127">Rete</span><span class="sxs-lookup"><span data-stu-id="62124-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="62124-128">1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP).</span><span class="sxs-lookup"><span data-stu-id="62124-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62124-129">Le configurazioni dual o multihomed non sono supportate per i server front-end, i server back-end, i server Standard Edition e i server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="62124-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="62124-130">Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e usate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e quindi sono supportate.</span><span class="sxs-lookup"><span data-stu-id="62124-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="62124-131">Hardware consigliato per Edge Server, Mediation Server autonomi e direttori</span><span class="sxs-lookup"><span data-stu-id="62124-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62124-132">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="62124-132">Hardware component</span></span></th>
<th><span data-ttu-id="62124-133">Consigliato</span><span class="sxs-lookup"><span data-stu-id="62124-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62124-134">CPU</span><span class="sxs-lookup"><span data-stu-id="62124-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="62124-135">64-bit Dual Processor, quad-core, 2,0 gigahertz (GHz) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="62124-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="62124-136">-O</span><span class="sxs-lookup"><span data-stu-id="62124-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="62124-137">processore a 4 vie a 64 bit, Dual-Core, 2,0 GHz o superiore.</span><span class="sxs-lookup"><span data-stu-id="62124-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="62124-138">I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</span><span class="sxs-lookup"><span data-stu-id="62124-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62124-139">Memoria</span><span class="sxs-lookup"><span data-stu-id="62124-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="62124-140">16 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="62124-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62124-141">Disco</span><span class="sxs-lookup"><span data-stu-id="62124-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="62124-142">4 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="62124-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="62124-143">I dischi devono essere in una configurazione di 2x RAID 1.</span><span class="sxs-lookup"><span data-stu-id="62124-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="62124-144">-O</span><span class="sxs-lookup"><span data-stu-id="62124-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="62124-145">SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 4 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="62124-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62124-146">Rete</span><span class="sxs-lookup"><span data-stu-id="62124-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="62124-147">1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP).</span><span class="sxs-lookup"><span data-stu-id="62124-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="62124-148">2 le interfacce di rete sono necessarie in Edge Server e sono supportate nei server di mediazione autonomi.</span><span class="sxs-lookup"><span data-stu-id="62124-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="62124-149">Le configurazioni dual o multihomed non sono supportate per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="62124-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="62124-150">Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e usate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e quindi sono supportate.</span><span class="sxs-lookup"><span data-stu-id="62124-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="62124-151">I server perimetrali richiedono due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ogni coppia che viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).</span><span class="sxs-lookup"><span data-stu-id="62124-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="62124-152">L'installazione di schede di interfaccia di rete aggiuntive (NIC) per consentire la configurazione di un indirizzo IP PSTN specifico è supportata nei server di mediazione autonomi.</span><span class="sxs-lookup"><span data-stu-id="62124-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

