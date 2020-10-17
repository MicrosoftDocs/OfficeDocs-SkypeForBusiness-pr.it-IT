---
title: 'Lync Server 2013: visualizzazione ErrorReport'
description: 'Lync Server 2013: visualizzazione ErrorReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572042"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="95893-103">Visualizzazione ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95893-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95893-104">_**Ultimo argomento modificato:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="95893-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="95893-105">Nella visualizzazione ErrorReport vengono archiviate informazioni sugli errori segnalati.</span><span class="sxs-lookup"><span data-stu-id="95893-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="95893-106">Ogni record corrisponde a un'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="95893-106">Each record is one error occurrence.</span></span> <span data-ttu-id="95893-107">Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="95893-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="95893-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95893-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95893-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="95893-109">Column</span></span></th>
<th><span data-ttu-id="95893-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="95893-110">Data Type</span></span></th>
<th><span data-ttu-id="95893-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="95893-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95893-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="95893-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-113">datetime</span><span class="sxs-lookup"><span data-stu-id="95893-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="95893-p102">Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="95893-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="95893-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-117">int</span><span class="sxs-lookup"><span data-stu-id="95893-117">int</span></span></p></td>
<td><p><span data-ttu-id="95893-p103">Numero ID per identificare l'errore. Valore utilizzato con ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="95893-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="95893-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-121">int</span><span class="sxs-lookup"><span data-stu-id="95893-121">int</span></span></p></td>
<td><p><span data-ttu-id="95893-122">ID diagnostica della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="95893-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="95893-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95893-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95893-125">URI dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-128">Tipo di URI dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="95893-129">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="95893-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-132">Tenant dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="95893-133">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="95893-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95893-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95893-136">URI dell'utente di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="95893-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-p106">Tipo di URI dell'utente di destinazione della segnalazione errori. Per ulteriori informazioni, vedere la tabella UriTypes.</span><span class="sxs-lookup"><span data-stu-id="95893-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-141"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="95893-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-143">Tenant dell'utente di destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="95893-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="95893-144">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="95893-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95893-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95893-147">URI della conferenza di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="95893-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-150">Tipo di URI della conferenza di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="95893-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="95893-151">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="95893-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-153">datetime</span><span class="sxs-lookup"><span data-stu-id="95893-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="95893-154">Data/ora della richiesta di sessione che ha dato origine alla segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="95893-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="95893-155">Valore utilizzato con SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="95893-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="95893-156">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="95893-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-158">int</span><span class="sxs-lookup"><span data-stu-id="95893-158">int</span></span></p></td>
<td><p><span data-ttu-id="95893-159">Numero ID per identificare la richiesta di sessione che ha dato origine alla segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="95893-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="95893-160">Valore utilizzato con SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="95893-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="95893-161">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="95893-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="95893-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="95893-p111">ID dialogo SIP della sessione che ha dato origine all'errore. Il formato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="95893-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="95893-166">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="95893-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="95893-167">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="95893-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="95893-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="95893-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="95893-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-171">Versione del client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-173">int</span><span class="sxs-lookup"><span data-stu-id="95893-173">int</span></span></p></td>
<td><p><span data-ttu-id="95893-174">Client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="95893-175">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="95893-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="95893-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="95893-178">Nome della categoria del client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="95893-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-181">Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="95893-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-182"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="95893-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-184">Nome dell'applicazione che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="95893-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="95893-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-186">int</span><span class="sxs-lookup"><span data-stu-id="95893-186">int</span></span></p></td>
<td><p><span data-ttu-id="95893-187">Codice di risposta SIP per la sessione del messaggio SIP contenente la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="95893-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-189">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="95893-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="95893-190">Tipo della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="95893-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-192">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="95893-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="95893-193">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="95893-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="95893-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95893-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95893-196">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="95893-196">Type of session.</span></span> <span data-ttu-id="95893-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-calltype-table.md">tabella CallType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95893-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="95893-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-199">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="95893-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="95893-200">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="95893-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-201"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="95893-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-202">int</span><span class="sxs-lookup"><span data-stu-id="95893-202">int</span></span></p></td>
<td><p><span data-ttu-id="95893-203">Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="95893-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="95893-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-205">po'</span><span class="sxs-lookup"><span data-stu-id="95893-205">bit</span></span></p></td>
<td><p><span data-ttu-id="95893-206">Indica se la segnalazione errori è stata acquisita dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o è stata inviata dal client.</span><span class="sxs-lookup"><span data-stu-id="95893-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-207"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="95893-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-208">smallint</span><span class="sxs-lookup"><span data-stu-id="95893-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="95893-209">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="95893-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="95893-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-211">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="95893-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="95893-212">Informazioni aggiuntive sull'errore.</span><span class="sxs-lookup"><span data-stu-id="95893-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95893-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="95893-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="95893-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="95893-215">Nome di dominio completo del front end server che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="95893-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95893-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="95893-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="95893-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="95893-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="95893-218">Nome di dominio completo del pool contenente il front end server che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="95893-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

