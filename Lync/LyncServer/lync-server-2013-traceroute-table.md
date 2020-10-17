---
title: 'Lync Server 2013: Tabella TraceRoute'
description: 'Lync Server 2013: Tabella TraceRoute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549062"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="0690d-103">Tabella TraceRoute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0690d-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0690d-104">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="0690d-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="0690d-105">Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0690d-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="0690d-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0690d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0690d-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0690d-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0690d-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0690d-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0690d-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0690d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0690d-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="0690d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0690d-114">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0690d-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0690d-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-116">int</span><span class="sxs-lookup"><span data-stu-id="0690d-116">int</span></span></p></td>
<td><p><span data-ttu-id="0690d-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="0690d-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0690d-118">Identificatore univoco utilizzato per distinguere le diverse chiamate che possono essere iniziate nella stessa data e alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="0690d-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0690d-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="0690d-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0690d-121">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="0690d-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0690d-p102">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="0690d-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0690d-124">0 – audio</span><span class="sxs-lookup"><span data-stu-id="0690d-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="0690d-125">1-video</span><span class="sxs-lookup"><span data-stu-id="0690d-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="0690d-126">2 - Panoramica</span><span class="sxs-lookup"><span data-stu-id="0690d-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="0690d-127">3 – condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="0690d-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0690d-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-129">po'</span><span class="sxs-lookup"><span data-stu-id="0690d-129">bit</span></span></p></td>
<td><p><span data-ttu-id="0690d-130">Principale</span><span class="sxs-lookup"><span data-stu-id="0690d-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="0690d-131">Endpoint che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0690d-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0690d-132"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-133">int</span><span class="sxs-lookup"><span data-stu-id="0690d-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0690d-134">Hop di rete.</span><span class="sxs-lookup"><span data-stu-id="0690d-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0690d-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-136">int</span><span class="sxs-lookup"><span data-stu-id="0690d-136">int</span></span></p></td>
<td><p><span data-ttu-id="0690d-137">Stranieri</span><span class="sxs-lookup"><span data-stu-id="0690d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0690d-138">Identificatore univoco dell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="0690d-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="0690d-139">Le informazioni sull'indirizzo IP sono archiviate nella <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0690d-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0690d-140"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="0690d-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="0690d-141">int</span><span class="sxs-lookup"><span data-stu-id="0690d-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0690d-p104">Tempo di roundtrip, ovvero la quantità di tempo necessaria a un pacchetto voce per raggiungere la relativa destinazione e quindi inviare di nuovo la notifica ricevuta.</span><span class="sxs-lookup"><span data-stu-id="0690d-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

