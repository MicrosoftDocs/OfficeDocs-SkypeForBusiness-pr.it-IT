---
title: Piattaforme hardware del server Lync Server 2013
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
ms.openlocfilehash: cb5c5cbe1ef98a4028f8b05d96e4acc90cae7963
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510273"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="8d697-102">Piattaforme hardware server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d697-102">Server hardware platforms for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d697-103">_**Ultimo argomento modificato:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="8d697-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="8d697-104">I ruoli del server e i computer Lync Server 2013 che eseguono gli strumenti di amministrazione di Lync Server richiedono hardware a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="8d697-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="8d697-105">L'hardware specifico utilizzato per la distribuzione di Lync Server 2013 può variare a seconda delle dimensioni e dei requisiti di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8d697-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="8d697-106">In questa sezione viene descritto l'hardware consigliato.</span><span class="sxs-lookup"><span data-stu-id="8d697-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="8d697-107">Sebbene si tratti di suggerimenti e non di requisiti, l'utilizzo di hardware che non soddisfa tali indicazioni potrebbe generare rallentamenti significativi delle prestazioni e altri problemi.</span><span class="sxs-lookup"><span data-stu-id="8d697-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="8d697-108">Piattaforma hardware consigliata</span><span class="sxs-lookup"><span data-stu-id="8d697-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="8d697-109">Per prestazioni ottimali, è consigliabile eseguire Lync Server nei server con hardware che soddisfi i requisiti indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8d697-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="8d697-110">Se si utilizzano componenti hardware meno potenti, è possibile che si verifichino problemi funzionali o di prestazioni insufficienti.</span><span class="sxs-lookup"><span data-stu-id="8d697-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="8d697-111">Si noti che questi requisiti hardware sono superiori a quelli delle versioni precedenti di Lync Server, principalmente perché in Lync Server 2013 tutti i front end server eseguono SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d697-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d697-112">Il teaming NIC è supportato e deve essere trasparente per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d697-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="8d697-113">Per informazioni dettagliate, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and Network Adapter Teaming</A>.</span><span class="sxs-lookup"><span data-stu-id="8d697-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="8d697-114">Hardware consigliato per Front End Server, server back-end, server Standard Edition, server Chat persistente e archivio chat persistente e archivio conformità chat persistente (ruoli del server back-end per il server Chat persistente)</span><span class="sxs-lookup"><span data-stu-id="8d697-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d697-115">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="8d697-115">Hardware component</span></span></th>
<th><span data-ttu-id="8d697-116">Consigliata</span><span class="sxs-lookup"><span data-stu-id="8d697-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d697-117">CPU</span><span class="sxs-lookup"><span data-stu-id="8d697-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="8d697-118">processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.</span><span class="sxs-lookup"><span data-stu-id="8d697-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8d697-119">I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d697-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d697-120">Memoria</span><span class="sxs-lookup"><span data-stu-id="8d697-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="8d697-121">32 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="8d697-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d697-122">Disco</span><span class="sxs-lookup"><span data-stu-id="8d697-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d697-123">Otto o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco</span><span class="sxs-lookup"><span data-stu-id="8d697-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8d697-124">Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.</span><span class="sxs-lookup"><span data-stu-id="8d697-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="8d697-125">- O</span><span class="sxs-lookup"><span data-stu-id="8d697-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8d697-126">Unità SSD (Solid State Drive) con prestazioni simili a otto unità disco meccanico da 10.000 RPM.</span><span class="sxs-lookup"><span data-stu-id="8d697-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d697-127">Rete</span><span class="sxs-lookup"><span data-stu-id="8d697-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d697-128">1 scheda di rete Dual-Port, 1 Gbps o superiore (2 consigliate, che richiede la collaborazione con un singolo indirizzo MAC e un singolo indirizzo IP).</span><span class="sxs-lookup"><span data-stu-id="8d697-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8d697-129">Le configurazioni dual o multi-homed non sono supportate per Front End Server, server back-end, server Standard Edition e server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8d697-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="8d697-130">Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e utilizzate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e pertanto sono supportate.</span><span class="sxs-lookup"><span data-stu-id="8d697-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="8d697-131">Hardware consigliato per server perimetrali, Mediation Server autonomi e server Director</span><span class="sxs-lookup"><span data-stu-id="8d697-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d697-132">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="8d697-132">Hardware component</span></span></th>
<th><span data-ttu-id="8d697-133">Consigliata</span><span class="sxs-lookup"><span data-stu-id="8d697-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d697-134">CPU</span><span class="sxs-lookup"><span data-stu-id="8d697-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d697-135">processore duale a 64 bit, quad-core, 2,0 gigahertz (GHz) o superiore.</span><span class="sxs-lookup"><span data-stu-id="8d697-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8d697-136">- O</span><span class="sxs-lookup"><span data-stu-id="8d697-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8d697-137">processore a 4 vie a 64 bit, Dual Core, 2,0 GHz o superiore.</span><span class="sxs-lookup"><span data-stu-id="8d697-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="8d697-138">I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d697-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d697-139">Memoria</span><span class="sxs-lookup"><span data-stu-id="8d697-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="8d697-140">16 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="8d697-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d697-141">Disco</span><span class="sxs-lookup"><span data-stu-id="8d697-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d697-142">4 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</span><span class="sxs-lookup"><span data-stu-id="8d697-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8d697-143">I dischi devono essere in una configurazione di 2x RAID 1.</span><span class="sxs-lookup"><span data-stu-id="8d697-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="8d697-144">- O</span><span class="sxs-lookup"><span data-stu-id="8d697-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8d697-145">Unità SSD (Solid State Drive) con prestazioni simili a quattro unità disco meccanico da 10.000 RPM.</span><span class="sxs-lookup"><span data-stu-id="8d697-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d697-146">Rete</span><span class="sxs-lookup"><span data-stu-id="8d697-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d697-147">1 scheda di rete Dual-Port, 1 Gbps o superiore (2 consigliate, che richiede la collaborazione con un singolo indirizzo MAC e un singolo indirizzo IP).</span><span class="sxs-lookup"><span data-stu-id="8d697-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="8d697-148">2 le interfacce di rete sono necessarie nei server perimetrali e sono supportate su Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="8d697-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="8d697-149">Le configurazioni dual o multi-homed non sono supportate per i direttori.</span><span class="sxs-lookup"><span data-stu-id="8d697-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="8d697-150">Le connessioni ILO/DRAC/etc. non esposte al sistema operativo e utilizzate per monitorare e gestire l'hardware del server non costituiscono un server multihomed e pertanto sono supportate.</span><span class="sxs-lookup"><span data-stu-id="8d697-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="8d697-151">I server perimetrali richiedono due interfacce di rete che sono schede di rete Dual-Port, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ciascuna coppia viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).</span><span class="sxs-lookup"><span data-stu-id="8d697-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="8d697-152">L'installazione di altre schede di interfaccia di rete (NIC) per consentire la configurazione di un indirizzo IP PSTN specifico è supportata su Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="8d697-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

