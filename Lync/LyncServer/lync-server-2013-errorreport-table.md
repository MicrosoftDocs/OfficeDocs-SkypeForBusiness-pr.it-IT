---
title: 'Lync Server 2013: Tabella ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="6aeb8-102">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aeb8-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aeb8-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6aeb8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6aeb8-104">La Tabella ErrorReport archivia le informazioni sugli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="6aeb8-105">Ogni record è un'occorrenza di errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-105">Each record is one error occurrence.</span></span> <span data-ttu-id="6aeb8-106">Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6aeb8-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-107">Column</span></span></th>
<th><span data-ttu-id="6aeb8-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6aeb8-108">Data Type</span></span></th>
<th><span data-ttu-id="6aeb8-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="6aeb8-109">Key/Index</span></span></th>
<th><span data-ttu-id="6aeb8-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6aeb8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="6aeb8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-113">Principale</span><span class="sxs-lookup"><span data-stu-id="6aeb8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-114">Data e ora in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-116">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-116">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-117">Principale</span><span class="sxs-lookup"><span data-stu-id="6aeb8-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-118">Numero ID per identificare il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-118">ID number to identify the error report.</span></span> <span data-ttu-id="6aeb8-119">Usato in combinazione con <strong>ErrorTime</strong> per identificare in modo univoco una segnalazione di errori.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-121">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-121">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-123">ID univoco del tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-123">Unique ID of the error type.</span></span> <span data-ttu-id="6aeb8-124">Per altre informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-126">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-126">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-128">Utente che ha originato la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="6aeb8-129">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-130"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-131">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-131">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-132">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-133">Utente di destinazione per la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="6aeb8-134">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-136">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-136">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-137">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-138">URI della conferenza correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-138">Conference URI related to the error.</span></span> <span data-ttu-id="6aeb8-139">Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="6aeb8-140">In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="6aeb8-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-143">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-144">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6aeb8-145">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-147">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-147">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-148">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-149">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-149">ID number to identify the session.</span></span> <span data-ttu-id="6aeb8-150">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6aeb8-151">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-153">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-153">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-154">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-155">Server che ha inviato il report degli errori (se il report viene inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="6aeb8-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="6aeb8-156">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6aeb8-157">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-159">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-159">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-160">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-161">Server che ha inviato il report degli errori (se il report viene inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="6aeb8-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="6aeb8-162">Per altre informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella delle applicazioni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6aeb8-163">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-165">image</span><span class="sxs-lookup"><span data-stu-id="6aeb8-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6aeb8-166">Altre informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-166">More information about the error.</span></span></p>
<p><span data-ttu-id="6aeb8-167">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="6aeb8-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-169">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-169">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-170">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-171">Versione client di endpoint che invia il report di errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="6aeb8-172">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-174">po'</span><span class="sxs-lookup"><span data-stu-id="6aeb8-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6aeb8-175">È il rapporto di errore acquisito dall'agente CDR in uso nel server front-end o inviato dal client.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-176"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-177">smallint</span><span class="sxs-lookup"><span data-stu-id="6aeb8-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6aeb8-178">Riservato per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="6aeb8-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6aeb8-181">Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="6aeb8-182">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-184">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6aeb8-185">Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="6aeb8-186">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aeb8-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-188">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-188">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-189">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-190">Rappresenta il nome di dominio completo del server che ha generato il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aeb8-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="6aeb8-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="6aeb8-192">int</span><span class="sxs-lookup"><span data-stu-id="6aeb8-192">int</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-193">Esterna</span><span class="sxs-lookup"><span data-stu-id="6aeb8-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6aeb8-194">Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

