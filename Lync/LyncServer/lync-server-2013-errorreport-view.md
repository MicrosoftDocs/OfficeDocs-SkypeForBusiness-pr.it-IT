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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="5f5b4-102">Visualizzazione ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f5b4-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f5b4-103">_**Argomento Ultima modifica:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="5f5b4-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="5f5b4-104">La visualizzazione ErrorReport archivia le informazioni sugli errori segnalati.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="5f5b4-105">Ogni record è un'occorrenza di errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-105">Each record is one error occurrence.</span></span> <span data-ttu-id="5f5b4-106">Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="5f5b4-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f5b4-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="5f5b4-108">Column</span></span></th>
<th><span data-ttu-id="5f5b4-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5f5b4-109">Data Type</span></span></th>
<th><span data-ttu-id="5f5b4-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5f5b4-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f5b4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-113">Periodo di errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-113">Time of error occurred.</span></span> <span data-ttu-id="5f5b4-114">Usato in combinazione con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-116">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-116">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-117">Numero ID per identificare l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-117">ID number to identify the error.</span></span> <span data-ttu-id="5f5b4-118">Usato in combinazione con ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-120">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-120">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-121">ID di diagnostica per il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-124">URI dell'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-127">Tipo di URI dell'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="5f5b4-128">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-131">Tenant dell'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="5f5b4-132">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-135">URI dell'utente che era la destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-138">Tipo di URI dell'utente che ha la destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="5f5b4-139">Per altre informazioni, vedere la tabella UriTypes.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-140"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-142">Tenant dell'utente destinatario della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="5f5b4-143">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-146">URI della conferenza che era la destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-149">Tipo di URI della conferenza che era la destinazione della segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="5f5b4-150">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-152">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f5b4-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-153">Ora della richiesta di sessione che ha originato il rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="5f5b4-154">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5f5b4-155">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-157">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-157">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-158">Numero ID per identificare la richiesta di sessione che ha originato il rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="5f5b4-159">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5f5b4-160">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-163">ID finestra di dialogo SIP della sessione che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="5f5b4-164">Il formato è:</span><span class="sxs-lookup"><span data-stu-id="5f5b4-164">The format is:</span></span></p>
<p><span data-ttu-id="5f5b4-165">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5f5b4-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="5f5b4-166">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5f5b4-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="5f5b4-167">Cast (ExternalId come varbinary (max)) come varchar (max))</span><span class="sxs-lookup"><span data-stu-id="5f5b4-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-170">Versione del client usata dall'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-171"><strong>TipoClient</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-172">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-172">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-173">Client usato dall'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="5f5b4-174">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-177">Nome della categoria del client usata dall'utente che ha originato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-178"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-180">Nome del server che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="5f5b4-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-181"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-183">Nome dell'applicazione che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="5f5b4-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-185">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-185">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-186">Codice di risposta SIP nella sessione del messaggio SIP contenente il report di errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-189">Tipo di richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-192">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-195">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-195">Type of session.</span></span> <span data-ttu-id="5f5b4-196">Per altre informazioni, vedere la <a href="lync-server-2013-calltype-table.md">tabella CallType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5f5b4-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5f5b4-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-199">Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-201">int</span><span class="sxs-lookup"><span data-stu-id="5f5b4-201">int</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-202">Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-204">po'</span><span class="sxs-lookup"><span data-stu-id="5f5b4-204">bit</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-205">Indica se il report di errore è stato acquisito dall'agente CDR in uso nel server front-end o inviato dal client.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-206"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-207">smallint</span><span class="sxs-lookup"><span data-stu-id="5f5b4-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-208">Riservato per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f5b4-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-211">Altre informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f5b4-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f5b4-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-214">Nome di dominio completo del server front-end che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f5b4-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5f5b4-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5f5b4-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f5b4-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f5b4-217">Nome di dominio completo del pool che contiene il front end server che ha inviato il report.</span><span class="sxs-lookup"><span data-stu-id="5f5b4-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

