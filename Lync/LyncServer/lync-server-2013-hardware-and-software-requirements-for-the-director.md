---
title: 'Lync Server 2013: Requisiti hardware e software per il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d91a739935b2e42bb925d5645350c5875e5b43
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="91bc3-102">Requisiti hardware e software per il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91bc3-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bc3-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="91bc3-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="91bc3-104">In questa sezione vengono illustrati i requisiti hardware e software per il Director e gli scenari di collocazione supportati per il Director.</span><span class="sxs-lookup"><span data-stu-id="91bc3-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="91bc3-105">Requisiti hardware per il Director</span><span class="sxs-lookup"><span data-stu-id="91bc3-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="91bc3-106">La tabella seguente elenca i requisiti hardware per il Director:</span><span class="sxs-lookup"><span data-stu-id="91bc3-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="91bc3-107">Requisiti hardware per il Director</span><span class="sxs-lookup"><span data-stu-id="91bc3-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91bc3-108">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="91bc3-108">Hardware component</span></span></th>
<th><span data-ttu-id="91bc3-109">Requisito minimo</span><span class="sxs-lookup"><span data-stu-id="91bc3-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91bc3-110">CPU</span><span class="sxs-lookup"><span data-stu-id="91bc3-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91bc3-111">processore a 64 bit, quad-core, 2,0 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="91bc3-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="91bc3-112">processore duale a 64 bit, Dual-Core, 2,0 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="91bc3-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bc3-113">Memoria</span><span class="sxs-lookup"><span data-stu-id="91bc3-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="91bc3-114">4 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="91bc3-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91bc3-115">Disco</span><span class="sxs-lookup"><span data-stu-id="91bc3-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91bc3-116">unità disco rigido RPM 10K (HDD)</span><span class="sxs-lookup"><span data-stu-id="91bc3-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="91bc3-117">SSD (Solid State Drive) a prestazioni elevate con prestazioni pari o superiori a 10K RPM HDD</span><span class="sxs-lookup"><span data-stu-id="91bc3-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="91bc3-118">2x RAID 10 (con striping e mirroring) 15K RPM per i file di dati del database</span><span class="sxs-lookup"><span data-stu-id="91bc3-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91bc3-119">Rete</span><span class="sxs-lookup"><span data-stu-id="91bc3-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91bc3-120">Schede di rete dual 1 Gigabit per secondo (Gbps) (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="91bc3-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="91bc3-121">Scheda di rete single 1 Gbps (supportata)</span><span class="sxs-lookup"><span data-stu-id="91bc3-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="91bc3-122">Requisiti software per il direttore</span><span class="sxs-lookup"><span data-stu-id="91bc3-122">Software Requirements for the Director</span></span>

<span data-ttu-id="91bc3-123">Il ruolo Director può essere distribuito solo nei server che utilizzano Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="91bc3-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="91bc3-124">Per gli amministratori è necessario uno dei sistemi operativi a 64 bit seguenti:</span><span class="sxs-lookup"><span data-stu-id="91bc3-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="91bc3-125">Sistema operativo standard Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91bc3-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91bc3-126">Sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91bc3-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91bc3-127">Sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91bc3-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91bc3-128">Sistema operativo standard di Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="91bc3-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="91bc3-129">Sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="91bc3-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="91bc3-130">Lync Server 2013 richiede inoltre l'installazione dei programmi e degli aggiornamenti seguenti descritti nell'argomento [supporto e requisiti aggiuntivi del server in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91bc3-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="91bc3-131">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="91bc3-131">Supported Collocation</span></span>

<span data-ttu-id="91bc3-132">Il ruolo del server Director non può essere collocato con qualsiasi altro ruolo del server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91bc3-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="91bc3-133">Tuttavia, se non si distribuisce un amministratore, i server front-end si assumeranno il ruolo.</span><span class="sxs-lookup"><span data-stu-id="91bc3-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

