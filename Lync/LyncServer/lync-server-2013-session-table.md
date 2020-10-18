---
title: 'Lync Server 2013: tabella Session'
description: 'Lync Server 2013: tabella Session.'
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
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576452"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="f63aa-103">Tabella di sessione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f63aa-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f63aa-104">_**Ultimo argomento modificato:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="f63aa-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="f63aa-105">Ogni record rappresenta una sessione che coinvolge audio o audio e video.</span><span class="sxs-lookup"><span data-stu-id="f63aa-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="f63aa-106">Contiene informazioni generali sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="f63aa-106">It contains overall information about the session.</span></span> <span data-ttu-id="f63aa-107">Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="f63aa-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f63aa-108"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f63aa-109"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f63aa-110"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f63aa-111"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f63aa-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="f63aa-114">Principale</span><span class="sxs-lookup"><span data-stu-id="f63aa-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="f63aa-115">A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-117">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-117">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-118">Principale</span><span class="sxs-lookup"><span data-stu-id="f63aa-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="f63aa-119">A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-121">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-121">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-123">Chiave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="f63aa-123">Conference key.</span></span> <span data-ttu-id="f63aa-124">A cui viene fatto riferimento dalla <a href="lync-server-2013-conference-table.md">tabella conferenze in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-126">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-126">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-128">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="f63aa-128">Correlation key.</span></span> <span data-ttu-id="f63aa-129">A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-131">po'</span><span class="sxs-lookup"><span data-stu-id="f63aa-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f63aa-132">Categoria della finestra di dialogo; 0 è Lync Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f63aa-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-134">po'</span><span class="sxs-lookup"><span data-stu-id="f63aa-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f63aa-135">Flag che indica se la chiamata è stata o meno ignorata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-137">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f63aa-138">Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass.</span><span class="sxs-lookup"><span data-stu-id="f63aa-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="f63aa-139">Per Lync Server, viene definito un solo valore.</span><span class="sxs-lookup"><span data-stu-id="f63aa-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="f63aa-140">0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="f63aa-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-142">datetime</span><span class="sxs-lookup"><span data-stu-id="f63aa-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f63aa-143">Ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-145">datetime</span><span class="sxs-lookup"><span data-stu-id="f63aa-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f63aa-146">Ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-148">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-148">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-149">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-150">Il pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f63aa-150">The pool of the caller.</span></span> <span data-ttu-id="f63aa-151">A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-153">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-153">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-154">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-155">Il pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-155">The pool of the call receiver.</span></span> <span data-ttu-id="f63aa-156">A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-158">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-158">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-159">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-160">URI SIP nell'identità p-Asserted SIP (PAI) dell'endpoint di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f63aa-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="f63aa-161">A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-163">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-163">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-164">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-165">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f63aa-165">Caller’s URI.</span></span> <span data-ttu-id="f63aa-166">A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-168">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-168">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-169">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-170">Endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f63aa-170">Caller’s endpoint.</span></span> <span data-ttu-id="f63aa-171">A cui viene fatto riferimento dalla <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-173">po'</span><span class="sxs-lookup"><span data-stu-id="f63aa-173">bit</span></span></p></td>
<td><p><span data-ttu-id="f63aa-174">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-175">Agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f63aa-175">Caller’s user agent.</span></span> <span data-ttu-id="f63aa-176">A cui viene fatto riferimento dalla <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f63aa-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-178">smallint</span><span class="sxs-lookup"><span data-stu-id="f63aa-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f63aa-179">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-181">po'</span><span class="sxs-lookup"><span data-stu-id="f63aa-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f63aa-182">Questa colonna è obsoleta e non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f63aa-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f63aa-183">Invece, queste informazioni vengono riportate in base alle linee per i media.</span><span class="sxs-lookup"><span data-stu-id="f63aa-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="f63aa-184">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f63aa-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-186">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-186">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-187">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-188">P-Asserted-Identity dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="f63aa-189">L'identità P-Asserted-Identity (PAI) viene utilizzata per trasmettere la vera identità dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-191">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-191">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-192">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-193">Endpoint che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63aa-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-195">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-195">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-196">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-197">Agente utente impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="f63aa-198">Gli agenti utente rappresentano il dispositivo endpoint client.</span><span class="sxs-lookup"><span data-stu-id="f63aa-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63aa-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="f63aa-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f63aa-200">int</span><span class="sxs-lookup"><span data-stu-id="f63aa-200">int</span></span></p></td>
<td><p><span data-ttu-id="f63aa-201">Stranieri</span><span class="sxs-lookup"><span data-stu-id="f63aa-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f63aa-202">URI SIP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f63aa-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

