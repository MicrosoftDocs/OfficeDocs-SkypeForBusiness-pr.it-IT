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
ms.openlocfilehash: 11279857e7bf217d311f4f2eb0a54a5d5f628084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="36ec0-102">Visualizzazione AudioStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ec0-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ec0-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="36ec0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="36ec0-104">Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="36ec0-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="36ec0-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36ec0-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36ec0-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="36ec0-106">Column</span></span></th>
<th><span data-ttu-id="36ec0-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="36ec0-107">Data Type</span></span></th>
<th><span data-ttu-id="36ec0-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="36ec0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="36ec0-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="36ec0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-111">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36ec0-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="36ec0-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="36ec0-113">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-113">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36ec0-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="36ec0-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="36ec0-116">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-116">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-117">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="36ec0-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="36ec0-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-119">datetime</span><span class="sxs-lookup"><span data-stu-id="36ec0-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-120">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="36ec0-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="36ec0-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-122">datetime</span><span class="sxs-lookup"><span data-stu-id="36ec0-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="36ec0-123">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="36ec0-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="36ec0-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="36ec0-125">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-125">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-126">Categoria della finestra di dialogo: 0 è il Lync Server a Mediation Server Leg; 1 è il Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="36ec0-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="36ec0-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="36ec0-128">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-128">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-129">Flag che indica se la chiamata è stata o meno ignorata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="36ec0-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="36ec0-131">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-131">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p102">Se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="36ec0-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="36ec0-134">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="36ec0-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="36ec0-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="36ec0-136">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-136">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-137">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="36ec0-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="36ec0-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-140">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="36ec0-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="36ec0-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-143">FQDN del pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-144">Chiamante</span><span class="sxs-lookup"><span data-stu-id="36ec0-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="36ec0-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="36ec0-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-146">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-147">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="36ec0-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="36ec0-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="36ec0-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-149">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="36ec0-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="36ec0-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-152">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="36ec0-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="36ec0-154">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-155">Tipo dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="36ec0-156">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="36ec0-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="36ec0-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="36ec0-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-159">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="36ec0-160">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="36ec0-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="36ec0-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-163">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="36ec0-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="36ec0-165">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-166">Tipo dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-166">Type of callee’s user agent.</span></span> <span data-ttu-id="36ec0-167">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="36ec0-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="36ec0-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="36ec0-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-170">Categoria dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-170">Category of callee’s user agent.</span></span> <span data-ttu-id="36ec0-171">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="36ec0-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-174">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="36ec0-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-177">Nome dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-180">Sistema operativo dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-183">Sistema operativo dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="36ec0-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="36ec0-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-186">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="36ec0-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="36ec0-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-189">Nome della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="36ec0-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="36ec0-191">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-192">Numero di core della CPU nell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="36ec0-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="36ec0-194">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-195">Numero di core della CPU nell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="36ec0-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="36ec0-197">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-197">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-198">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="36ec0-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="36ec0-200">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-200">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-201">Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="36ec0-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="36ec0-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-204">Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="36ec0-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="36ec0-205">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="36ec0-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="36ec0-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-208">Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="36ec0-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="36ec0-209">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="36ec0-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36ec0-211">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="36ec0-211">Correlation key.</span></span> <span data-ttu-id="36ec0-212">A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36ec0-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="36ec0-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="36ec0-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-215">Informazioni sul percorso multimediale, ad esempio diretto o inoltrato.</span><span class="sxs-lookup"><span data-stu-id="36ec0-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="36ec0-216">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="36ec0-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="36ec0-218">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-218">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p111">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="36ec0-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="36ec0-222">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-222">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p112">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-225">Trasporto</span><span class="sxs-lookup"><span data-stu-id="36ec0-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="36ec0-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-227">Tipo di trasporto: 0 è UDP e 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="36ec0-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="36ec0-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="36ec0-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-230">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-230">IP address of the caller.</span></span> <span data-ttu-id="36ec0-231">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="36ec0-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="36ec0-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="36ec0-233">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-233">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-234">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="36ec0-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="36ec0-236">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-236">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-237">Indica se il chiamante è nella rete interna: 1 indica che il chiamante è all'interno della rete aziendale e 0 indica che il chiamante è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="36ec0-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="36ec0-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="36ec0-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="36ec0-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-240">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-240">IP address of the callee.</span></span> <span data-ttu-id="36ec0-241">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="36ec0-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="36ec0-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="36ec0-243">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-243">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-244">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="36ec0-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="36ec0-246">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-246">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-247">Indica se il destinatario della chiamata è nella rete interna: 1 indica che il destinatario della chiamata è all'interno della rete aziendale e 0 indica che il destinatario della chiamata è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="36ec0-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="36ec0-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="36ec0-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-250">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="36ec0-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="36ec0-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-253">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="36ec0-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="36ec0-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-256">Nome del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="36ec0-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="36ec0-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="36ec0-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-259">Nome del paese/area geografica del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="36ec0-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="36ec0-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="36ec0-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-262">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="36ec0-263">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="36ec0-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="36ec0-265">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-265">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-266">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="36ec0-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="36ec0-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="36ec0-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-269">Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="36ec0-270">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="36ec0-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="36ec0-272">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-272">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-273">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="36ec0-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="36ec0-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-276">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="36ec0-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="36ec0-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-279">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="36ec0-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="36ec0-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-282">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="36ec0-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="36ec0-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-285">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="36ec0-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="36ec0-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-288">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="36ec0-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="36ec0-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-291">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="36ec0-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="36ec0-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-294">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="36ec0-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="36ec0-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ec0-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-297">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="36ec0-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="36ec0-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-300">Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="36ec0-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="36ec0-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="36ec0-302">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-302">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-303">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="36ec0-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="36ec0-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="36ec0-305">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="36ec0-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-306">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="36ec0-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="36ec0-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-309">Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="36ec0-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="36ec0-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="36ec0-311">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-311">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-312">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="36ec0-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="36ec0-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="36ec0-314">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="36ec0-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-315">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-317">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-318">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="36ec0-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="36ec0-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-320">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-320">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p117">Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="36ec0-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="36ec0-325">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-325">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-326">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="36ec0-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="36ec0-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="36ec0-328">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-328">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-329">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-331">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="36ec0-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-332">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="36ec0-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="36ec0-334">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="36ec0-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-335">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-336">DensitàBurst</span><span class="sxs-lookup"><span data-stu-id="36ec0-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="36ec0-337">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="36ec0-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-338">Densità media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="36ec0-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="36ec0-340">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-340">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-341">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="36ec0-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="36ec0-343">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="36ec0-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-344">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="36ec0-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="36ec0-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="36ec0-346">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-346">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-347">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="36ec0-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="36ec0-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="36ec0-349">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-349">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-350">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="36ec0-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-351">Larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="36ec0-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="36ec0-352">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-352">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-353">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="36ec0-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-355">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p118">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="36ec0-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="36ec0-361">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-362">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-364">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-365">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="36ec0-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-367">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-368">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="36ec0-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="36ec0-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="36ec0-370">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-370">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-371">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36ec0-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-373">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-373">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-374">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="36ec0-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-376">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-376">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p119">Livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-382">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-382">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p120">Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-388">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-388">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p121">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-394">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-394">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p122">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="36ec0-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="36ec0-400">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-400">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p123">ERLE (Echo Return Loss Enhancement) per il chiamante. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-406">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-406">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p124">Media dei problemi di rendering dell'altoparlante del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-411">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-411">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p125">Media dei problemi di acquisizione del microfono del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="36ec0-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="36ec0-416">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-417">Deviazione del clock del dispositivo microfono del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="36ec0-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="36ec0-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="36ec0-419">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-420">Deviazione del clock del dispositivo altoparlante del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="36ec0-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="36ec0-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="36ec0-422">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-423">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="36ec0-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="36ec0-425">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-426">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del chiamante negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="36ec0-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="36ec0-428">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-429">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="36ec0-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="36ec0-430">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="36ec0-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="36ec0-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-433">Cause di un evento di eco per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="36ec0-434">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="36ec0-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="36ec0-436">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p128">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamante. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="36ec0-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="36ec0-440">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p129">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del chiamante. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-444">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-444">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p130">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra -30 e -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-449">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-449">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p131">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="36ec0-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="36ec0-455">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-455">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-456">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="36ec0-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-458">galleggiante</span><span class="sxs-lookup"><span data-stu-id="36ec0-458">float</span></span></p></td>
<td><p><span data-ttu-id="36ec0-459">Radice della media dei quadrati del segnale in ingresso per il chiamante fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-461">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-461">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p132">Rappresenta il livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-467">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-467">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p133">Livello di segnale audio per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-473">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-473">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p134">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-479">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-479">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p135">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="36ec0-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="36ec0-485">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-485">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p136">ERLE (Echo Return Loss Enhancement) per il destinatario della chiamata. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-491">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-491">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p137">Media dei problemi di rendering dell'altoparlante del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="36ec0-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="36ec0-496">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-496">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p138">Media dei problemi di acquisizione del microfono del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="36ec0-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="36ec0-501">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-502">Deviazione del clock del dispositivo microfono del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="36ec0-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="36ec0-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="36ec0-504">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-505">Deviazione del clock del dispositivo altoparlante del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="36ec0-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="36ec0-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="36ec0-507">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-508">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="36ec0-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="36ec0-510">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-511">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del destinatario della chiamata negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="36ec0-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="36ec0-513">smallint</span><span class="sxs-lookup"><span data-stu-id="36ec0-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-514">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="36ec0-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="36ec0-515">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="36ec0-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="36ec0-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="36ec0-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36ec0-518">Cause di un evento di eco per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="36ec0-519">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ec0-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="36ec0-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="36ec0-521">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p141">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del destinatario della chiamata. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="36ec0-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="36ec0-525">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p142">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del destinatario della chiamata. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-529">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-529">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p143">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra [-30 e -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="36ec0-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="36ec0-534">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-534">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p144">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="36ec0-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="36ec0-540">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-540">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-541">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="36ec0-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-543">galleggiante</span><span class="sxs-lookup"><span data-stu-id="36ec0-543">float</span></span></p></td>
<td><p><span data-ttu-id="36ec0-544">Radice della media dei quadrati del segnale in ingresso per il destinatario della chiamata fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-546">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-547">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="36ec0-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-549">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-550">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="36ec0-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="36ec0-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="36ec0-552">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-553">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="36ec0-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="36ec0-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="36ec0-555">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-555">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-556">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="36ec0-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="36ec0-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="36ec0-558">int</span><span class="sxs-lookup"><span data-stu-id="36ec0-558">int</span></span></p></td>
<td><p><span data-ttu-id="36ec0-559">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="36ec0-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-561">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-p145">MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo valido è compreso tra 1,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="36ec0-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-566">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-567">MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-568">Valore SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-569">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-570">Punteggio Listening MOS a banda larga previsto medio per l'audio inviato, inclusi il livello di parlato, il livello di disturbo e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="36ec0-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="36ec0-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="36ec0-572">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-573">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="36ec0-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="36ec0-575">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-576">Punteggio Listening MOS a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di disturbo, il codec, le condizioni della rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="36ec0-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="36ec0-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="36ec0-578">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="36ec0-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="36ec0-579">Valore RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36ec0-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ec0-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="36ec0-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="36ec0-581">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-581">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-582">Indica se per la chiamata è stata utilizzata la correzione FEC audio.</span><span class="sxs-lookup"><span data-stu-id="36ec0-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ec0-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="36ec0-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="36ec0-584">po'</span><span class="sxs-lookup"><span data-stu-id="36ec0-584">bit</span></span></p></td>
<td><p><span data-ttu-id="36ec0-585">Indica la direzione delle informazioni P-Asserted-Identity: 1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata e 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="36ec0-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

