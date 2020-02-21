---
title: 'Lync Server 2013: visualizzazione ErrorReport'
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
ms.openlocfilehash: e635cd289f0224a7f8d4106cecc3d8b047e9bb92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="3be03-102">Visualizzazione ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be03-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3be03-103">_**Ultimo argomento modificato:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="3be03-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="3be03-104">Nella visualizzazione ErrorReport vengono archiviate informazioni sugli errori segnalati.</span><span class="sxs-lookup"><span data-stu-id="3be03-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="3be03-105">Ogni record corrisponde a un'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-105">Each record is one error occurrence.</span></span> <span data-ttu-id="3be03-106">Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="3be03-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="3be03-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3be03-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3be03-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="3be03-108">Column</span></span></th>
<th><span data-ttu-id="3be03-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3be03-109">Data Type</span></span></th>
<th><span data-ttu-id="3be03-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3be03-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3be03-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3be03-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be03-p102">Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-116">int</span><span class="sxs-lookup"><span data-stu-id="3be03-116">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-p103">Numero ID per identificare l'errore. Valore utilizzato con ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-120">int</span><span class="sxs-lookup"><span data-stu-id="3be03-120">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-121">ID diagnostica della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be03-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be03-124">URI dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-127">Tipo di URI dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="3be03-128">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-131">Tenant dell'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="3be03-132">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be03-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be03-135">URI dell'utente di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-p106">Tipo di URI dell'utente di destinazione della segnalazione errori. Per ulteriori informazioni, vedere la tabella UriTypes.</span><span class="sxs-lookup"><span data-stu-id="3be03-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-140"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-142">Tenant dell'utente di destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="3be03-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be03-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be03-146">URI della conferenza di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-149">Tipo di URI della conferenza di destinazione della segnalazioni errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="3be03-150">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-152">datetime</span><span class="sxs-lookup"><span data-stu-id="3be03-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be03-153">Data/ora della richiesta di sessione che ha dato origine alla segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="3be03-154">Valore utilizzato con SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="3be03-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="3be03-155">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-157">int</span><span class="sxs-lookup"><span data-stu-id="3be03-157">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-158">Numero ID per identificare la richiesta di sessione che ha dato origine alla segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="3be03-159">Valore utilizzato con SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="3be03-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="3be03-160">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="3be03-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="3be03-p111">ID dialogo SIP della sessione che ha dato origine all'errore. Il formato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3be03-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="3be03-165">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="3be03-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="3be03-166">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3be03-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="3be03-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="3be03-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-170">Versione del client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-172">int</span><span class="sxs-lookup"><span data-stu-id="3be03-172">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-173">Client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="3be03-174">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3be03-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3be03-177">Nome della categoria del client utilizzato dall'utente che ha dato origine all'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-180">Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="3be03-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-181"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-183">Nome dell'applicazione che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="3be03-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-185">int</span><span class="sxs-lookup"><span data-stu-id="3be03-185">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-186">Codice di risposta SIP per la sessione del messaggio SIP contenente la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="3be03-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-188">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="3be03-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="3be03-189">Tipo della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="3be03-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-191">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="3be03-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="3be03-192">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="3be03-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be03-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be03-195">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="3be03-195">Type of session.</span></span> <span data-ttu-id="3be03-196">Per ulteriori informazioni, vedere la <a href="lync-server-2013-calltype-table.md">tabella CallType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be03-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3be03-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3be03-199">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="3be03-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-201">int</span><span class="sxs-lookup"><span data-stu-id="3be03-201">int</span></span></p></td>
<td><p><span data-ttu-id="3be03-202">Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="3be03-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-204">po'</span><span class="sxs-lookup"><span data-stu-id="3be03-204">bit</span></span></p></td>
<td><p><span data-ttu-id="3be03-205">Indica se la segnalazione errori è stata acquisita dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o è stata inviata dal client.</span><span class="sxs-lookup"><span data-stu-id="3be03-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-206"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-207">smallint</span><span class="sxs-lookup"><span data-stu-id="3be03-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="3be03-208">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="3be03-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-210">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="3be03-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="3be03-211">Informazioni aggiuntive sull'errore.</span><span class="sxs-lookup"><span data-stu-id="3be03-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be03-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="3be03-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="3be03-214">Nome di dominio completo del front end server che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="3be03-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be03-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="3be03-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3be03-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="3be03-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="3be03-217">Nome di dominio completo del pool contenente il front end server che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="3be03-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

