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
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="9689d-102">Visualizzazione sessione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9689d-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9689d-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9689d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9689d-104">La visualizzazione sessione archivia le informazioni sulle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="9689d-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="9689d-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9689d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9689d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="9689d-106">Column</span></span></th>
<th><span data-ttu-id="9689d-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9689d-107">Data Type</span></span></th>
<th><span data-ttu-id="9689d-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9689d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9689d-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="9689d-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="9689d-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="9689d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9689d-111">A cui si fa riferimento dalla Tabella MediaLine.</span><span class="sxs-lookup"><span data-stu-id="9689d-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="9689d-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="9689d-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9689d-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9689d-114">URI conferenza se si tratta di una conferenza o di DialogID se si tratta di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="9689d-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-115">Correlazione</span><span class="sxs-lookup"><span data-stu-id="9689d-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="9689d-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9689d-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9689d-117">ID correlazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="9689d-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="9689d-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="9689d-119">po'</span><span class="sxs-lookup"><span data-stu-id="9689d-119">bit</span></span></p></td>
<td><p><span data-ttu-id="9689d-120">Categoria finestra di dialogo; 0 è il server di Lync per mediazione server; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9689d-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="9689d-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="9689d-122">po'</span><span class="sxs-lookup"><span data-stu-id="9689d-122">bit</span></span></p></td>
<td><p><span data-ttu-id="9689d-123">Indica se la chiamata è stata ignorata o meno.</span><span class="sxs-lookup"><span data-stu-id="9689d-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="9689d-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="9689d-125">int</span><span class="sxs-lookup"><span data-stu-id="9689d-125">int</span></span></p></td>
<td><p><span data-ttu-id="9689d-126">Questo campo, se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono.</span><span class="sxs-lookup"><span data-stu-id="9689d-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="9689d-127">Per Lync Server, viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="9689d-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="9689d-128">0x0001-ID esclusione sconosciuta per la scheda di rete predefinita</span><span class="sxs-lookup"><span data-stu-id="9689d-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="9689d-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9689d-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9689d-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="9689d-131">Chiama ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="9689d-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="9689d-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9689d-133">DateTime</span><span class="sxs-lookup"><span data-stu-id="9689d-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="9689d-134">Ora di fine chiamata.</span><span class="sxs-lookup"><span data-stu-id="9689d-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9689d-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9689d-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-137">FQDN del pool chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9689d-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9689d-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-140">Nome di dominio completo del pool di chiamate.</span><span class="sxs-lookup"><span data-stu-id="9689d-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="9689d-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9689d-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9689d-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9689d-143">URI di identità p-asserito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="9689d-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="9689d-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9689d-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9689d-146">URI di identità p-Asserted del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9689d-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9689d-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9689d-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-149">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9689d-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9689d-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-152">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9689d-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9689d-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-155">Stringa agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9689d-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9689d-157">smallint</span><span class="sxs-lookup"><span data-stu-id="9689d-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="9689d-158">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-158">Type of caller’s user agent.</span></span> <span data-ttu-id="9689d-159">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9689d-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9689d-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9689d-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9689d-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9689d-162">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-162">Category of caller’s user agent.</span></span> <span data-ttu-id="9689d-163">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9689d-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9689d-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9689d-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9689d-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9689d-166">Stringa agente utente del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9689d-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9689d-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9689d-168">smallint</span><span class="sxs-lookup"><span data-stu-id="9689d-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="9689d-169">Tipo di agente utente per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="9689d-169">Type of user agent for the callee.</span></span> <span data-ttu-id="9689d-170">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9689d-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9689d-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9689d-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9689d-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9689d-173">Categoria agente utente per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="9689d-173">User agent category for the callee.</span></span> <span data-ttu-id="9689d-174">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9689d-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="9689d-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="9689d-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9689d-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9689d-177">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9689d-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9689d-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="9689d-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="9689d-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9689d-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9689d-180">URI del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9689d-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9689d-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="9689d-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="9689d-182">int</span><span class="sxs-lookup"><span data-stu-id="9689d-182">int</span></span></p></td>
<td><p><span data-ttu-id="9689d-183">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9689d-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

