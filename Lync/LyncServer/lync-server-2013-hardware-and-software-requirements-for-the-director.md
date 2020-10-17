---
title: 'Lync Server 2013: requisiti hardware e software per il Director'
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
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536863"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="c7343-102">Requisiti hardware e software per il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7343-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7343-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c7343-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c7343-104">In questa sezione vengono illustrati i requisiti hardware e software per il server Director e gli scenari di collocazione supportati per il server Director.</span><span class="sxs-lookup"><span data-stu-id="c7343-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="c7343-105">Requisiti hardware per il server Director</span><span class="sxs-lookup"><span data-stu-id="c7343-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="c7343-106">Nella tabella seguente sono elencati i requisiti hardware per il server Director:</span><span class="sxs-lookup"><span data-stu-id="c7343-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="c7343-107">Requisiti hardware per il server Director</span><span class="sxs-lookup"><span data-stu-id="c7343-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7343-108">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="c7343-108">Hardware component</span></span></th>
<th><span data-ttu-id="c7343-109">Requisito minimo</span><span class="sxs-lookup"><span data-stu-id="c7343-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7343-110">CPU</span><span class="sxs-lookup"><span data-stu-id="c7343-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7343-111">Processore a 64 bit, quad-core, 2.0 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="c7343-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="c7343-112">Processore doppio a 64 bit, dual-core, 2.0 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="c7343-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7343-113">Memoria</span><span class="sxs-lookup"><span data-stu-id="c7343-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="c7343-114">4 gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="c7343-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7343-115">Disco</span><span class="sxs-lookup"><span data-stu-id="c7343-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7343-116">Unità disco rigido 10K RPM</span><span class="sxs-lookup"><span data-stu-id="c7343-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="c7343-117">Unità SSD (Solid State Drive) ad alte prestazioni, equivalenti o superiori rispetto alle unità disco rigido 10K RPM</span><span class="sxs-lookup"><span data-stu-id="c7343-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="c7343-118">Dischi 2x RAID 10 (con striping e mirroring) 15K RPM per file di dati del database</span><span class="sxs-lookup"><span data-stu-id="c7343-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7343-119">Rete</span><span class="sxs-lookup"><span data-stu-id="c7343-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7343-120">Scheda di rete doppia a 1 gigabit al secondo (Gbps) (consigliata)</span><span class="sxs-lookup"><span data-stu-id="c7343-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="c7343-121">Scheda di rete singola a 1 Gbps (supportata)</span><span class="sxs-lookup"><span data-stu-id="c7343-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="c7343-122">Requisiti software per il server Director</span><span class="sxs-lookup"><span data-stu-id="c7343-122">Software Requirements for the Director</span></span>

<span data-ttu-id="c7343-123">Il ruolo di Director può essere distribuito solo sui server che eseguono Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c7343-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="c7343-124">Per i direttori è necessario uno dei seguenti sistemi operativi a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="c7343-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="c7343-125">Sistema operativo Windows Server 2008 R2 Standard con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c7343-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c7343-126">Sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c7343-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c7343-127">Sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c7343-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c7343-128">Sistema operativo Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="c7343-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="c7343-129">Sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c7343-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="c7343-130">Lync Server 2013 richiede inoltre l'installazione dei programmi e degli aggiornamenti seguenti descritti nell'argomento [additional server support and requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7343-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="c7343-131">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="c7343-131">Supported Collocation</span></span>

<span data-ttu-id="c7343-132">Il ruolo server Director non può essere collocato con qualsiasi altro ruolo del server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7343-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="c7343-133">Tuttavia, se non si distribuisce un Director, i Front End Server assumeranno il ruolo.</span><span class="sxs-lookup"><span data-stu-id="c7343-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

