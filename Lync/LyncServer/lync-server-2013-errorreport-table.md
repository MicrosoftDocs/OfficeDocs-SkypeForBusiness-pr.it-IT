---
title: 'Lync Server 2013: Tabella ErrorReport'
description: 'Lync Server 2013: Tabella ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572012"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="4e608-103">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e608-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e608-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4e608-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4e608-105">Nella Tabella ErrorReport vengono archiviate informazioni sugli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="4e608-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="4e608-106">Ogni record corrisponde a un'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-106">Each record is one error occurrence.</span></span> <span data-ttu-id="4e608-107">Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="4e608-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e608-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="4e608-108">Column</span></span></th>
<th><span data-ttu-id="4e608-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4e608-109">Data Type</span></span></th>
<th><span data-ttu-id="4e608-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="4e608-110">Key/Index</span></span></th>
<th><span data-ttu-id="4e608-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4e608-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e608-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4e608-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e608-114">Principale</span><span class="sxs-lookup"><span data-stu-id="4e608-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e608-115">Data e ora in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-117">int</span><span class="sxs-lookup"><span data-stu-id="4e608-117">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-118">Principale</span><span class="sxs-lookup"><span data-stu-id="4e608-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e608-119">Numero ID per identificare la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="4e608-119">ID number to identify the error report.</span></span> <span data-ttu-id="4e608-120">Utilizzato insieme a <strong>ErrorTime</strong> per identificare in modo univoco un report di errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-122">int</span><span class="sxs-lookup"><span data-stu-id="4e608-122">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-124">ID univoco del tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-124">Unique ID of the error type.</span></span> <span data-ttu-id="4e608-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-127">int</span><span class="sxs-lookup"><span data-stu-id="4e608-127">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-129">Utente che ha originato la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="4e608-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-131"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-132">int</span><span class="sxs-lookup"><span data-stu-id="4e608-132">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-133">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-134">Utente di destinazione per la richiesta che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="4e608-135">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-137">int</span><span class="sxs-lookup"><span data-stu-id="4e608-137">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-138">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-139">URI della conferenza relativo all'errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-139">Conference URI related to the error.</span></span> <span data-ttu-id="4e608-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4e608-141">In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</span><span class="sxs-lookup"><span data-stu-id="4e608-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-143">datetime</span><span class="sxs-lookup"><span data-stu-id="4e608-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e608-144">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-145">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4e608-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4e608-146">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-148">int</span><span class="sxs-lookup"><span data-stu-id="4e608-148">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-149">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-150">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="4e608-150">ID number to identify the session.</span></span> <span data-ttu-id="4e608-151">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4e608-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4e608-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-154">int</span><span class="sxs-lookup"><span data-stu-id="4e608-154">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-156">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="4e608-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4e608-157">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4e608-158">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e608-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-160">int</span><span class="sxs-lookup"><span data-stu-id="4e608-160">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-161">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-162">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="4e608-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4e608-163">Per ulteriori informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella applicazioni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4e608-164">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e608-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-166">immagine</span><span class="sxs-lookup"><span data-stu-id="4e608-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e608-167">Ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-167">More information about the error.</span></span></p>
<p><span data-ttu-id="4e608-168">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4e608-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-170">int</span><span class="sxs-lookup"><span data-stu-id="4e608-170">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-171">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-172">La versione client di endpoint che invia la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="4e608-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="4e608-173">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4e608-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-175">po'</span><span class="sxs-lookup"><span data-stu-id="4e608-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e608-176">È la segnalazione errori acquisita dall'agente di registrazione dettagli chiamata in esecuzione nel server front-end o inviata dal client.</span><span class="sxs-lookup"><span data-stu-id="4e608-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-177"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-178">smallint</span><span class="sxs-lookup"><span data-stu-id="4e608-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e608-179">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="4e608-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-181">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4e608-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e608-182">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="4e608-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="4e608-183">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e608-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-185">int</span><span class="sxs-lookup"><span data-stu-id="4e608-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e608-186">Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="4e608-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="4e608-187">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e608-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e608-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-189">int</span><span class="sxs-lookup"><span data-stu-id="4e608-189">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-190">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-191">Rappresenta il nome di dominio completo del server che ha generato la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="4e608-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e608-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4e608-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e608-193">int</span><span class="sxs-lookup"><span data-stu-id="4e608-193">int</span></span></p></td>
<td><p><span data-ttu-id="4e608-194">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4e608-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e608-195">Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</span><span class="sxs-lookup"><span data-stu-id="4e608-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

