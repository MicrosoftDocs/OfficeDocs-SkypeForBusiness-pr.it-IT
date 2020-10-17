---
title: 'Lync Server 2013: visualizzazione VideoStreamDetail'
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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518523"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="61b32-102">Visualizzazione VideoStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61b32-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61b32-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="61b32-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="61b32-104">Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="61b32-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="61b32-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61b32-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61b32-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="61b32-106">Column</span></span></th>
<th><span data-ttu-id="61b32-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="61b32-107">Data Type</span></span></th>
<th><span data-ttu-id="61b32-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61b32-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61b32-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="61b32-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="61b32-110">datetime</span><span class="sxs-lookup"><span data-stu-id="61b32-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="61b32-111">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61b32-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="61b32-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="61b32-113">int</span><span class="sxs-lookup"><span data-stu-id="61b32-113">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61b32-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="61b32-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="61b32-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61b32-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="61b32-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="61b32-119">int</span><span class="sxs-lookup"><span data-stu-id="61b32-119">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-120">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="61b32-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="61b32-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="61b32-122">datetime</span><span class="sxs-lookup"><span data-stu-id="61b32-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="61b32-123">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="61b32-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="61b32-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="61b32-125">datetime</span><span class="sxs-lookup"><span data-stu-id="61b32-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="61b32-126">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="61b32-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="61b32-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="61b32-128">int</span><span class="sxs-lookup"><span data-stu-id="61b32-128">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-129">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="61b32-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="61b32-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-132">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="61b32-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="61b32-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-135">FQDN del pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-136">Chiamante</span><span class="sxs-lookup"><span data-stu-id="61b32-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="61b32-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61b32-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61b32-138">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-139">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="61b32-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="61b32-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61b32-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61b32-141">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="61b32-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61b32-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-144">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="61b32-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61b32-146">smallint</span><span class="sxs-lookup"><span data-stu-id="61b32-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="61b32-147">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-147">Type of caller’s user agent.</span></span> <span data-ttu-id="61b32-148">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="61b32-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61b32-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61b32-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61b32-151">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-151">Category of caller’s user agent.</span></span> <span data-ttu-id="61b32-152">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="61b32-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61b32-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-155">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="61b32-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61b32-157">smallint</span><span class="sxs-lookup"><span data-stu-id="61b32-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="61b32-158">Tipo dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-158">Type of callee’s user agent.</span></span> <span data-ttu-id="61b32-159">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="61b32-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61b32-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61b32-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61b32-162">Categoria dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-162">Category of callee’s user agent.</span></span> <span data-ttu-id="61b32-163">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="61b32-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61b32-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-166">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="61b32-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61b32-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-169">Nome dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="61b32-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="61b32-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-172">Sistema operativo dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="61b32-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="61b32-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-175">Sistema operativo dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="61b32-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="61b32-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-178">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="61b32-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="61b32-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-181">Nome della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="61b32-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61b32-183">smallint</span><span class="sxs-lookup"><span data-stu-id="61b32-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="61b32-184">Numero di core della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="61b32-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61b32-186">smallint</span><span class="sxs-lookup"><span data-stu-id="61b32-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="61b32-187">Nome di core della CPU dell'endpoint del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="61b32-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61b32-189">int</span><span class="sxs-lookup"><span data-stu-id="61b32-189">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-190">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="61b32-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61b32-192">int</span><span class="sxs-lookup"><span data-stu-id="61b32-192">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-193">Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="61b32-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61b32-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-196">Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="61b32-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61b32-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="61b32-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61b32-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-200">Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="61b32-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61b32-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="61b32-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="61b32-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-204">Informazioni sul percorso multimediale, ad esempio diretto o inoltrato.</span><span class="sxs-lookup"><span data-stu-id="61b32-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="61b32-205">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="61b32-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61b32-207">int</span><span class="sxs-lookup"><span data-stu-id="61b32-207">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-p109">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="61b32-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="61b32-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61b32-211">int</span><span class="sxs-lookup"><span data-stu-id="61b32-211">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-p110">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="61b32-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-214">Trasporto</span><span class="sxs-lookup"><span data-stu-id="61b32-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="61b32-215">int</span><span class="sxs-lookup"><span data-stu-id="61b32-215">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-216">Tipo di trasporto: 0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="61b32-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="61b32-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61b32-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="61b32-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61b32-219">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-219">IP address of the caller.</span></span> <span data-ttu-id="61b32-220">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="61b32-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="61b32-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="61b32-222">int</span><span class="sxs-lookup"><span data-stu-id="61b32-222">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-223">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="61b32-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="61b32-225">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-225">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-p112">Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="61b32-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="61b32-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61b32-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="61b32-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61b32-230">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-230">IP address of the callee.</span></span> <span data-ttu-id="61b32-231">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="61b32-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="61b32-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="61b32-233">int</span><span class="sxs-lookup"><span data-stu-id="61b32-233">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-234">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="61b32-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="61b32-236">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-236">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-237">Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il destinatario chiamata è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="61b32-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="61b32-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="61b32-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-240">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="61b32-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="61b32-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-243">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="61b32-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="61b32-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-246">Nome del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="61b32-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="61b32-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="61b32-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61b32-249">Nome del paese/area geografica del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="61b32-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61b32-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="61b32-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61b32-252">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="61b32-253">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="61b32-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61b32-255">int</span><span class="sxs-lookup"><span data-stu-id="61b32-255">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-256">Porta del servizio A/V Edge utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="61b32-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61b32-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="61b32-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61b32-259">Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="61b32-260">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61b32-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="61b32-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61b32-262">int</span><span class="sxs-lookup"><span data-stu-id="61b32-262">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-263">Porta del servizio A/V Edge utilizzato dal destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="61b32-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61b32-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-266">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="61b32-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61b32-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-269">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="61b32-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61b32-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-272">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="61b32-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61b32-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-275">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="61b32-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61b32-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-278">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="61b32-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61b32-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-281">Nome del dispositivo di rendering del destinatario chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="61b32-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61b32-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-284">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="61b32-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61b32-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61b32-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61b32-287">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="61b32-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61b32-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-290">Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="61b32-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="61b32-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="61b32-292">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-292">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-p116">Indica se il chiamante si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="61b32-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="61b32-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61b32-296">decimale (18,)</span><span class="sxs-lookup"><span data-stu-id="61b32-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="61b32-297">Velocità del collegamento di rete per l'endpoint del chiamante (in bps).</span><span class="sxs-lookup"><span data-stu-id="61b32-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="61b32-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61b32-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="61b32-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61b32-300">Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="61b32-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="61b32-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="61b32-302">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-302">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-p117">Indica se il destinatario chiamata si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="61b32-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="61b32-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61b32-306">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="61b32-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="61b32-307">Velocità del collegamento di rete per l'endpoint del destinatario chiamata (in bps).</span><span class="sxs-lookup"><span data-stu-id="61b32-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="61b32-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="61b32-309">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61b32-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61b32-310">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="61b32-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="61b32-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="61b32-312">int</span><span class="sxs-lookup"><span data-stu-id="61b32-312">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-p118">Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="61b32-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="61b32-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="61b32-317">int</span><span class="sxs-lookup"><span data-stu-id="61b32-317">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-318">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="61b32-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="61b32-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="61b32-320">int</span><span class="sxs-lookup"><span data-stu-id="61b32-320">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-321">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="61b32-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="61b32-323">int</span><span class="sxs-lookup"><span data-stu-id="61b32-323">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-324">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="61b32-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="61b32-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="61b32-326">int</span><span class="sxs-lookup"><span data-stu-id="61b32-326">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-327">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="61b32-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="61b32-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="61b32-329">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="61b32-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-330">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="61b32-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="61b32-332">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="61b32-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-333">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="61b32-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="61b32-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="61b32-335">int</span><span class="sxs-lookup"><span data-stu-id="61b32-335">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-336">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="61b32-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-337">Larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="61b32-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="61b32-338">int</span><span class="sxs-lookup"><span data-stu-id="61b32-338">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-339">Stime di larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="61b32-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="61b32-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="61b32-341">int</span><span class="sxs-lookup"><span data-stu-id="61b32-341">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-342">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61b32-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="61b32-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="61b32-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="61b32-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="61b32-p119">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="61b32-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="61b32-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61b32-348">int</span><span class="sxs-lookup"><span data-stu-id="61b32-348">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-349">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="61b32-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="61b32-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61b32-351">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="61b32-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-352">Frequenza dei fotogrammi del video ricevuto.</span><span class="sxs-lookup"><span data-stu-id="61b32-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="61b32-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61b32-354">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="61b32-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-355">Frequenza dei fotogrammi del video inviato.</span><span class="sxs-lookup"><span data-stu-id="61b32-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="61b32-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="61b32-357">int</span><span class="sxs-lookup"><span data-stu-id="61b32-357">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-358">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="61b32-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="61b32-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="61b32-360">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="61b32-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-361">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="61b32-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="61b32-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="61b32-363">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="61b32-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-364">Percentuale di frame video totali perduti.</span><span class="sxs-lookup"><span data-stu-id="61b32-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="61b32-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="61b32-366">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-366">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-367">Non utilizzata.</span><span class="sxs-lookup"><span data-stu-id="61b32-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="61b32-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="61b32-369">int</span><span class="sxs-lookup"><span data-stu-id="61b32-369">int</span></span></p></td>
<td><p><span data-ttu-id="61b32-370">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="61b32-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61b32-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="61b32-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="61b32-372">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="61b32-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="61b32-373">Percentuale di frame video totali perduti.</span><span class="sxs-lookup"><span data-stu-id="61b32-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61b32-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="61b32-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="61b32-375">po'</span><span class="sxs-lookup"><span data-stu-id="61b32-375">bit</span></span></p></td>
<td><p><span data-ttu-id="61b32-p120">Direzione del flusso per le informazioni PAI (P-Asserted Identity). 1 indica che la direzione del flusso procede dal chiamante verso il destinatario della chiamata, 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="61b32-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

