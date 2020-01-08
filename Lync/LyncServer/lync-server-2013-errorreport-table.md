---
title: 'Lync Server 2013: Tabella ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="f90da-102">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f90da-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f90da-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f90da-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f90da-104">La Tabella ErrorReport archivia le informazioni sugli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="f90da-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="f90da-105">Ogni record è un'occorrenza di errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-105">Each record is one error occurrence.</span></span> <span data-ttu-id="f90da-106">Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="f90da-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f90da-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="f90da-107">Column</span></span></th>
<th><span data-ttu-id="f90da-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f90da-108">Data Type</span></span></th>
<th><span data-ttu-id="f90da-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="f90da-109">Key/Index</span></span></th>
<th><span data-ttu-id="f90da-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f90da-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f90da-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="f90da-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f90da-113">Principale</span><span class="sxs-lookup"><span data-stu-id="f90da-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f90da-114">Data e ora in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-116">int</span><span class="sxs-lookup"><span data-stu-id="f90da-116">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-117">Principale</span><span class="sxs-lookup"><span data-stu-id="f90da-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f90da-118">Numero ID per identificare il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="f90da-118">ID number to identify the error report.</span></span> <span data-ttu-id="f90da-119">Usato in combinazione con <strong>ErrorTime</strong> per identificare in modo univoco una segnalazione di errori.</span><span class="sxs-lookup"><span data-stu-id="f90da-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-121">int</span><span class="sxs-lookup"><span data-stu-id="f90da-121">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-123">ID univoco del tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-123">Unique ID of the error type.</span></span> <span data-ttu-id="f90da-124">Per altre informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-126">int</span><span class="sxs-lookup"><span data-stu-id="f90da-126">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-128">Utente che ha originato la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="f90da-129">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-130"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-131">int</span><span class="sxs-lookup"><span data-stu-id="f90da-131">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-132">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-133">Utente di destinazione per la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="f90da-134">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-136">int</span><span class="sxs-lookup"><span data-stu-id="f90da-136">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-137">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-138">URI della conferenza correlato all'errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-138">Conference URI related to the error.</span></span> <span data-ttu-id="f90da-139">Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f90da-140">In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</span><span class="sxs-lookup"><span data-stu-id="f90da-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="f90da-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="f90da-143">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-144">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="f90da-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f90da-145">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-147">int</span><span class="sxs-lookup"><span data-stu-id="f90da-147">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-148">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-149">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="f90da-149">ID number to identify the session.</span></span> <span data-ttu-id="f90da-150">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="f90da-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f90da-151">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-153">int</span><span class="sxs-lookup"><span data-stu-id="f90da-153">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-154">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-155">Server che ha inviato il report degli errori (se il report viene inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="f90da-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f90da-156">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f90da-157">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f90da-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-159">int</span><span class="sxs-lookup"><span data-stu-id="f90da-159">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-160">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-161">Server che ha inviato il report degli errori (se il report viene inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="f90da-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f90da-162">Per altre informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella delle applicazioni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f90da-163">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f90da-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-165">image</span><span class="sxs-lookup"><span data-stu-id="f90da-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f90da-166">Altre informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-166">More information about the error.</span></span></p>
<p><span data-ttu-id="f90da-167">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f90da-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-169">int</span><span class="sxs-lookup"><span data-stu-id="f90da-169">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-170">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-171">Versione client di endpoint che invia il report di errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="f90da-172">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f90da-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-174">po'</span><span class="sxs-lookup"><span data-stu-id="f90da-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f90da-175">È il rapporto di errore acquisito dall'agente CDR in uso nel server front-end o inviato dal client.</span><span class="sxs-lookup"><span data-stu-id="f90da-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-176"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-177">smallint</span><span class="sxs-lookup"><span data-stu-id="f90da-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f90da-178">Riservato per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f90da-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="f90da-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f90da-181">Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f90da-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="f90da-182">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f90da-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-184">int</span><span class="sxs-lookup"><span data-stu-id="f90da-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f90da-185">Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f90da-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="f90da-186">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f90da-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f90da-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-188">int</span><span class="sxs-lookup"><span data-stu-id="f90da-188">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-189">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-190">Rappresenta il nome di dominio completo del server che ha generato il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="f90da-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f90da-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="f90da-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f90da-192">int</span><span class="sxs-lookup"><span data-stu-id="f90da-192">int</span></span></p></td>
<td><p><span data-ttu-id="f90da-193">Esterna</span><span class="sxs-lookup"><span data-stu-id="f90da-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f90da-194">Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</span><span class="sxs-lookup"><span data-stu-id="f90da-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

