---
title: 'Lync Server 2013: visualizzazione sessione'
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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b403e-102">Visualizzazione sessione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b403e-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b403e-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b403e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b403e-104">Nella visualizzazione Session sono archiviate informazioni sulle sessioni per le quali sono presenti record nel database.</span><span class="sxs-lookup"><span data-stu-id="b403e-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b403e-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b403e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b403e-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="b403e-106">Column</span></span></th>
<th><span data-ttu-id="b403e-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b403e-107">Data Type</span></span></th>
<th><span data-ttu-id="b403e-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b403e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b403e-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b403e-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b403e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b403e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b403e-111">Riferimento dalla tabella MediaLine.</span><span class="sxs-lookup"><span data-stu-id="b403e-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b403e-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b403e-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b403e-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b403e-114">URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b403e-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="b403e-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b403e-116">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="b403e-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b403e-117">ID correlazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="b403e-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b403e-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b403e-119">po'</span><span class="sxs-lookup"><span data-stu-id="b403e-119">bit</span></span></p></td>
<td><p><span data-ttu-id="b403e-120">Categoria della finestra di dialogo; 0 è Lync Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b403e-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b403e-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b403e-122">po'</span><span class="sxs-lookup"><span data-stu-id="b403e-122">bit</span></span></p></td>
<td><p><span data-ttu-id="b403e-123">Indica se la chiamata è stata ignorata o meno.</span><span class="sxs-lookup"><span data-stu-id="b403e-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b403e-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b403e-125">int</span><span class="sxs-lookup"><span data-stu-id="b403e-125">int</span></span></p></td>
<td><p><span data-ttu-id="b403e-126">Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass.</span><span class="sxs-lookup"><span data-stu-id="b403e-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b403e-127">Per Lync Server, viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="b403e-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b403e-128">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita</span><span class="sxs-lookup"><span data-stu-id="b403e-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="b403e-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b403e-130">datetime</span><span class="sxs-lookup"><span data-stu-id="b403e-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b403e-131">Ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="b403e-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b403e-133">datetime</span><span class="sxs-lookup"><span data-stu-id="b403e-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="b403e-134">Ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b403e-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b403e-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-137">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b403e-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b403e-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-140">FQDN del pool del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b403e-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b403e-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b403e-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b403e-143">URI P-Asserted-Identity del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b403e-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b403e-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b403e-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b403e-146">URI P-Asserted-Identity del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b403e-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b403e-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-149">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b403e-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b403e-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-152">Nome dell'endpoint del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b403e-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b403e-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-155">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b403e-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b403e-157">smallint</span><span class="sxs-lookup"><span data-stu-id="b403e-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b403e-158">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-158">Type of caller’s user agent.</span></span> <span data-ttu-id="b403e-159">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b403e-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b403e-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b403e-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b403e-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b403e-162">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-162">Category of caller’s user agent.</span></span> <span data-ttu-id="b403e-163">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b403e-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b403e-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b403e-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b403e-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b403e-166">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b403e-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b403e-168">smallint</span><span class="sxs-lookup"><span data-stu-id="b403e-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="b403e-169">Tipo dell'agente utente per il destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-169">Type of user agent for the callee.</span></span> <span data-ttu-id="b403e-170">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b403e-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b403e-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b403e-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b403e-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b403e-173">Categoria dell'agente utente per il destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-173">User agent category for the callee.</span></span> <span data-ttu-id="b403e-174">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b403e-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b403e-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b403e-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b403e-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b403e-177">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b403e-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b403e-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b403e-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b403e-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b403e-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b403e-180">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b403e-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="b403e-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b403e-182">int</span><span class="sxs-lookup"><span data-stu-id="b403e-182">int</span></span></p></td>
<td><p><span data-ttu-id="b403e-183">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b403e-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

