---
title: 'Lync Server 2013: visualizzazione VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="097ad-102">Visualizzazione VideoStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="097ad-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="097ad-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="097ad-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="097ad-104">La visualizzazione VideoStreamDetail archivia le informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="097ad-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="097ad-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="097ad-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="097ad-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="097ad-106">Column</span></span></th>
<th><span data-ttu-id="097ad-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="097ad-107">Data Type</span></span></th>
<th><span data-ttu-id="097ad-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="097ad-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="097ad-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="097ad-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="097ad-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="097ad-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="097ad-111">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="097ad-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="097ad-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="097ad-113">int</span><span class="sxs-lookup"><span data-stu-id="097ad-113">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-114">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="097ad-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="097ad-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="097ad-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="097ad-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="097ad-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="097ad-119">int</span><span class="sxs-lookup"><span data-stu-id="097ad-119">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-120">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="097ad-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="097ad-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="097ad-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="097ad-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="097ad-123">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="097ad-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="097ad-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="097ad-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="097ad-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="097ad-126">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="097ad-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="097ad-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="097ad-128">int</span><span class="sxs-lookup"><span data-stu-id="097ad-128">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-129">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="097ad-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="097ad-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="097ad-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-132">FQDN del pool chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="097ad-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="097ad-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-135">Nome di dominio completo del pool di chiamate.</span><span class="sxs-lookup"><span data-stu-id="097ad-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-136">Chiamante</span><span class="sxs-lookup"><span data-stu-id="097ad-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="097ad-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="097ad-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="097ad-138">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-139">Chiamato</span><span class="sxs-lookup"><span data-stu-id="097ad-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="097ad-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="097ad-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="097ad-141">URI del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="097ad-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="097ad-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-144">Stringa agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="097ad-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="097ad-146">smallint</span><span class="sxs-lookup"><span data-stu-id="097ad-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="097ad-147">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-147">Type of caller’s user agent.</span></span> <span data-ttu-id="097ad-148">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="097ad-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="097ad-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="097ad-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="097ad-151">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-151">Category of caller’s user agent.</span></span> <span data-ttu-id="097ad-152">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="097ad-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="097ad-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-155">Stringa agente utente del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="097ad-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="097ad-157">smallint</span><span class="sxs-lookup"><span data-stu-id="097ad-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="097ad-158">Tipo di agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-158">Type of callee’s user agent.</span></span> <span data-ttu-id="097ad-159">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="097ad-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="097ad-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="097ad-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="097ad-162">Categoria dell'agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-162">Category of callee’s user agent.</span></span> <span data-ttu-id="097ad-163">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="097ad-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="097ad-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-166">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="097ad-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="097ad-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-169">Nome dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="097ad-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="097ad-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-172">Sistema operativo (OS) dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="097ad-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="097ad-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-175">Sistema operativo (OS) dell'endpoint del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="097ad-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="097ad-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-178">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="097ad-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="097ad-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-181">Nome della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="097ad-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="097ad-183">smallint</span><span class="sxs-lookup"><span data-stu-id="097ad-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="097ad-184">Numero di core della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="097ad-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="097ad-186">smallint</span><span class="sxs-lookup"><span data-stu-id="097ad-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="097ad-187">Numero di core della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="097ad-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="097ad-189">int</span><span class="sxs-lookup"><span data-stu-id="097ad-189">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-190">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="097ad-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="097ad-192">int</span><span class="sxs-lookup"><span data-stu-id="097ad-192">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-193">Velocità del processore della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="097ad-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="097ad-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-196">Indica se il sistema del chiamante è in uso in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="097ad-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="097ad-197">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="097ad-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="097ad-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-200">Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="097ad-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="097ad-201">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="097ad-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="097ad-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-204">Informazioni sul percorso multimediale, ad esempio Direct o inoltrata.</span><span class="sxs-lookup"><span data-stu-id="097ad-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="097ad-205">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="097ad-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="097ad-207">int</span><span class="sxs-lookup"><span data-stu-id="097ad-207">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-208">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="097ad-209">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="097ad-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="097ad-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="097ad-211">int</span><span class="sxs-lookup"><span data-stu-id="097ad-211">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-212">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="097ad-213">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="097ad-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-214">Transport</span><span class="sxs-lookup"><span data-stu-id="097ad-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="097ad-215">int</span><span class="sxs-lookup"><span data-stu-id="097ad-215">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-216">Tipo di trasporto: 0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="097ad-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="097ad-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="097ad-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="097ad-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="097ad-219">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-219">IP address of the caller.</span></span> <span data-ttu-id="097ad-220">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="097ad-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="097ad-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="097ad-222">int</span><span class="sxs-lookup"><span data-stu-id="097ad-222">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-223">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="097ad-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="097ad-225">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-225">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-226">Indica se il chiamante si trova all'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="097ad-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="097ad-227">1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="097ad-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="097ad-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="097ad-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="097ad-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="097ad-230">Indirizzo IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-230">IP address of the callee.</span></span> <span data-ttu-id="097ad-231">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="097ad-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="097ad-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="097ad-233">int</span><span class="sxs-lookup"><span data-stu-id="097ad-233">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-234">Porta utilizzata dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="097ad-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="097ad-236">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-236">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-237">Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il visitatore si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="097ad-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="097ad-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="097ad-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-240">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="097ad-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="097ad-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-243">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="097ad-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="097ad-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-246">Nome del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="097ad-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="097ad-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="097ad-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="097ad-249">Nome del paese/area geografica del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="097ad-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="097ad-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="097ad-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="097ad-252">Indirizzo IP del servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="097ad-253">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="097ad-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="097ad-255">int</span><span class="sxs-lookup"><span data-stu-id="097ad-255">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-256">Porta nel servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="097ad-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="097ad-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="097ad-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="097ad-259">Chiave indirizzo IP del servizio A/V Edge usato dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="097ad-260">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="097ad-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="097ad-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="097ad-262">int</span><span class="sxs-lookup"><span data-stu-id="097ad-262">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-263">Porta nel servizio A/V Edge usato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="097ad-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="097ad-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-266">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="097ad-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="097ad-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-269">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="097ad-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="097ad-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-272">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="097ad-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="097ad-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-275">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="097ad-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="097ad-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-278">Nome del dispositivo di acquisizione del chiamato.</span><span class="sxs-lookup"><span data-stu-id="097ad-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="097ad-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="097ad-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-281">Nome del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="097ad-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="097ad-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-284">Nome del driver del dispositivo di acquisizione del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="097ad-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="097ad-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="097ad-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="097ad-287">Nome del driver del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="097ad-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="097ad-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="097ad-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-290">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="097ad-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="097ad-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="097ad-292">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-292">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-293">Indica se il chiamante è connesso o meno tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="097ad-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="097ad-294">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="097ad-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="097ad-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="097ad-296">decimale (18)</span><span class="sxs-lookup"><span data-stu-id="097ad-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="097ad-297">Velocità di collegamento di rete per l'endpoint del chiamante in bps.</span><span class="sxs-lookup"><span data-stu-id="097ad-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="097ad-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="097ad-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="097ad-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="097ad-300">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="097ad-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="097ad-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="097ad-302">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-302">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-303">Indica se il chiamato è connesso o meno tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="097ad-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="097ad-304">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="097ad-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="097ad-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="097ad-306">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="097ad-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="097ad-307">Velocità di collegamento di rete per l'endpoint del destinatario della chiamata (in bps).</span><span class="sxs-lookup"><span data-stu-id="097ad-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="097ad-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="097ad-309">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="097ad-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="097ad-310">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="097ad-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="097ad-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="097ad-312">int</span><span class="sxs-lookup"><span data-stu-id="097ad-312">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-313">Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="097ad-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="097ad-314">Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="097ad-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="097ad-315">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="097ad-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="097ad-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="097ad-317">int</span><span class="sxs-lookup"><span data-stu-id="097ad-317">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-318">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="097ad-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="097ad-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="097ad-320">int</span><span class="sxs-lookup"><span data-stu-id="097ad-320">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-321">Variazione massima della rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="097ad-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="097ad-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="097ad-323">int</span><span class="sxs-lookup"><span data-stu-id="097ad-323">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-324">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="097ad-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="097ad-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="097ad-326">int</span><span class="sxs-lookup"><span data-stu-id="097ad-326">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-327">Tempo massimo di andata e ritorno per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="097ad-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="097ad-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="097ad-329">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="097ad-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-330">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="097ad-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="097ad-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="097ad-332">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="097ad-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-333">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="097ad-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="097ad-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="097ad-335">int</span><span class="sxs-lookup"><span data-stu-id="097ad-335">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-336">Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).</span><span class="sxs-lookup"><span data-stu-id="097ad-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-337">Larghezza di banda più ampia</span><span class="sxs-lookup"><span data-stu-id="097ad-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="097ad-338">int</span><span class="sxs-lookup"><span data-stu-id="097ad-338">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-339">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="097ad-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="097ad-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="097ad-341">int</span><span class="sxs-lookup"><span data-stu-id="097ad-341">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-342">Codec audio usato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="097ad-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="097ad-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="097ad-344">codice.caratt(9</span><span class="sxs-lookup"><span data-stu-id="097ad-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="097ad-345">Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel.</span><span class="sxs-lookup"><span data-stu-id="097ad-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="097ad-346">Segnalato come stringa.</span><span class="sxs-lookup"><span data-stu-id="097ad-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="097ad-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="097ad-348">int</span><span class="sxs-lookup"><span data-stu-id="097ad-348">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-349">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="097ad-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="097ad-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="097ad-351">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="097ad-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-352">Frequenza fotogrammi del video ricevuto.</span><span class="sxs-lookup"><span data-stu-id="097ad-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="097ad-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="097ad-354">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="097ad-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-355">Frequenza fotogrammi del video inviato.</span><span class="sxs-lookup"><span data-stu-id="097ad-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="097ad-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="097ad-357">int</span><span class="sxs-lookup"><span data-stu-id="097ad-357">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-358">Velocità in bit massima video durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="097ad-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-359">Flussi</span><span class="sxs-lookup"><span data-stu-id="097ad-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="097ad-360">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="097ad-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-361">Frequenza con cui sono stati persi i pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="097ad-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="097ad-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="097ad-363">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="097ad-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-364">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="097ad-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="097ad-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="097ad-366">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-366">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-367">Non usato.</span><span class="sxs-lookup"><span data-stu-id="097ad-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="097ad-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="097ad-369">int</span><span class="sxs-lookup"><span data-stu-id="097ad-369">int</span></span></p></td>
<td><p><span data-ttu-id="097ad-370">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="097ad-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="097ad-371">Flussi</span><span class="sxs-lookup"><span data-stu-id="097ad-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="097ad-372">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="097ad-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="097ad-373">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="097ad-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="097ad-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="097ad-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="097ad-375">po'</span><span class="sxs-lookup"><span data-stu-id="097ad-375">bit</span></span></p></td>
<td><p><span data-ttu-id="097ad-376">Direzione del flusso per le informazioni sull'identità asserite da p.</span><span class="sxs-lookup"><span data-stu-id="097ad-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="097ad-377">1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="097ad-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

