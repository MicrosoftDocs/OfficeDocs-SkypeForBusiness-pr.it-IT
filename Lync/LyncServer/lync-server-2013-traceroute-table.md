---
title: 'Lync Server 2013: Tabella TraceRoute'
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
ms.openlocfilehash: afb8cfb65fdf8fdbb4c281127caafd394cb878af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="39055-102">Tabella TraceRoute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39055-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39055-103">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="39055-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="39055-104">Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="39055-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="39055-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39055-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39055-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="39055-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="39055-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="39055-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="39055-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="39055-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="39055-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="39055-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39055-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="39055-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-111">datetime</span><span class="sxs-lookup"><span data-stu-id="39055-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="39055-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="39055-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39055-113">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="39055-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39055-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="39055-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-115">int</span><span class="sxs-lookup"><span data-stu-id="39055-115">int</span></span></p></td>
<td><p><span data-ttu-id="39055-116">Primario, esterno</span><span class="sxs-lookup"><span data-stu-id="39055-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39055-117">Identificatore univoco utilizzato per distinguere le diverse chiamate che possono essere iniziate nella stessa data e alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="39055-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39055-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="39055-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="39055-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="39055-120">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="39055-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39055-p102">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="39055-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="39055-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="39055-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="39055-124">1-video</span><span class="sxs-lookup"><span data-stu-id="39055-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="39055-125">2 - Panoramica</span><span class="sxs-lookup"><span data-stu-id="39055-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="39055-126">3 – condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="39055-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39055-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="39055-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-128">po'</span><span class="sxs-lookup"><span data-stu-id="39055-128">bit</span></span></p></td>
<td><p><span data-ttu-id="39055-129">Principale</span><span class="sxs-lookup"><span data-stu-id="39055-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="39055-130">Endpoint che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="39055-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39055-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="39055-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-132">int</span><span class="sxs-lookup"><span data-stu-id="39055-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39055-133">Hop di rete.</span><span class="sxs-lookup"><span data-stu-id="39055-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39055-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="39055-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-135">int</span><span class="sxs-lookup"><span data-stu-id="39055-135">int</span></span></p></td>
<td><p><span data-ttu-id="39055-136">Stranieri</span><span class="sxs-lookup"><span data-stu-id="39055-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="39055-137">Identificatore univoco dell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="39055-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="39055-138">Le informazioni sull'indirizzo IP sono archiviate nella <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="39055-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39055-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="39055-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="39055-140">int</span><span class="sxs-lookup"><span data-stu-id="39055-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39055-p104">Tempo di roundtrip, ovvero la quantità di tempo necessaria a un pacchetto voce per raggiungere la relativa destinazione e quindi inviare di nuovo la notifica ricevuta.</span><span class="sxs-lookup"><span data-stu-id="39055-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

