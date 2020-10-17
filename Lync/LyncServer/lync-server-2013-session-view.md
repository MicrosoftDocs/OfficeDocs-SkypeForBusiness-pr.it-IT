---
title: 'Lync Server 2013: visualizzazione sessione'
description: 'Lync Server 2013: visualizzazione sessione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545012"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="ecf75-103">Visualizzazione sessione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecf75-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecf75-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ecf75-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ecf75-105">Nella visualizzazione Session sono archiviate informazioni sulle sessioni per le quali sono presenti record nel database.</span><span class="sxs-lookup"><span data-stu-id="ecf75-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="ecf75-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecf75-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecf75-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="ecf75-107">Column</span></span></th>
<th><span data-ttu-id="ecf75-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ecf75-108">Data Type</span></span></th>
<th><span data-ttu-id="ecf75-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ecf75-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="ecf75-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ecf75-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-112">Riferimento dalla tabella MediaLine.</span><span class="sxs-lookup"><span data-stu-id="ecf75-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="ecf75-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="ecf75-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ecf75-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-115">URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ecf75-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="ecf75-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="ecf75-117">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="ecf75-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-118">ID correlazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="ecf75-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="ecf75-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="ecf75-120">po'</span><span class="sxs-lookup"><span data-stu-id="ecf75-120">bit</span></span></p></td>
<td><p><span data-ttu-id="ecf75-121">Categoria della finestra di dialogo; 0 è Lync Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ecf75-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="ecf75-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="ecf75-123">po'</span><span class="sxs-lookup"><span data-stu-id="ecf75-123">bit</span></span></p></td>
<td><p><span data-ttu-id="ecf75-124">Indica se la chiamata è stata ignorata o meno.</span><span class="sxs-lookup"><span data-stu-id="ecf75-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="ecf75-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="ecf75-126">int</span><span class="sxs-lookup"><span data-stu-id="ecf75-126">int</span></span></p></td>
<td><p><span data-ttu-id="ecf75-127">Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass.</span><span class="sxs-lookup"><span data-stu-id="ecf75-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="ecf75-128">Per Lync Server, viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="ecf75-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="ecf75-129">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita</span><span class="sxs-lookup"><span data-stu-id="ecf75-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="ecf75-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-131">datetime</span><span class="sxs-lookup"><span data-stu-id="ecf75-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-132">Ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="ecf75-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-134">datetime</span><span class="sxs-lookup"><span data-stu-id="ecf75-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="ecf75-135">Ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="ecf75-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ecf75-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-138">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="ecf75-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ecf75-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-141">FQDN del pool del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="ecf75-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ecf75-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ecf75-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-144">URI P-Asserted-Identity del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="ecf75-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="ecf75-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ecf75-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-147">URI P-Asserted-Identity del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ecf75-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ecf75-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-150">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="ecf75-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ecf75-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-153">Nome dell'endpoint del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="ecf75-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ecf75-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-156">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ecf75-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ecf75-158">smallint</span><span class="sxs-lookup"><span data-stu-id="ecf75-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="ecf75-159">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-159">Type of caller’s user agent.</span></span> <span data-ttu-id="ecf75-160">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ecf75-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ecf75-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ecf75-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ecf75-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-163">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-163">Category of caller’s user agent.</span></span> <span data-ttu-id="ecf75-164">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ecf75-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="ecf75-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ecf75-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf75-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-167">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ecf75-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ecf75-169">smallint</span><span class="sxs-lookup"><span data-stu-id="ecf75-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="ecf75-170">Tipo dell'agente utente per il destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-170">Type of user agent for the callee.</span></span> <span data-ttu-id="ecf75-171">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ecf75-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ecf75-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ecf75-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ecf75-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-174">Categoria dell'agente utente per il destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-174">User agent category for the callee.</span></span> <span data-ttu-id="ecf75-175">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ecf75-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="ecf75-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="ecf75-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ecf75-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-178">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ecf75-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecf75-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="ecf75-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="ecf75-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ecf75-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ecf75-181">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecf75-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="ecf75-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="ecf75-183">int</span><span class="sxs-lookup"><span data-stu-id="ecf75-183">int</span></span></p></td>
<td><p><span data-ttu-id="ecf75-184">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ecf75-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

