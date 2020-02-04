---
title: 'Lync Server 2013: Tabella Session'
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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="53c17-102">Tabella Session in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53c17-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53c17-103">_**Argomento Ultima modifica:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="53c17-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="53c17-104">Ogni record rappresenta una sessione che include audio o audio e video.</span><span class="sxs-lookup"><span data-stu-id="53c17-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="53c17-105">Contiene informazioni generali sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="53c17-105">It contains overall information about the session.</span></span> <span data-ttu-id="53c17-106">Una sessione viene definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="53c17-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53c17-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="53c17-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="53c17-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="53c17-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53c17-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="53c17-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="53c17-113">Principale</span><span class="sxs-lookup"><span data-stu-id="53c17-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="53c17-114">A cui si fa riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella della finestra di dialogo in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-116">int</span><span class="sxs-lookup"><span data-stu-id="53c17-116">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-117">Principale</span><span class="sxs-lookup"><span data-stu-id="53c17-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="53c17-118">A cui si fa riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella della finestra di dialogo in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-120">int</span><span class="sxs-lookup"><span data-stu-id="53c17-120">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-122">Tasto Conferenza.</span><span class="sxs-lookup"><span data-stu-id="53c17-122">Conference key.</span></span> <span data-ttu-id="53c17-123">A cui si fa riferimento dalla <a href="lync-server-2013-conference-table.md">tabella conferenze in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-125">int</span><span class="sxs-lookup"><span data-stu-id="53c17-125">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-126">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-127">Chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="53c17-127">Correlation key.</span></span> <span data-ttu-id="53c17-128">A cui si fa riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-130">po'</span><span class="sxs-lookup"><span data-stu-id="53c17-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53c17-131">Categoria finestra di dialogo; 0 è il server di Lync per mediazione server; 1 è Mediation Server per la gamba del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="53c17-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-133">po'</span><span class="sxs-lookup"><span data-stu-id="53c17-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53c17-134">Contrassegno che indica se la chiamata è stata ignorata o meno.</span><span class="sxs-lookup"><span data-stu-id="53c17-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-136">int</span><span class="sxs-lookup"><span data-stu-id="53c17-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53c17-137">Questo campo, se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono.</span><span class="sxs-lookup"><span data-stu-id="53c17-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="53c17-138">Per Lync Server, viene definito un solo valore.</span><span class="sxs-lookup"><span data-stu-id="53c17-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="53c17-139">0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.</span><span class="sxs-lookup"><span data-stu-id="53c17-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-141">DateTime</span><span class="sxs-lookup"><span data-stu-id="53c17-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53c17-142">Chiama ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="53c17-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="53c17-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53c17-145">Ora di fine chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-147">int</span><span class="sxs-lookup"><span data-stu-id="53c17-147">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-148">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-149">Pool del chiamante.</span><span class="sxs-lookup"><span data-stu-id="53c17-149">The pool of the caller.</span></span> <span data-ttu-id="53c17-150">A cui si fa riferimento dalla <a href="lync-server-2013-pool-table.md">tabella pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-152">int</span><span class="sxs-lookup"><span data-stu-id="53c17-152">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-153">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-154">Pool del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-154">The pool of the call receiver.</span></span> <span data-ttu-id="53c17-155">A cui si fa riferimento dalla <a href="lync-server-2013-pool-table.md">tabella pool in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-157">int</span><span class="sxs-lookup"><span data-stu-id="53c17-157">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-158">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-159">URI SIP nell'identità con asserzione p (PAI) SIP dell'endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53c17-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="53c17-160">A cui si fa riferimento dalla <a href="lync-server-2013-user-table.md">tabella utente in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-162">int</span><span class="sxs-lookup"><span data-stu-id="53c17-162">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-163">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-164">URI del chiamante.</span><span class="sxs-lookup"><span data-stu-id="53c17-164">Caller’s URI.</span></span> <span data-ttu-id="53c17-165">A cui si fa riferimento dalla <a href="lync-server-2013-user-table.md">tabella utente in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-167">int</span><span class="sxs-lookup"><span data-stu-id="53c17-167">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-168">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-169">Endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="53c17-169">Caller’s endpoint.</span></span> <span data-ttu-id="53c17-170">A cui si fa riferimento dalla <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-172">po'</span><span class="sxs-lookup"><span data-stu-id="53c17-172">bit</span></span></p></td>
<td><p><span data-ttu-id="53c17-173">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-174">Agente utente del chiamante.</span><span class="sxs-lookup"><span data-stu-id="53c17-174">Caller’s user agent.</span></span> <span data-ttu-id="53c17-175">A cui si fa riferimento dalla <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53c17-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-177">smallint</span><span class="sxs-lookup"><span data-stu-id="53c17-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53c17-178">Priorità di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-180">po'</span><span class="sxs-lookup"><span data-stu-id="53c17-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53c17-181">Questa colonna è stata deprecata e non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53c17-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="53c17-182">Queste informazioni vengono invece segnalate in base a una riga per media.</span><span class="sxs-lookup"><span data-stu-id="53c17-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="53c17-183">Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53c17-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-185">int</span><span class="sxs-lookup"><span data-stu-id="53c17-185">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-186">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-187">P-asserzione-identità dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="53c17-188">Il P-Asserted-Identity (PAI) viene usato per comunicare l'identità effettiva dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-190">int</span><span class="sxs-lookup"><span data-stu-id="53c17-190">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-191">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-192">Endpoint che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53c17-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-194">int</span><span class="sxs-lookup"><span data-stu-id="53c17-194">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-195">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-196">Agente utente impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="53c17-197">Gli agenti utente rappresentano il dispositivo endpoint client.</span><span class="sxs-lookup"><span data-stu-id="53c17-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53c17-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="53c17-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53c17-199">int</span><span class="sxs-lookup"><span data-stu-id="53c17-199">int</span></span></p></td>
<td><p><span data-ttu-id="53c17-200">Esterna</span><span class="sxs-lookup"><span data-stu-id="53c17-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53c17-201">URI SIP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="53c17-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

