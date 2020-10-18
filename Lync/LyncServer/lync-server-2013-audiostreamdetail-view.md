---
title: 'Lync Server 2013: visualizzazione AudioStreamDetail'
description: 'Lync Server 2013: visualizzazione AudioStreamDetail.'
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573052"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="f49ea-103">Visualizzazione AudioStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f49ea-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f49ea-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f49ea-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f49ea-105">Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="f49ea-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="f49ea-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f49ea-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f49ea-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="f49ea-107">Column</span></span></th>
<th><span data-ttu-id="f49ea-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f49ea-108">Data Type</span></span></th>
<th><span data-ttu-id="f49ea-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f49ea-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="f49ea-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f49ea-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-112">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f49ea-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="f49ea-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="f49ea-114">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-114">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-115">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f49ea-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="f49ea-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="f49ea-117">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-117">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-118">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="f49ea-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="f49ea-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-120">datetime</span><span class="sxs-lookup"><span data-stu-id="f49ea-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-121">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="f49ea-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="f49ea-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-123">datetime</span><span class="sxs-lookup"><span data-stu-id="f49ea-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="f49ea-124">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="f49ea-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="f49ea-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="f49ea-126">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-126">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-127">Categoria della finestra di dialogo: 0 è il Lync Server a Mediation Server Leg; 1 è il Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f49ea-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="f49ea-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="f49ea-129">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-129">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-130">Flag che indica se la chiamata è stata o meno ignorata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="f49ea-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="f49ea-132">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-132">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p102">Se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="f49ea-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="f49ea-135">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="f49ea-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="f49ea-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="f49ea-137">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-137">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-138">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="f49ea-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="f49ea-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-141">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="f49ea-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="f49ea-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-144">FQDN del pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-145">Chiamante</span><span class="sxs-lookup"><span data-stu-id="f49ea-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="f49ea-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f49ea-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-147">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-148">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="f49ea-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="f49ea-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f49ea-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-150">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="f49ea-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f49ea-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-153">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f49ea-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f49ea-155">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-156">Tipo dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="f49ea-157">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f49ea-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f49ea-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f49ea-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-160">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="f49ea-161">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="f49ea-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f49ea-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-164">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f49ea-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f49ea-166">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-167">Tipo dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-167">Type of callee’s user agent.</span></span> <span data-ttu-id="f49ea-168">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f49ea-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f49ea-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f49ea-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-171">Categoria dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-171">Category of callee’s user agent.</span></span> <span data-ttu-id="f49ea-172">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f49ea-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-175">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="f49ea-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-178">Nome dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-181">Sistema operativo dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-183">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-184">Sistema operativo dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="f49ea-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="f49ea-186">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-187">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="f49ea-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="f49ea-189">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-190">Nome della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="f49ea-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f49ea-192">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-193">Numero di core della CPU nell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="f49ea-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f49ea-195">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-196">Numero di core della CPU nell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="f49ea-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f49ea-198">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-198">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-199">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="f49ea-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f49ea-201">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-201">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-202">Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="f49ea-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f49ea-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-205">Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="f49ea-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f49ea-206">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="f49ea-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f49ea-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-209">Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="f49ea-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f49ea-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="f49ea-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f49ea-212">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="f49ea-212">Correlation key.</span></span> <span data-ttu-id="f49ea-213">A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f49ea-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="f49ea-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="f49ea-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-216">Informazioni sul percorso multimediale, ad esempio diretto o inoltrato.</span><span class="sxs-lookup"><span data-stu-id="f49ea-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="f49ea-217">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f49ea-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f49ea-219">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-219">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p111">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f49ea-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f49ea-223">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-223">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p112">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-226">Trasporto</span><span class="sxs-lookup"><span data-stu-id="f49ea-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="f49ea-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-228">Tipo di trasporto: 0 è UDP e 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="f49ea-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f49ea-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="f49ea-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-231">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-231">IP address of the caller.</span></span> <span data-ttu-id="f49ea-232">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="f49ea-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="f49ea-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="f49ea-234">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-234">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-235">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="f49ea-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="f49ea-237">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-237">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-238">Indica se il chiamante è nella rete interna: 1 indica che il chiamante è all'interno della rete aziendale e 0 indica che il chiamante è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="f49ea-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="f49ea-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f49ea-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="f49ea-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-241">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-241">IP address of the callee.</span></span> <span data-ttu-id="f49ea-242">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="f49ea-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="f49ea-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="f49ea-244">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-244">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-245">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="f49ea-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="f49ea-247">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-247">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-248">Indica se il destinatario della chiamata è nella rete interna: 1 indica che il destinatario della chiamata è all'interno della rete aziendale e 0 indica che il destinatario della chiamata è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="f49ea-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="f49ea-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="f49ea-250">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-251">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="f49ea-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="f49ea-253">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-254">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="f49ea-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="f49ea-256">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-257">Nome del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="f49ea-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="f49ea-259">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="f49ea-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-260">Nome del paese/area geografica del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f49ea-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f49ea-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="f49ea-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-263">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="f49ea-264">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="f49ea-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f49ea-266">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-266">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-267">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f49ea-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f49ea-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="f49ea-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-270">Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="f49ea-271">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="f49ea-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f49ea-273">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-273">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-274">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f49ea-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f49ea-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-277">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="f49ea-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f49ea-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-280">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f49ea-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f49ea-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-283">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="f49ea-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="f49ea-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-286">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f49ea-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f49ea-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-289">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="f49ea-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f49ea-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-292">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f49ea-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f49ea-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-295">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="f49ea-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f49ea-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f49ea-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-298">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="f49ea-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f49ea-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-301">Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="f49ea-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="f49ea-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="f49ea-303">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-303">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-304">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="f49ea-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="f49ea-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f49ea-306">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="f49ea-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-307">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="f49ea-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f49ea-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-310">Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="f49ea-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="f49ea-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="f49ea-312">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-312">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-313">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="f49ea-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="f49ea-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f49ea-315">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="f49ea-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-316">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-318">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-319">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="f49ea-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="f49ea-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-321">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-321">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p117">Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="f49ea-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="f49ea-326">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-326">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-327">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="f49ea-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="f49ea-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="f49ea-329">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-329">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-330">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-332">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f49ea-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-333">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="f49ea-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="f49ea-335">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f49ea-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-336">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-337">DensitàBurst</span><span class="sxs-lookup"><span data-stu-id="f49ea-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="f49ea-338">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f49ea-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-339">Densità media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="f49ea-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="f49ea-341">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-341">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-342">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="f49ea-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="f49ea-344">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f49ea-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-345">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f49ea-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="f49ea-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="f49ea-347">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-347">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-348">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f49ea-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="f49ea-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="f49ea-350">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-350">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-351">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="f49ea-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-352">Larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f49ea-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="f49ea-353">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-353">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-354">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="f49ea-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-356">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p118">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="f49ea-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="f49ea-362">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-363">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-365">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-366">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="f49ea-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-368">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-369">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f49ea-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="f49ea-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="f49ea-371">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-371">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-372">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f49ea-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-374">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-374">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-375">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="f49ea-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-377">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-377">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p119">Livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-383">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-383">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p120">Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-389">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-389">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p121">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-395">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-395">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p122">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="f49ea-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="f49ea-401">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-401">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p123">ERLE (Echo Return Loss Enhancement) per il chiamante. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-407">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-407">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p124">Media dei problemi di rendering dell'altoparlante del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-412">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-412">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p125">Media dei problemi di acquisizione del microfono del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="f49ea-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="f49ea-417">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-418">Deviazione del clock del dispositivo microfono del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="f49ea-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="f49ea-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="f49ea-420">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-421">Deviazione del clock del dispositivo altoparlante del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="f49ea-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="f49ea-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="f49ea-423">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-424">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="f49ea-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="f49ea-426">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-427">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del chiamante negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="f49ea-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="f49ea-429">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-430">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="f49ea-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="f49ea-431">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="f49ea-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="f49ea-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-434">Cause di un evento di eco per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="f49ea-435">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="f49ea-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="f49ea-437">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p128">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamante. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="f49ea-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="f49ea-441">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p129">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del chiamante. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-445">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-445">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p130">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra -30 e -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-450">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-450">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p131">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="f49ea-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="f49ea-456">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-456">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-457">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="f49ea-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-459">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f49ea-459">float</span></span></p></td>
<td><p><span data-ttu-id="f49ea-460">Radice della media dei quadrati del segnale in ingresso per il chiamante fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-462">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-462">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p132">Rappresenta il livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-468">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-468">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p133">Livello di segnale audio per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-474">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-474">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p134">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-480">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-480">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p135">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="f49ea-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="f49ea-486">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-486">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p136">ERLE (Echo Return Loss Enhancement) per il destinatario della chiamata. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-492">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-492">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p137">Media dei problemi di rendering dell'altoparlante del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f49ea-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f49ea-497">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-497">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p138">Media dei problemi di acquisizione del microfono del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="f49ea-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="f49ea-502">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-503">Deviazione del clock del dispositivo microfono del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="f49ea-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="f49ea-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="f49ea-505">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-506">Deviazione del clock del dispositivo altoparlante del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="f49ea-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="f49ea-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="f49ea-508">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-509">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="f49ea-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="f49ea-511">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-512">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del destinatario della chiamata negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="f49ea-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="f49ea-514">smallint</span><span class="sxs-lookup"><span data-stu-id="f49ea-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-515">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="f49ea-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="f49ea-516">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="f49ea-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="f49ea-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="f49ea-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f49ea-519">Cause di un evento di eco per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="f49ea-520">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f49ea-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="f49ea-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="f49ea-522">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p141">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del destinatario della chiamata. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="f49ea-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="f49ea-526">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p142">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del destinatario della chiamata. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-530">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-530">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p143">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra [-30 e -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f49ea-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f49ea-535">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-535">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p144">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="f49ea-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="f49ea-541">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-541">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-542">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="f49ea-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-544">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f49ea-544">float</span></span></p></td>
<td><p><span data-ttu-id="f49ea-545">Radice della media dei quadrati del segnale in ingresso per il destinatario della chiamata fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-547">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-548">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="f49ea-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-550">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-551">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="f49ea-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f49ea-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f49ea-553">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-554">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="f49ea-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-555">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="f49ea-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="f49ea-556">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-556">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-557">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="f49ea-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="f49ea-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="f49ea-559">int</span><span class="sxs-lookup"><span data-stu-id="f49ea-559">int</span></span></p></td>
<td><p><span data-ttu-id="f49ea-560">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="f49ea-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-562">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-p145">MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo valido è compreso tra 1,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="f49ea-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-567">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-568">MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-569">Valore SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-570">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-571">Punteggio Listening MOS a banda larga previsto medio per l'audio inviato, inclusi il livello di parlato, il livello di disturbo e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="f49ea-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="f49ea-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="f49ea-573">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-574">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="f49ea-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="f49ea-576">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-577">Punteggio Listening MOS a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di disturbo, il codec, le condizioni della rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="f49ea-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="f49ea-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="f49ea-579">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f49ea-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f49ea-580">Valore RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f49ea-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f49ea-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="f49ea-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="f49ea-582">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-582">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-583">Indica se per la chiamata è stata utilizzata la correzione FEC audio.</span><span class="sxs-lookup"><span data-stu-id="f49ea-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f49ea-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="f49ea-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="f49ea-585">po'</span><span class="sxs-lookup"><span data-stu-id="f49ea-585">bit</span></span></p></td>
<td><p><span data-ttu-id="f49ea-586">Indica la direzione delle informazioni P-Asserted-Identity: 1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata e 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f49ea-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

