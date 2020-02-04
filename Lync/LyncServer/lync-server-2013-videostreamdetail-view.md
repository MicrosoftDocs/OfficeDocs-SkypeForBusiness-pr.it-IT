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
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="15115-102">Visualizzazione VideoStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15115-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15115-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="15115-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="15115-104">La visualizzazione VideoStreamDetail archivia le informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="15115-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="15115-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15115-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15115-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="15115-106">Column</span></span></th>
<th><span data-ttu-id="15115-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="15115-107">Data Type</span></span></th>
<th><span data-ttu-id="15115-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15115-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15115-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="15115-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="15115-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="15115-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="15115-111">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15115-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="15115-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="15115-113">int</span><span class="sxs-lookup"><span data-stu-id="15115-113">int</span></span></p></td>
<td><p><span data-ttu-id="15115-114">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15115-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="15115-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="15115-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15115-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="15115-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="15115-119">int</span><span class="sxs-lookup"><span data-stu-id="15115-119">int</span></span></p></td>
<td><p><span data-ttu-id="15115-120">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="15115-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="15115-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="15115-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="15115-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="15115-123">Ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="15115-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="15115-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="15115-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="15115-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="15115-126">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="15115-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="15115-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="15115-128">int</span><span class="sxs-lookup"><span data-stu-id="15115-128">int</span></span></p></td>
<td><p><span data-ttu-id="15115-129">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="15115-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="15115-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="15115-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-132">FQDN del pool chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="15115-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="15115-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-135">Nome di dominio completo del pool di chiamate.</span><span class="sxs-lookup"><span data-stu-id="15115-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-136">Chiamante</span><span class="sxs-lookup"><span data-stu-id="15115-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="15115-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="15115-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="15115-138">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-139">Chiamato</span><span class="sxs-lookup"><span data-stu-id="15115-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="15115-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="15115-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="15115-141">URI del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="15115-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="15115-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-144">Stringa agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="15115-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="15115-146">smallint</span><span class="sxs-lookup"><span data-stu-id="15115-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="15115-147">Tipo di agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-147">Type of caller’s user agent.</span></span> <span data-ttu-id="15115-148">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="15115-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="15115-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="15115-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="15115-151">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-151">Category of caller’s user agent.</span></span> <span data-ttu-id="15115-152">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="15115-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="15115-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-155">Stringa agente utente del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="15115-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="15115-157">smallint</span><span class="sxs-lookup"><span data-stu-id="15115-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="15115-158">Tipo di agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-158">Type of callee’s user agent.</span></span> <span data-ttu-id="15115-159">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="15115-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="15115-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="15115-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="15115-162">Categoria dell'agente utente del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-162">Category of callee’s user agent.</span></span> <span data-ttu-id="15115-163">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="15115-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="15115-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-166">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="15115-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="15115-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-169">Nome dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="15115-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="15115-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-172">Sistema operativo (OS) dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="15115-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="15115-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-175">Sistema operativo (OS) dell'endpoint del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="15115-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="15115-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-178">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="15115-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="15115-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-181">Nome della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="15115-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="15115-183">smallint</span><span class="sxs-lookup"><span data-stu-id="15115-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="15115-184">Numero di core della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="15115-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="15115-186">smallint</span><span class="sxs-lookup"><span data-stu-id="15115-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="15115-187">Numero di core della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="15115-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="15115-189">int</span><span class="sxs-lookup"><span data-stu-id="15115-189">int</span></span></p></td>
<td><p><span data-ttu-id="15115-190">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="15115-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="15115-192">int</span><span class="sxs-lookup"><span data-stu-id="15115-192">int</span></span></p></td>
<td><p><span data-ttu-id="15115-193">Velocità del processore della CPU dell'endpoint del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="15115-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="15115-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-196">Indica se il sistema del chiamante è in uso in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="15115-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="15115-197">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="15115-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="15115-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-200">Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="15115-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="15115-201">Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="15115-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="15115-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-204">Informazioni sul percorso multimediale, ad esempio Direct o inoltrata.</span><span class="sxs-lookup"><span data-stu-id="15115-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="15115-205">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="15115-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="15115-207">int</span><span class="sxs-lookup"><span data-stu-id="15115-207">int</span></span></p></td>
<td><p><span data-ttu-id="15115-208">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="15115-209">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="15115-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="15115-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="15115-211">int</span><span class="sxs-lookup"><span data-stu-id="15115-211">int</span></span></p></td>
<td><p><span data-ttu-id="15115-212">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="15115-213">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="15115-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-214">Transport</span><span class="sxs-lookup"><span data-stu-id="15115-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="15115-215">int</span><span class="sxs-lookup"><span data-stu-id="15115-215">int</span></span></p></td>
<td><p><span data-ttu-id="15115-216">Tipo di trasporto: 0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="15115-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="15115-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="15115-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="15115-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="15115-219">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-219">IP address of the caller.</span></span> <span data-ttu-id="15115-220">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="15115-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="15115-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="15115-222">int</span><span class="sxs-lookup"><span data-stu-id="15115-222">int</span></span></p></td>
<td><p><span data-ttu-id="15115-223">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="15115-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="15115-225">po'</span><span class="sxs-lookup"><span data-stu-id="15115-225">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-226">Indica se il chiamante si trova all'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15115-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="15115-227">1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="15115-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="15115-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="15115-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="15115-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="15115-230">Indirizzo IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-230">IP address of the callee.</span></span> <span data-ttu-id="15115-231">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="15115-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="15115-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="15115-233">int</span><span class="sxs-lookup"><span data-stu-id="15115-233">int</span></span></p></td>
<td><p><span data-ttu-id="15115-234">Porta utilizzata dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="15115-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="15115-236">po'</span><span class="sxs-lookup"><span data-stu-id="15115-236">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-237">Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il visitatore si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="15115-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="15115-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="15115-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-240">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="15115-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="15115-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-243">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="15115-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="15115-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-246">Nome del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="15115-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="15115-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="15115-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="15115-249">Nome del paese/area geografica del sito del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="15115-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="15115-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="15115-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="15115-252">Indirizzo IP del servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="15115-253">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="15115-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="15115-255">int</span><span class="sxs-lookup"><span data-stu-id="15115-255">int</span></span></p></td>
<td><p><span data-ttu-id="15115-256">Porta nel servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="15115-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="15115-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="15115-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="15115-259">Chiave indirizzo IP del servizio A/V Edge usato dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="15115-260">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="15115-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="15115-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="15115-262">int</span><span class="sxs-lookup"><span data-stu-id="15115-262">int</span></span></p></td>
<td><p><span data-ttu-id="15115-263">Porta nel servizio A/V Edge usato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="15115-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="15115-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-266">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="15115-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="15115-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-269">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="15115-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="15115-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-272">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="15115-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="15115-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-275">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="15115-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="15115-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-278">Nome del dispositivo di acquisizione del chiamato.</span><span class="sxs-lookup"><span data-stu-id="15115-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="15115-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="15115-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-281">Nome del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="15115-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="15115-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-284">Nome del driver del dispositivo di acquisizione del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="15115-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="15115-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="15115-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15115-287">Nome del driver del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15115-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="15115-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="15115-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-290">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="15115-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="15115-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="15115-292">po'</span><span class="sxs-lookup"><span data-stu-id="15115-292">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-293">Indica se il chiamante è connesso o meno tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="15115-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="15115-294">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="15115-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="15115-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="15115-296">decimale (18)</span><span class="sxs-lookup"><span data-stu-id="15115-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="15115-297">Velocità di collegamento di rete per l'endpoint del chiamante in bps.</span><span class="sxs-lookup"><span data-stu-id="15115-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="15115-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="15115-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="15115-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15115-300">Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</span><span class="sxs-lookup"><span data-stu-id="15115-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="15115-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="15115-302">po'</span><span class="sxs-lookup"><span data-stu-id="15115-302">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-303">Indica se il chiamato è connesso o meno tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="15115-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="15115-304">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="15115-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="15115-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="15115-306">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="15115-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="15115-307">Velocità di collegamento di rete per l'endpoint del destinatario della chiamata (in bps).</span><span class="sxs-lookup"><span data-stu-id="15115-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="15115-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="15115-309">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="15115-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="15115-310">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="15115-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="15115-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="15115-312">int</span><span class="sxs-lookup"><span data-stu-id="15115-312">int</span></span></p></td>
<td><p><span data-ttu-id="15115-313">Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="15115-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="15115-314">Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="15115-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="15115-315">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="15115-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="15115-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="15115-317">int</span><span class="sxs-lookup"><span data-stu-id="15115-317">int</span></span></p></td>
<td><p><span data-ttu-id="15115-318">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="15115-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="15115-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="15115-320">int</span><span class="sxs-lookup"><span data-stu-id="15115-320">int</span></span></p></td>
<td><p><span data-ttu-id="15115-321">Variazione massima della rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="15115-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="15115-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="15115-323">int</span><span class="sxs-lookup"><span data-stu-id="15115-323">int</span></span></p></td>
<td><p><span data-ttu-id="15115-324">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="15115-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="15115-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="15115-326">int</span><span class="sxs-lookup"><span data-stu-id="15115-326">int</span></span></p></td>
<td><p><span data-ttu-id="15115-327">Tempo massimo di andata e ritorno per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="15115-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="15115-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="15115-329">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="15115-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="15115-330">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="15115-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="15115-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="15115-332">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="15115-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="15115-333">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="15115-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="15115-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="15115-335">int</span><span class="sxs-lookup"><span data-stu-id="15115-335">int</span></span></p></td>
<td><p><span data-ttu-id="15115-336">Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).</span><span class="sxs-lookup"><span data-stu-id="15115-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-337">Larghezza di banda più ampia</span><span class="sxs-lookup"><span data-stu-id="15115-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="15115-338">int</span><span class="sxs-lookup"><span data-stu-id="15115-338">int</span></span></p></td>
<td><p><span data-ttu-id="15115-339">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="15115-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="15115-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="15115-341">int</span><span class="sxs-lookup"><span data-stu-id="15115-341">int</span></span></p></td>
<td><p><span data-ttu-id="15115-342">Codec audio usato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15115-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="15115-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="15115-344">codice.caratt(9</span><span class="sxs-lookup"><span data-stu-id="15115-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="15115-345">Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel.</span><span class="sxs-lookup"><span data-stu-id="15115-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="15115-346">Segnalato come stringa.</span><span class="sxs-lookup"><span data-stu-id="15115-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="15115-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="15115-348">int</span><span class="sxs-lookup"><span data-stu-id="15115-348">int</span></span></p></td>
<td><p><span data-ttu-id="15115-349">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="15115-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="15115-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="15115-351">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="15115-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="15115-352">Frequenza fotogrammi del video ricevuto.</span><span class="sxs-lookup"><span data-stu-id="15115-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="15115-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="15115-354">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="15115-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="15115-355">Frequenza fotogrammi del video inviato.</span><span class="sxs-lookup"><span data-stu-id="15115-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="15115-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="15115-357">int</span><span class="sxs-lookup"><span data-stu-id="15115-357">int</span></span></p></td>
<td><p><span data-ttu-id="15115-358">Velocità in bit massima video durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="15115-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-359">Flussi</span><span class="sxs-lookup"><span data-stu-id="15115-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="15115-360">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="15115-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="15115-361">Frequenza con cui sono stati persi i pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="15115-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="15115-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="15115-363">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="15115-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="15115-364">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="15115-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="15115-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="15115-366">po'</span><span class="sxs-lookup"><span data-stu-id="15115-366">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-367">Non usato.</span><span class="sxs-lookup"><span data-stu-id="15115-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="15115-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="15115-369">int</span><span class="sxs-lookup"><span data-stu-id="15115-369">int</span></span></p></td>
<td><p><span data-ttu-id="15115-370">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="15115-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15115-371">Flussi</span><span class="sxs-lookup"><span data-stu-id="15115-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="15115-372">decimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="15115-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="15115-373">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="15115-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15115-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="15115-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="15115-375">po'</span><span class="sxs-lookup"><span data-stu-id="15115-375">bit</span></span></p></td>
<td><p><span data-ttu-id="15115-376">Direzione del flusso per le informazioni sull'identità asserite da p.</span><span class="sxs-lookup"><span data-stu-id="15115-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="15115-377">1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="15115-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

