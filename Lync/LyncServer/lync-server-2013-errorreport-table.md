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
ms.openlocfilehash: 0fad1f4138f1fae95f4e3d2ea88c8a8c72f7198a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="53057-102">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53057-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53057-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="53057-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="53057-104">Nella Tabella ErrorReport vengono archiviate informazioni sugli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="53057-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="53057-105">Ogni record corrisponde a un'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="53057-105">Each record is one error occurrence.</span></span> <span data-ttu-id="53057-106">Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="53057-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53057-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="53057-107">Column</span></span></th>
<th><span data-ttu-id="53057-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="53057-108">Data Type</span></span></th>
<th><span data-ttu-id="53057-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="53057-109">Key/Index</span></span></th>
<th><span data-ttu-id="53057-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="53057-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53057-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="53057-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-112">datetime</span><span class="sxs-lookup"><span data-stu-id="53057-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="53057-113">Principale</span><span class="sxs-lookup"><span data-stu-id="53057-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="53057-114">Data e ora in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="53057-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53057-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-116">int</span><span class="sxs-lookup"><span data-stu-id="53057-116">int</span></span></p></td>
<td><p><span data-ttu-id="53057-117">Principale</span><span class="sxs-lookup"><span data-stu-id="53057-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="53057-118">Numero ID per identificare la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="53057-118">ID number to identify the error report.</span></span> <span data-ttu-id="53057-119">Utilizzato insieme a <strong>ErrorTime</strong> per identificare in modo univoco un report di errore.</span><span class="sxs-lookup"><span data-stu-id="53057-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-121">int</span><span class="sxs-lookup"><span data-stu-id="53057-121">int</span></span></p></td>
<td><p><span data-ttu-id="53057-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-123">ID univoco del tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="53057-123">Unique ID of the error type.</span></span> <span data-ttu-id="53057-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-126">int</span><span class="sxs-lookup"><span data-stu-id="53057-126">int</span></span></p></td>
<td><p><span data-ttu-id="53057-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-128">Utente che ha originato la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="53057-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="53057-129">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-130"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="53057-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-131">int</span><span class="sxs-lookup"><span data-stu-id="53057-131">int</span></span></p></td>
<td><p><span data-ttu-id="53057-132">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-133">Utente di destinazione per la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="53057-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="53057-134">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-136">int</span><span class="sxs-lookup"><span data-stu-id="53057-136">int</span></span></p></td>
<td><p><span data-ttu-id="53057-137">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-138">URI della conferenza relativo all'errore.</span><span class="sxs-lookup"><span data-stu-id="53057-138">Conference URI related to the error.</span></span> <span data-ttu-id="53057-139">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="53057-140">In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</span><span class="sxs-lookup"><span data-stu-id="53057-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="53057-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-142">datetime</span><span class="sxs-lookup"><span data-stu-id="53057-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="53057-143">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-144">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="53057-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="53057-145">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53057-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-147">int</span><span class="sxs-lookup"><span data-stu-id="53057-147">int</span></span></p></td>
<td><p><span data-ttu-id="53057-148">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-149">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="53057-149">ID number to identify the session.</span></span> <span data-ttu-id="53057-150">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="53057-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="53057-151">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-153">int</span><span class="sxs-lookup"><span data-stu-id="53057-153">int</span></span></p></td>
<td><p><span data-ttu-id="53057-154">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-155">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="53057-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="53057-156">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="53057-157">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53057-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-159">int</span><span class="sxs-lookup"><span data-stu-id="53057-159">int</span></span></p></td>
<td><p><span data-ttu-id="53057-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-161">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="53057-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="53057-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella applicazioni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="53057-163">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53057-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="53057-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-165">immagine</span><span class="sxs-lookup"><span data-stu-id="53057-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53057-166">Ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="53057-166">More information about the error.</span></span></p>
<p><span data-ttu-id="53057-167">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="53057-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-169">int</span><span class="sxs-lookup"><span data-stu-id="53057-169">int</span></span></p></td>
<td><p><span data-ttu-id="53057-170">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-171">La versione client di endpoint che invia la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="53057-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="53057-172">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53057-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="53057-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-174">po'</span><span class="sxs-lookup"><span data-stu-id="53057-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53057-175">È la segnalazione errori acquisita dall'agente di registrazione dettagli chiamata in esecuzione nel server front-end o inviata dal client.</span><span class="sxs-lookup"><span data-stu-id="53057-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-176"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="53057-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-177">smallint</span><span class="sxs-lookup"><span data-stu-id="53057-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53057-178">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="53057-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="53057-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53057-181">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="53057-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="53057-182">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53057-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="53057-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-184">int</span><span class="sxs-lookup"><span data-stu-id="53057-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53057-185">Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="53057-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="53057-186">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53057-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53057-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-188">int</span><span class="sxs-lookup"><span data-stu-id="53057-188">int</span></span></p></td>
<td><p><span data-ttu-id="53057-189">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-190">Rappresenta il nome di dominio completo del server che ha generato la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="53057-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53057-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="53057-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="53057-192">int</span><span class="sxs-lookup"><span data-stu-id="53057-192">int</span></span></p></td>
<td><p><span data-ttu-id="53057-193">Stranieri</span><span class="sxs-lookup"><span data-stu-id="53057-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53057-194">Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</span><span class="sxs-lookup"><span data-stu-id="53057-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

