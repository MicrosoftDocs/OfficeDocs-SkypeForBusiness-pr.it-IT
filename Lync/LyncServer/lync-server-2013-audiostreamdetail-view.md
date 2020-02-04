---
title: 'Lync Server 2013: visualizzazione AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="9744d-102">Visualizzazione AudioStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9744d-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9744d-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9744d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9744d-104">La visualizzazione AudioStreamDetail archivia le informazioni su ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="9744d-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="9744d-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9744d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9744d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="9744d-106">Column</span></span></th>
<th><span data-ttu-id="9744d-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9744d-107">Data Type</span></span></th>
<th><span data-ttu-id="9744d-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9744d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9744d-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="9744d-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="9744d-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="9744d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9744d-111">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9744d-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="9744d-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="9744d-113">int</span><span class="sxs-lookup"><span data-stu-id="9744d-113">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-114">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9744d-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="9744d-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="9744d-116">int</span><span class="sxs-lookup"><span data-stu-id="9744d-116">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-117">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="9744d-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="9744d-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9744d-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="9744d-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="9744d-120">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="9744d-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="9744d-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9744d-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="9744d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="9744d-123">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="9744d-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="9744d-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="9744d-125">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-125">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-126">Categoria di finestra di dialogo: 0 è il server Lync a Leg Mediation Server; 1 è il Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9744d-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="9744d-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="9744d-128">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-128">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-129">Contrassegno che indica se la chiamata è stata ignorata o meno.</span><span class="sxs-lookup"><span data-stu-id="9744d-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="9744d-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="9744d-131">int</span><span class="sxs-lookup"><span data-stu-id="9744d-131">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-132">Se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono.</span><span class="sxs-lookup"><span data-stu-id="9744d-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="9744d-133">Viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="9744d-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="9744d-134">0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="9744d-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="9744d-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="9744d-136">int</span><span class="sxs-lookup"><span data-stu-id="9744d-136">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-137">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9744d-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9744d-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-140">FQDN del pool chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9744d-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9744d-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-143">Nome di dominio completo del pool di chiamate.</span><span class="sxs-lookup"><span data-stu-id="9744d-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-144">Chiamante</span><span class="sxs-lookup"><span data-stu-id="9744d-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="9744d-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9744d-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9744d-146">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-147">Chiamato</span><span class="sxs-lookup"><span data-stu-id="9744d-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="9744d-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9744d-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9744d-149">URI del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9744d-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9744d-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-152">Stringa agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9744d-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9744d-154">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-155">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="9744d-156">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9744d-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9744d-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9744d-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9744d-159">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="9744d-160">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9744d-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9744d-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-163">Stringa agente utente del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9744d-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9744d-165">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-166">Tipo di agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-166">Type of callee’s user agent.</span></span> <span data-ttu-id="9744d-167">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9744d-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9744d-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9744d-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9744d-170">Categoria dell'agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-170">Category of callee’s user agent.</span></span> <span data-ttu-id="9744d-171">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9744d-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9744d-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-174">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9744d-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9744d-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-177">Nome dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="9744d-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-180">Sistema operativo (OS) dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="9744d-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-183">Sistema operativo (OS) dell'endpoint del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="9744d-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="9744d-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-186">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="9744d-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="9744d-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-189">Nome della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="9744d-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="9744d-191">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-192">Numero di core della CPU nell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="9744d-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="9744d-194">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-195">Numero di core della CPU nell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="9744d-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="9744d-197">int</span><span class="sxs-lookup"><span data-stu-id="9744d-197">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-198">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="9744d-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="9744d-200">int</span><span class="sxs-lookup"><span data-stu-id="9744d-200">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-201">Velocità del processore della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="9744d-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="9744d-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-204">Indica se il sistema del chiamante è in uso in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="9744d-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="9744d-205">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="9744d-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="9744d-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-208">Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="9744d-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="9744d-209">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="9744d-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9744d-211">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="9744d-211">Correlation key.</span></span> <span data-ttu-id="9744d-212">A cui si fa riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9744d-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="9744d-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="9744d-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-215">Informazioni sul percorso multimediale, ad esempio Direct o inoltrata.</span><span class="sxs-lookup"><span data-stu-id="9744d-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="9744d-216">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9744d-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9744d-218">int</span><span class="sxs-lookup"><span data-stu-id="9744d-218">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-219">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="9744d-220">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="9744d-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9744d-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9744d-222">int</span><span class="sxs-lookup"><span data-stu-id="9744d-222">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-223">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="9744d-224">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="9744d-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-225">Transport</span><span class="sxs-lookup"><span data-stu-id="9744d-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="9744d-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-227">Tipo di trasporto: 0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="9744d-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="9744d-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9744d-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="9744d-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9744d-230">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-230">IP address of the caller.</span></span> <span data-ttu-id="9744d-231">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9744d-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="9744d-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="9744d-233">int</span><span class="sxs-lookup"><span data-stu-id="9744d-233">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-234">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="9744d-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="9744d-236">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-236">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-237">Indica se il chiamante si trova all'interno della rete di intervalli: 1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="9744d-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="9744d-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9744d-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="9744d-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9744d-240">Indirizzo IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-240">IP address of the callee.</span></span> <span data-ttu-id="9744d-241">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9744d-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="9744d-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="9744d-243">int</span><span class="sxs-lookup"><span data-stu-id="9744d-243">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-244">Porta utilizzata dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="9744d-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="9744d-246">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-246">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-247">Indica se il chiamato si trova all'interno della rete a intervalli: 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="9744d-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="9744d-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="9744d-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-250">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="9744d-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="9744d-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-253">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="9744d-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="9744d-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-256">Nome del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="9744d-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="9744d-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="9744d-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9744d-259">Nome del paese/area geografica del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9744d-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9744d-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="9744d-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9744d-262">Indirizzo IP del servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="9744d-263">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="9744d-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9744d-265">int</span><span class="sxs-lookup"><span data-stu-id="9744d-265">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-266">Porta usata nel servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9744d-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9744d-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="9744d-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9744d-269">Chiave indirizzo IP del servizio A/V Edge usato dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="9744d-270">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="9744d-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9744d-272">int</span><span class="sxs-lookup"><span data-stu-id="9744d-272">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-273">Porta usata nel servizio A/V Edge usato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9744d-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9744d-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-276">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="9744d-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9744d-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-279">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9744d-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9744d-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-282">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="9744d-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="9744d-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-285">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9744d-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9744d-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-288">Nome del dispositivo di acquisizione del chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="9744d-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9744d-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-291">Nome del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9744d-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9744d-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-294">Nome del driver del dispositivo di acquisizione del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="9744d-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9744d-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9744d-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9744d-297">Nome del driver del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="9744d-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="9744d-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-300">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="9744d-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="9744d-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="9744d-302">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-302">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-303">Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="9744d-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="9744d-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="9744d-305">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="9744d-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="9744d-306">Velocità di collegamento di rete per l'endpoint del chiamante in bps.</span><span class="sxs-lookup"><span data-stu-id="9744d-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="9744d-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="9744d-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-309">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="9744d-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="9744d-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="9744d-311">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-311">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-312">Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="9744d-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="9744d-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="9744d-314">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="9744d-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="9744d-315">Velocità di collegamento di rete per l'endpoint del destinatario in bps.</span><span class="sxs-lookup"><span data-stu-id="9744d-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="9744d-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-317">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-318">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="9744d-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="9744d-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="9744d-320">int</span><span class="sxs-lookup"><span data-stu-id="9744d-320">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-321">Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="9744d-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="9744d-322">Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9744d-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="9744d-323">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="9744d-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="9744d-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="9744d-325">int</span><span class="sxs-lookup"><span data-stu-id="9744d-325">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-326">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="9744d-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="9744d-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="9744d-328">int</span><span class="sxs-lookup"><span data-stu-id="9744d-328">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-329">Variazione massima della rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="9744d-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-331">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="9744d-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="9744d-332">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="9744d-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="9744d-334">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="9744d-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="9744d-335">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="9744d-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="9744d-337">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="9744d-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="9744d-338">Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="9744d-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="9744d-340">int</span><span class="sxs-lookup"><span data-stu-id="9744d-340">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-341">Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="9744d-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="9744d-343">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="9744d-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="9744d-344">Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9744d-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="9744d-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="9744d-346">int</span><span class="sxs-lookup"><span data-stu-id="9744d-346">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-347">Durata media degli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9744d-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="9744d-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="9744d-349">int</span><span class="sxs-lookup"><span data-stu-id="9744d-349">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-350">Conteggio dei pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9744d-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-351">Larghezza di banda più ampia</span><span class="sxs-lookup"><span data-stu-id="9744d-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="9744d-352">int</span><span class="sxs-lookup"><span data-stu-id="9744d-352">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-353">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9744d-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-355">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-356">Degradazione MOS Network per l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="9744d-357">L'intervallo è compreso tra 0,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="9744d-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="9744d-358">Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9744d-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="9744d-359">Per una qualità accettabile dovrebbe essere inferiore a 0,5.</span><span class="sxs-lookup"><span data-stu-id="9744d-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="9744d-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="9744d-361">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-362">Massimo degrado dei MOS di rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-364">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-365">Degradazione dei MOS di rete causata da jitter.</span><span class="sxs-lookup"><span data-stu-id="9744d-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-367">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-368">Degradazione dei MOS di rete causata da perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9744d-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="9744d-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="9744d-370">int</span><span class="sxs-lookup"><span data-stu-id="9744d-370">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-371">Codec audio usato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9744d-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="9744d-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-373">int</span><span class="sxs-lookup"><span data-stu-id="9744d-373">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-374">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9744d-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-376">int</span><span class="sxs-lookup"><span data-stu-id="9744d-376">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-377">Livello di segnale audio di controllo del guadagno post-analogico per l'audio inviato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="9744d-378">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-379">Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="9744d-380">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-382">int</span><span class="sxs-lookup"><span data-stu-id="9744d-382">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-383">Livello di segnale audio per l'audio ricevuto dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="9744d-384">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-385">Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="9744d-386">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-388">int</span><span class="sxs-lookup"><span data-stu-id="9744d-388">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-389">Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="9744d-390">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-391">Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="9744d-392">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-394">int</span><span class="sxs-lookup"><span data-stu-id="9744d-394">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-395">Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="9744d-396">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-397">Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="9744d-398">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="9744d-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="9744d-400">int</span><span class="sxs-lookup"><span data-stu-id="9744d-400">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-401">Miglioramento della perdita di ritorno Echo per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="9744d-402">L'unità per questa metrica è dB.</span><span class="sxs-lookup"><span data-stu-id="9744d-402">The unit for this metric is dB.</span></span> <span data-ttu-id="9744d-403">I valori più bassi rappresentano meno eco.</span><span class="sxs-lookup"><span data-stu-id="9744d-403">Lower values represent less echo.</span></span> <span data-ttu-id="9744d-404">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="9744d-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-406">int</span><span class="sxs-lookup"><span data-stu-id="9744d-406">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-407">Glitch media per cinque minuti per il rendering dell'altoparlante del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="9744d-408">Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="9744d-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="9744d-409">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="9744d-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-411">int</span><span class="sxs-lookup"><span data-stu-id="9744d-411">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-412">Glitch media per cinque minuti per l'acquisizione del microfono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="9744d-413">Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="9744d-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="9744d-414">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="9744d-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="9744d-416">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-417">Tasso di velocità di clock del dispositivo microfono del chiamante, relativo all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="9744d-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="9744d-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="9744d-419">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-420">Tasso di deriva dell'orologio del dispositivo di altoparlante del chiamante, relativo all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="9744d-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="9744d-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="9744d-422">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-423">Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="9744d-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="9744d-425">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-426">Media dell'errore del timestamp del chiamante del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="9744d-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="9744d-428">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-429">L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="9744d-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="9744d-430">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="9744d-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="9744d-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-433">Cause di un evento Echo per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="9744d-434">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="9744d-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="9744d-436">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-437">Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="9744d-438">Se si usa l'auricolare, il valore dovrebbe essere basso.</span><span class="sxs-lookup"><span data-stu-id="9744d-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="9744d-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="9744d-440">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-441">Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="9744d-442">Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="9744d-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-444">int</span><span class="sxs-lookup"><span data-stu-id="9744d-444">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-445">Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante; Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9744d-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="9744d-446">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9744d-447">Per una buona qualità, l'intervallo accettabile deve essere compreso tra-30 e-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-449">int</span><span class="sxs-lookup"><span data-stu-id="9744d-449">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-450">Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="9744d-451">Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9744d-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="9744d-452">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9744d-453">Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="9744d-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="9744d-455">int</span><span class="sxs-lookup"><span data-stu-id="9744d-455">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-456">Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="9744d-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="9744d-458">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9744d-458">float</span></span></p></td>
<td><p><span data-ttu-id="9744d-459">Radice media quadrata (RMS) del segnale in arrivo al chiamante per un massimo di 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-461">int</span><span class="sxs-lookup"><span data-stu-id="9744d-461">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-462">Rappresenta il livello di segnale audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="9744d-463">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-464">Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="9744d-465">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-467">int</span><span class="sxs-lookup"><span data-stu-id="9744d-467">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-468">Livello di segnale audio per l'audio ricevuto dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="9744d-469">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-470">Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="9744d-471">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-473">int</span><span class="sxs-lookup"><span data-stu-id="9744d-473">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-474">Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="9744d-475">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-476">Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="9744d-477">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-479">int</span><span class="sxs-lookup"><span data-stu-id="9744d-479">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-480">Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="9744d-481">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="9744d-482">Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="9744d-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="9744d-483">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="9744d-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="9744d-485">int</span><span class="sxs-lookup"><span data-stu-id="9744d-485">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-486">Miglioramento della perdita di ritorno Echo per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="9744d-487">L'unità per questa metrica è dB.</span><span class="sxs-lookup"><span data-stu-id="9744d-487">The unit for this metric is dB.</span></span> <span data-ttu-id="9744d-488">I valori più bassi rappresentano meno eco.</span><span class="sxs-lookup"><span data-stu-id="9744d-488">Lower values represent less echo.</span></span> <span data-ttu-id="9744d-489">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="9744d-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-491">int</span><span class="sxs-lookup"><span data-stu-id="9744d-491">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-492">Inconvenienti medi per cinque minuti per il rendering dell'altoparlante del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="9744d-493">Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="9744d-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="9744d-494">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="9744d-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="9744d-496">int</span><span class="sxs-lookup"><span data-stu-id="9744d-496">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-497">Glitch media per cinque minuti per l'acquisizione del microfono del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="9744d-498">Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="9744d-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="9744d-499">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="9744d-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="9744d-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="9744d-501">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-502">Tasso di velocità di clock del dispositivo microfono del destinatario, relativo all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="9744d-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="9744d-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="9744d-504">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-505">Tasso di deriva dell'orologio del dispositivo altoparlante del destinatario, relativo all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="9744d-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="9744d-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="9744d-507">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-508">Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="9744d-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="9744d-510">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-511">Media dell'errore di timestamp del flusso di rendering del relatore del destinatario, in millisecondi, negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="9744d-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="9744d-513">smallint</span><span class="sxs-lookup"><span data-stu-id="9744d-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="9744d-514">L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="9744d-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="9744d-515">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="9744d-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="9744d-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="9744d-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9744d-518">Cause di un evento Echo per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="9744d-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="9744d-519">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9744d-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="9744d-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="9744d-521">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-522">Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="9744d-523">Se si usa l'auricolare, il valore dovrebbe essere basso.</span><span class="sxs-lookup"><span data-stu-id="9744d-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="9744d-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="9744d-525">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-526">Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="9744d-527">Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="9744d-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-529">int</span><span class="sxs-lookup"><span data-stu-id="9744d-529">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-530">Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario; Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9744d-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="9744d-531">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9744d-532">Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="9744d-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="9744d-534">int</span><span class="sxs-lookup"><span data-stu-id="9744d-534">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-535">Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="9744d-536">Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9744d-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="9744d-537">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="9744d-538">Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="9744d-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="9744d-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="9744d-540">int</span><span class="sxs-lookup"><span data-stu-id="9744d-540">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-541">Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9744d-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="9744d-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="9744d-543">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9744d-543">float</span></span></p></td>
<td><p><span data-ttu-id="9744d-544">Radice media quadrata (RMS) del segnale in arrivo al chiamato per un massimo di 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-546">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-547">Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="9744d-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-549">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-550">Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="9744d-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="9744d-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="9744d-552">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-553">Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.</span><span class="sxs-lookup"><span data-stu-id="9744d-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="9744d-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="9744d-555">int</span><span class="sxs-lookup"><span data-stu-id="9744d-555">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-556">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="9744d-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="9744d-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="9744d-558">int</span><span class="sxs-lookup"><span data-stu-id="9744d-558">int</span></span></p></td>
<td><p><span data-ttu-id="9744d-559">Tempo massimo di andata e ritorno per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9744d-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="9744d-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-561">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-562">MOS di rete a banda larga media per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="9744d-563">Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati.</span><span class="sxs-lookup"><span data-stu-id="9744d-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="9744d-564">L'intervallo è compreso tra 1,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="9744d-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="9744d-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-566">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-567">MOS della rete a banda larga minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="9744d-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-569">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-570">Valore medio previsto per l'ascolto della banda larga stimata per l'invio di audio, tra cui livello vocale, livello di rumore e caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="9744d-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="9744d-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="9744d-572">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-573">SendListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="9744d-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="9744d-575">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-576">Valore medio previsto per l'ascolto della banda larga stimata per l'audio ricevuto dalla rete, inclusi livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="9744d-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="9744d-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="9744d-578">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9744d-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9744d-579">RecvListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9744d-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9744d-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="9744d-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="9744d-581">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-581">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-582">Indica se per la chiamata è stato usato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="9744d-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9744d-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="9744d-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9744d-584">po'</span><span class="sxs-lookup"><span data-stu-id="9744d-584">bit</span></span></p></td>
<td><p><span data-ttu-id="9744d-585">Indica la direzione delle informazioni identificative p-asserite; 1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="9744d-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

