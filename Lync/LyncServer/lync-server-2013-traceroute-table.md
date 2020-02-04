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
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="3e310-102">Tabella TraceRoute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e310-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e310-103">_**Argomento Ultima modifica:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="3e310-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="3e310-104">La tabella TraceRoute contiene le informazioni di routing dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3e310-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="3e310-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e310-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e310-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3e310-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3e310-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3e310-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e310-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e310-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3e310-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="3e310-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3e310-113">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e310-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e310-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-115">int</span><span class="sxs-lookup"><span data-stu-id="3e310-115">int</span></span></p></td>
<td><p><span data-ttu-id="3e310-116">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="3e310-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3e310-117">Identificatore univoco usato per distinguere tra più chiamate che potrebbero essere iniziate nella stessa data e contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3e310-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e310-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="3e310-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3e310-120">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="3e310-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3e310-121">Rappresenta il tipo di linea video usato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e310-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="3e310-122">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="3e310-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e310-123">0-audio</span><span class="sxs-lookup"><span data-stu-id="3e310-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="3e310-124">1-video</span><span class="sxs-lookup"><span data-stu-id="3e310-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="3e310-125">2-video panoramico</span><span class="sxs-lookup"><span data-stu-id="3e310-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="3e310-126">3-condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="3e310-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e310-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-128">po'</span><span class="sxs-lookup"><span data-stu-id="3e310-128">bit</span></span></p></td>
<td><p><span data-ttu-id="3e310-129">Principale</span><span class="sxs-lookup"><span data-stu-id="3e310-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e310-130">Endpoint che ha posto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e310-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e310-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-132">int</span><span class="sxs-lookup"><span data-stu-id="3e310-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e310-133">Hop di rete/</span><span class="sxs-lookup"><span data-stu-id="3e310-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e310-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-135">int</span><span class="sxs-lookup"><span data-stu-id="3e310-135">int</span></span></p></td>
<td><p><span data-ttu-id="3e310-136">Esterna</span><span class="sxs-lookup"><span data-stu-id="3e310-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3e310-137">Identificatore univoco per l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="3e310-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="3e310-138">Le informazioni sull'indirizzo IP sono archiviate nella <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3e310-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e310-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="3e310-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="3e310-140">int</span><span class="sxs-lookup"><span data-stu-id="3e310-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e310-141">Ora di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="3e310-141">Roundtrip time.</span></span> <span data-ttu-id="3e310-142">Il tempo di andata e ritorno misura la quantità di tempo necessaria per il pacchetto vocale per raggiungere la destinazione e quindi inviare di nuovo la notifica che è stata ricevuta.</span><span class="sxs-lookup"><span data-stu-id="3e310-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

