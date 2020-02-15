---
title: 'Lync Server 2013: tabella Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="a03d5-102">Tabella di sessione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a03d5-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a03d5-103">_**Ultimo argomento modificato:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="a03d5-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="a03d5-104">Ogni record rappresenta una sessione che coinvolge audio o audio e video.</span><span class="sxs-lookup"><span data-stu-id="a03d5-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="a03d5-105">Contiene informazioni generali sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="a03d5-105">It contains overall information about the session.</span></span> <span data-ttu-id="a03d5-106">Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="a03d5-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a03d5-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a03d5-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a03d5-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a03d5-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a03d5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a03d5-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a03d5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a03d5-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-116">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-116">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-117">Principale</span><span class="sxs-lookup"><span data-stu-id="a03d5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a03d5-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-120">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-120">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-122">Chiave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a03d5-122">Conference key.</span></span> <span data-ttu-id="a03d5-123">A cui viene fatto riferimento dalla <a href="lync-server-2013-conference-table.md">tabella conferenze in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-125">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-125">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-126">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-127">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="a03d5-127">Correlation key.</span></span> <span data-ttu-id="a03d5-128">A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-130">po'</span><span class="sxs-lookup"><span data-stu-id="a03d5-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a03d5-131">Categoria della finestra di dialogo; 0 è Lync Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="a03d5-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-133">po'</span><span class="sxs-lookup"><span data-stu-id="a03d5-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a03d5-134">Flag che indica se la chiamata è stata o meno ignorata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-136">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a03d5-137">Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass.</span><span class="sxs-lookup"><span data-stu-id="a03d5-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="a03d5-138">Per Lync Server, viene definito un solo valore.</span><span class="sxs-lookup"><span data-stu-id="a03d5-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="a03d5-139">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="a03d5-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-141">datetime</span><span class="sxs-lookup"><span data-stu-id="a03d5-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a03d5-142">Ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-144">datetime</span><span class="sxs-lookup"><span data-stu-id="a03d5-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a03d5-145">Ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-147">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-147">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-148">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-149">Il pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a03d5-149">The pool of the caller.</span></span> <span data-ttu-id="a03d5-150">A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-152">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-152">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-153">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-154">Il pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-154">The pool of the call receiver.</span></span> <span data-ttu-id="a03d5-155">A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-157">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-157">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-158">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-159">URI SIP nell'identità p-Asserted SIP (PAI) dell'endpoint di ricezione.</span><span class="sxs-lookup"><span data-stu-id="a03d5-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="a03d5-160">A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-162">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-162">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-163">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-164">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a03d5-164">Caller’s URI.</span></span> <span data-ttu-id="a03d5-165">A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-167">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-167">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-168">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-169">Endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a03d5-169">Caller’s endpoint.</span></span> <span data-ttu-id="a03d5-170">A cui viene fatto riferimento dalla <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-172">po'</span><span class="sxs-lookup"><span data-stu-id="a03d5-172">bit</span></span></p></td>
<td><p><span data-ttu-id="a03d5-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-174">Agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a03d5-174">Caller’s user agent.</span></span> <span data-ttu-id="a03d5-175">A cui viene fatto riferimento dalla <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a03d5-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-177">smallint</span><span class="sxs-lookup"><span data-stu-id="a03d5-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a03d5-178">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-180">po'</span><span class="sxs-lookup"><span data-stu-id="a03d5-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a03d5-181">Questa colonna è obsoleta e non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a03d5-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a03d5-182">Invece, queste informazioni vengono riportate in base alle linee per i media.</span><span class="sxs-lookup"><span data-stu-id="a03d5-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="a03d5-183">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a03d5-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-185">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-185">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-186">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-187">P-Asserted-Identity dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="a03d5-188">L'identità P-Asserted-Identity (PAI) viene utilizzata per trasmettere la vera identità dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-190">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-190">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-191">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-192">Endpoint che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a03d5-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-194">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-194">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-195">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-196">Agente utente impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="a03d5-197">Gli agenti utente rappresentano il dispositivo endpoint client.</span><span class="sxs-lookup"><span data-stu-id="a03d5-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a03d5-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="a03d5-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a03d5-199">int</span><span class="sxs-lookup"><span data-stu-id="a03d5-199">int</span></span></p></td>
<td><p><span data-ttu-id="a03d5-200">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a03d5-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a03d5-201">URI SIP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a03d5-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

