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
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="b31bf-102">Visualizzazione AudioStreamDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b31bf-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b31bf-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b31bf-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b31bf-104">Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="b31bf-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="b31bf-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b31bf-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b31bf-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="b31bf-106">Column</span></span></th>
<th><span data-ttu-id="b31bf-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b31bf-107">Data Type</span></span></th>
<th><span data-ttu-id="b31bf-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b31bf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="b31bf-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b31bf-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-111">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b31bf-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="b31bf-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="b31bf-113">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-113">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b31bf-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="b31bf-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="b31bf-116">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-116">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-117">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="b31bf-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="b31bf-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-119">datetime</span><span class="sxs-lookup"><span data-stu-id="b31bf-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-120">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="b31bf-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="b31bf-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b31bf-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="b31bf-123">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="b31bf-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b31bf-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b31bf-125">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-125">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-126">Categoria della finestra di dialogo: 0 è il Lync Server a Mediation Server Leg; 1 è il Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b31bf-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b31bf-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b31bf-128">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-128">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-129">Flag che indica se la chiamata è stata o meno ignorata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b31bf-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b31bf-131">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-131">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p102">Se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Viene definito un solo valore:</span><span class="sxs-lookup"><span data-stu-id="b31bf-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="b31bf-134">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="b31bf-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="b31bf-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="b31bf-136">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-136">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-137">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b31bf-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b31bf-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-140">FQDN del pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b31bf-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b31bf-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-143">FQDN del pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-144">Chiamante</span><span class="sxs-lookup"><span data-stu-id="b31bf-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="b31bf-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b31bf-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-146">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-147">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="b31bf-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="b31bf-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b31bf-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-149">URI del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b31bf-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b31bf-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-152">Stringa dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b31bf-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b31bf-154">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-155">Tipo dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="b31bf-156">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b31bf-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b31bf-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b31bf-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-159">Categoria dell'agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="b31bf-160">Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b31bf-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b31bf-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-163">Stringa dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b31bf-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b31bf-165">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-166">Tipo dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-166">Type of callee’s user agent.</span></span> <span data-ttu-id="b31bf-167">Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b31bf-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b31bf-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b31bf-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-170">Categoria dell'agente utente del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-170">Category of callee’s user agent.</span></span> <span data-ttu-id="b31bf-171">Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b31bf-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-174">Nome dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b31bf-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-177">Nome dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-180">Sistema operativo dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-183">Sistema operativo dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="b31bf-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="b31bf-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-186">Nome della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="b31bf-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="b31bf-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-189">Nome della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="b31bf-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="b31bf-191">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-192">Numero di core della CPU nell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="b31bf-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="b31bf-194">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-195">Numero di core della CPU nell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="b31bf-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="b31bf-197">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-197">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-198">Velocità del processore della CPU dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="b31bf-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="b31bf-200">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-200">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-201">Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="b31bf-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="b31bf-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-204">Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="b31bf-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="b31bf-205">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="b31bf-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="b31bf-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-208">Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="b31bf-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="b31bf-209">Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="b31bf-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b31bf-211">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="b31bf-211">Correlation key.</span></span> <span data-ttu-id="b31bf-212">A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b31bf-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="b31bf-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="b31bf-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-215">Informazioni sul percorso multimediale, ad esempio diretto o inoltrato.</span><span class="sxs-lookup"><span data-stu-id="b31bf-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="b31bf-216">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b31bf-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b31bf-218">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-218">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p111">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b31bf-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b31bf-222">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-222">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p112">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-225">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b31bf-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="b31bf-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-227">Tipo di trasporto: 0 è UDP e 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="b31bf-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b31bf-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="b31bf-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-230">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-230">IP address of the caller.</span></span> <span data-ttu-id="b31bf-231">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b31bf-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="b31bf-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="b31bf-233">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-233">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-234">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="b31bf-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="b31bf-236">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-236">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-237">Indica se il chiamante è nella rete interna: 1 indica che il chiamante è all'interno della rete aziendale e 0 indica che il chiamante è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="b31bf-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="b31bf-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b31bf-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="b31bf-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-240">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-240">IP address of the callee.</span></span> <span data-ttu-id="b31bf-241">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b31bf-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="b31bf-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="b31bf-243">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-243">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-244">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="b31bf-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="b31bf-246">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-246">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-247">Indica se il destinatario della chiamata è nella rete interna: 1 indica che il destinatario della chiamata è all'interno della rete aziendale e 0 indica che il destinatario della chiamata è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="b31bf-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="b31bf-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="b31bf-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-250">Nome del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="b31bf-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="b31bf-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-253">Nome del paese/area geografica del sito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="b31bf-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="b31bf-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-256">Nome del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="b31bf-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="b31bf-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b31bf-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-259">Nome del paese/area geografica del sito del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b31bf-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b31bf-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="b31bf-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-262">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="b31bf-263">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="b31bf-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b31bf-265">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-265">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-266">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b31bf-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b31bf-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="b31bf-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-269">Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="b31bf-270">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="b31bf-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b31bf-272">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-272">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-273">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b31bf-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b31bf-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-276">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="b31bf-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b31bf-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-279">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b31bf-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b31bf-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-282">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="b31bf-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="b31bf-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-285">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b31bf-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b31bf-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-288">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="b31bf-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b31bf-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-291">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b31bf-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b31bf-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-294">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="b31bf-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b31bf-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b31bf-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-297">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="b31bf-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="b31bf-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-300">Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="b31bf-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="b31bf-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="b31bf-302">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-302">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-303">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="b31bf-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="b31bf-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="b31bf-305">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="b31bf-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-306">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="b31bf-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="b31bf-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-309">Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="b31bf-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="b31bf-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="b31bf-311">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-311">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-312">Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="b31bf-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="b31bf-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="b31bf-314">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="b31bf-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-315">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-317">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-318">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="b31bf-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="b31bf-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-320">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-320">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p117">Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="b31bf-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="b31bf-325">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-325">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-326">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="b31bf-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="b31bf-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="b31bf-328">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-328">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-329">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-331">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b31bf-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-332">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="b31bf-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="b31bf-334">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b31bf-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-335">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-336">DensitàBurst</span><span class="sxs-lookup"><span data-stu-id="b31bf-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="b31bf-337">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b31bf-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-338">Densità media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="b31bf-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="b31bf-340">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-340">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-341">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="b31bf-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="b31bf-343">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b31bf-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-344">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b31bf-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="b31bf-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="b31bf-346">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-346">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-347">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b31bf-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="b31bf-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="b31bf-349">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-349">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-350">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="b31bf-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-351">Larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="b31bf-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="b31bf-352">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-352">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-353">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="b31bf-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-355">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p118">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="b31bf-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="b31bf-361">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-362">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-364">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-365">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="b31bf-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-367">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-368">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b31bf-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="b31bf-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="b31bf-370">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-370">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-371">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b31bf-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-373">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-373">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-374">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="b31bf-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-376">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-376">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p119">Livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-382">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-382">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p120">Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-388">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-388">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p121">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-394">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-394">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p122">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="b31bf-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="b31bf-400">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-400">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p123">ERLE (Echo Return Loss Enhancement) per il chiamante. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-406">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-406">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p124">Media dei problemi di rendering dell'altoparlante del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-411">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-411">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p125">Media dei problemi di acquisizione del microfono del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="b31bf-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="b31bf-416">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-417">Deviazione del clock del dispositivo microfono del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="b31bf-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="b31bf-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="b31bf-419">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-420">Deviazione del clock del dispositivo altoparlante del chiamante rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="b31bf-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="b31bf-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="b31bf-422">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-423">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="b31bf-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="b31bf-425">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-426">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del chiamante negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="b31bf-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="b31bf-428">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-429">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="b31bf-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="b31bf-430">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="b31bf-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="b31bf-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-433">Cause di un evento di eco per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="b31bf-434">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="b31bf-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="b31bf-436">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p128">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamante. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="b31bf-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="b31bf-440">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p129">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del chiamante. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-444">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-444">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p130">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra -30 e -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-449">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-449">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p131">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="b31bf-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="b31bf-455">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-455">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-456">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="b31bf-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-458">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b31bf-458">float</span></span></p></td>
<td><p><span data-ttu-id="b31bf-459">Radice della media dei quadrati del segnale in ingresso per il chiamante fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-461">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-461">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p132">Rappresenta il livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-467">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-467">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p133">Livello di segnale audio per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-473">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-473">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p134">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-479">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-479">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p135">Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="b31bf-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="b31bf-485">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-485">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p136">ERLE (Echo Return Loss Enhancement) per il destinatario della chiamata. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-491">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-491">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p137">Media dei problemi di rendering dell'altoparlante del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="b31bf-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="b31bf-496">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-496">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p138">Media dei problemi di acquisizione del microfono del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="b31bf-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="b31bf-501">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-502">Deviazione del clock del dispositivo microfono del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="b31bf-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="b31bf-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="b31bf-504">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-505">Deviazione del clock del dispositivo altoparlante del destinatario della chiamata rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="b31bf-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="b31bf-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="b31bf-507">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-508">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="b31bf-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="b31bf-510">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-511">Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del destinatario della chiamata negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="b31bf-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="b31bf-513">smallint</span><span class="sxs-lookup"><span data-stu-id="b31bf-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-514">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="b31bf-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="b31bf-515">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="b31bf-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="b31bf-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="b31bf-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b31bf-518">Cause di un evento di eco per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="b31bf-519">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b31bf-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="b31bf-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="b31bf-521">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p141">Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del destinatario della chiamata. Se viene utilizzato un auricolare, il valore deve essere basso.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="b31bf-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="b31bf-525">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p142">Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del destinatario della chiamata. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-529">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-529">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p143">Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra [-30 e -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="b31bf-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="b31bf-534">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-534">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p144">Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="b31bf-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="b31bf-540">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-540">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-541">Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="b31bf-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-543">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b31bf-543">float</span></span></p></td>
<td><p><span data-ttu-id="b31bf-544">Radice della media dei quadrati del segnale in ingresso per il destinatario della chiamata fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-546">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-547">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="b31bf-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-549">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-550">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="b31bf-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="b31bf-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="b31bf-552">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-553">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="b31bf-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="b31bf-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="b31bf-555">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-555">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-556">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="b31bf-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="b31bf-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="b31bf-558">int</span><span class="sxs-lookup"><span data-stu-id="b31bf-558">int</span></span></p></td>
<td><p><span data-ttu-id="b31bf-559">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="b31bf-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-561">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-p145">MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo valido è compreso tra 1,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="b31bf-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-566">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-567">MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-568">Valore SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-569">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-570">Punteggio Listening MOS a banda larga previsto medio per l'audio inviato, inclusi il livello di parlato, il livello di disturbo e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="b31bf-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="b31bf-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="b31bf-572">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-573">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="b31bf-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="b31bf-575">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-576">Punteggio Listening MOS a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di disturbo, il codec, le condizioni della rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="b31bf-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="b31bf-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="b31bf-578">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b31bf-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b31bf-579">Valore RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b31bf-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b31bf-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="b31bf-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="b31bf-581">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-581">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-582">Indica se per la chiamata è stata utilizzata la correzione FEC audio.</span><span class="sxs-lookup"><span data-stu-id="b31bf-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b31bf-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="b31bf-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b31bf-584">po'</span><span class="sxs-lookup"><span data-stu-id="b31bf-584">bit</span></span></p></td>
<td><p><span data-ttu-id="b31bf-585">Indica la direzione delle informazioni P-Asserted-Identity: 1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata e 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31bf-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

