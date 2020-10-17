---
title: 'Lync Server 2013: visualizzazione VideoStreamDetail'
description: 'Lync Server 2013: visualizzazione VideoStreamDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567972"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="bb36d-103">Visualizzazione VideoStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb36d-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb36d-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bb36d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bb36d-105">Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="bb36d-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="bb36d-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb36d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb36d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="bb36d-107">Column</span></span></th>
<th><span data-ttu-id="bb36d-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bb36d-108">Data Type</span></span></th>
<th><span data-ttu-id="bb36d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb36d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="bb36d-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bb36d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-112">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bb36d-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="bb36d-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="bb36d-114">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-114">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-115">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bb36d-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="bb36d-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="bb36d-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bb36d-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="bb36d-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="bb36d-120">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-120">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-121">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="bb36d-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="bb36d-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-123">datetime</span><span class="sxs-lookup"><span data-stu-id="bb36d-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-124">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="bb36d-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="bb36d-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-126">datetime</span><span class="sxs-lookup"><span data-stu-id="bb36d-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb36d-127">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="bb36d-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="bb36d-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="bb36d-129">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-129">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-130">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="bb36d-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="bb36d-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-133">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="bb36d-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="bb36d-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-136">FQDN del pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-137">Chiamante</span><span class="sxs-lookup"><span data-stu-id="bb36d-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="bb36d-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bb36d-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-139">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-140">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="bb36d-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="bb36d-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bb36d-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-142">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="bb36d-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="bb36d-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-145">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="bb36d-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="bb36d-147">smallint</span><span class="sxs-lookup"><span data-stu-id="bb36d-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-148">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-148">Type of caller’s user agent.</span></span> <span data-ttu-id="bb36d-149">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="bb36d-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="bb36d-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bb36d-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-152">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-152">Category of caller’s user agent.</span></span> <span data-ttu-id="bb36d-153">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="bb36d-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="bb36d-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-156">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="bb36d-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="bb36d-158">smallint</span><span class="sxs-lookup"><span data-stu-id="bb36d-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-159">Tipo dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-159">Type of callee’s user agent.</span></span> <span data-ttu-id="bb36d-160">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="bb36d-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="bb36d-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bb36d-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-163">Categoria dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-163">Category of callee’s user agent.</span></span> <span data-ttu-id="bb36d-164">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="bb36d-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-167">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="bb36d-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-170">Nome dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="bb36d-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="bb36d-172">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-173">Sistema operativo dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="bb36d-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="bb36d-175">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-176">Sistema operativo dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="bb36d-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="bb36d-178">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-179">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="bb36d-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="bb36d-181">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-182">Nome della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="bb36d-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="bb36d-184">smallint</span><span class="sxs-lookup"><span data-stu-id="bb36d-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-185">Numero di core della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="bb36d-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="bb36d-187">smallint</span><span class="sxs-lookup"><span data-stu-id="bb36d-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-188">Nome di core della CPU dell'endpoint del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="bb36d-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="bb36d-190">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-190">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-191">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="bb36d-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="bb36d-193">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-193">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-194">Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="bb36d-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="bb36d-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-197">Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="bb36d-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="bb36d-198">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="bb36d-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="bb36d-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-201">Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="bb36d-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="bb36d-202">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="bb36d-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="bb36d-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-205">Informazioni sul percorso multimediale, ad esempio diretto o inoltrato.</span><span class="sxs-lookup"><span data-stu-id="bb36d-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="bb36d-206">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bb36d-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bb36d-208">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-208">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p109">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bb36d-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bb36d-212">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-212">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p110">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-215">Trasporto</span><span class="sxs-lookup"><span data-stu-id="bb36d-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="bb36d-216">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-216">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-217">Tipo di trasporto: 0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="bb36d-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="bb36d-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bb36d-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="bb36d-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-220">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-220">IP address of the caller.</span></span> <span data-ttu-id="bb36d-221">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="bb36d-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="bb36d-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="bb36d-223">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-223">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-224">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="bb36d-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="bb36d-226">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-226">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p112">Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="bb36d-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bb36d-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="bb36d-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-231">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-231">IP address of the callee.</span></span> <span data-ttu-id="bb36d-232">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="bb36d-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="bb36d-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="bb36d-234">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-234">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-235">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="bb36d-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="bb36d-237">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-237">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-238">Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il destinatario chiamata è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="bb36d-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="bb36d-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="bb36d-240">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-241">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="bb36d-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="bb36d-243">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-244">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="bb36d-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="bb36d-246">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-247">Nome del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="bb36d-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="bb36d-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bb36d-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-250">Nome del paese/area geografica del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bb36d-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bb36d-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="bb36d-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-253">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="bb36d-254">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="bb36d-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bb36d-256">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-256">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-257">Porta del servizio A/V Edge utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bb36d-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bb36d-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="bb36d-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-260">Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="bb36d-261">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb36d-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="bb36d-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bb36d-263">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-263">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-264">Porta del servizio A/V Edge utilizzato dal destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bb36d-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bb36d-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-267">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="bb36d-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bb36d-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-270">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bb36d-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bb36d-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-273">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="bb36d-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bb36d-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-276">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bb36d-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bb36d-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-279">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="bb36d-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bb36d-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-282">Nome del dispositivo di rendering del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bb36d-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bb36d-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-285">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="bb36d-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bb36d-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb36d-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-288">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="bb36d-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="bb36d-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-291">Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="bb36d-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="bb36d-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="bb36d-293">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-293">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p116">Indica se il chiamante si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="bb36d-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="bb36d-297">decimale (18,)</span><span class="sxs-lookup"><span data-stu-id="bb36d-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-298">Velocità del collegamento di rete per l'endpoint del chiamante (in bps).</span><span class="sxs-lookup"><span data-stu-id="bb36d-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="bb36d-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="bb36d-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb36d-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb36d-301">Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="bb36d-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="bb36d-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="bb36d-303">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-303">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p117">Indica se il destinatario chiamata si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="bb36d-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="bb36d-307">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="bb36d-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-308">Velocità del collegamento di rete per l'endpoint del destinatario chiamata (in bps).</span><span class="sxs-lookup"><span data-stu-id="bb36d-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="bb36d-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="bb36d-310">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="bb36d-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-311">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="bb36d-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="bb36d-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-313">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-313">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p118">Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="bb36d-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="bb36d-318">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-318">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-319">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="bb36d-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="bb36d-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="bb36d-321">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-321">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-322">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-323">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="bb36d-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="bb36d-324">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-324">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-325">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="bb36d-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="bb36d-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="bb36d-327">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-327">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-328">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="bb36d-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="bb36d-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="bb36d-330">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-331">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="bb36d-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="bb36d-333">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-334">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="bb36d-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="bb36d-336">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-336">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-337">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="bb36d-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-338">Larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="bb36d-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="bb36d-339">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-339">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-340">Stime di larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="bb36d-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="bb36d-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="bb36d-342">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-342">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-343">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bb36d-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="bb36d-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="bb36d-345">char (9)</span><span class="sxs-lookup"><span data-stu-id="bb36d-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p119">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="bb36d-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="bb36d-349">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-349">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-350">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="bb36d-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="bb36d-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="bb36d-352">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-353">Frequenza dei fotogrammi del video ricevuto.</span><span class="sxs-lookup"><span data-stu-id="bb36d-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="bb36d-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="bb36d-355">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-356">Frequenza dei fotogrammi del video inviato.</span><span class="sxs-lookup"><span data-stu-id="bb36d-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="bb36d-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="bb36d-358">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-358">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-359">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="bb36d-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="bb36d-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="bb36d-361">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-362">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="bb36d-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="bb36d-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="bb36d-364">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-365">Percentuale di frame video totali perduti.</span><span class="sxs-lookup"><span data-stu-id="bb36d-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="bb36d-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="bb36d-367">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-367">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-368">Non utilizzata.</span><span class="sxs-lookup"><span data-stu-id="bb36d-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="bb36d-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="bb36d-370">int</span><span class="sxs-lookup"><span data-stu-id="bb36d-370">int</span></span></p></td>
<td><p><span data-ttu-id="bb36d-371">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="bb36d-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb36d-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="bb36d-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="bb36d-373">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="bb36d-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="bb36d-374">Percentuale di frame video totali perduti.</span><span class="sxs-lookup"><span data-stu-id="bb36d-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb36d-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="bb36d-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="bb36d-376">po'</span><span class="sxs-lookup"><span data-stu-id="bb36d-376">bit</span></span></p></td>
<td><p><span data-ttu-id="bb36d-p120">Direzione del flusso per le informazioni PAI (P-Asserted Identity). 1 indica che la direzione del flusso procede dal chiamante verso il destinatario della chiamata, 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="bb36d-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

