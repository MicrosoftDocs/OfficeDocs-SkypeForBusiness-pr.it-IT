---
title: 'Lync Server 2013: Visualizzazione SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="6bb8d-102">Visualizzazione SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bb8d-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bb8d-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6bb8d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6bb8d-104">La visualizzazione SessionDetails archivia le informazioni sulle sessioni peer-to-peer, che potrebbero essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="6bb8d-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bb8d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="6bb8d-106">Column</span></span></th>
<th><span data-ttu-id="6bb8d-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6bb8d-107">Data Type</span></span></th>
<th><span data-ttu-id="6bb8d-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6bb8d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="6bb8d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-111">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-111">Time of session request.</span></span> <span data-ttu-id="6bb8d-112">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="6bb8d-113">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-115">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-115">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-116">ID number to identify the session.</span></span> <span data-ttu-id="6bb8d-117">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="6bb8d-118">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-120">DateTime</span><span class="sxs-lookup"><span data-stu-id="6bb8d-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-121">Ora della prima richiesta di invito.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-121">Time of the first INVITE request.</span></span> <span data-ttu-id="6bb8d-122">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="6bb8d-123">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="6bb8d-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="6bb8d-124">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="6bb8d-125">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="6bb8d-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-128">URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-131">URI dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-134">Tipo di URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="6bb8d-135">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-138">Tipo di URI dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="6bb8d-139">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-142">Tenant dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="6bb8d-143">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-146">Il tenant dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="6bb8d-147">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6bb8d-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-150">Identificatore univoco del punto finale dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6bb8d-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-153">Identificatore univoco del punto finale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-155">DateTime</span><span class="sxs-lookup"><span data-stu-id="6bb8d-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-156">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-158">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-158">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-159">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-161">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-161">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-162">Numero di messaggi inviati dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-165">Versione del client usata dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-167">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-167">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-168">Client usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-168">Client used by the user who started the session.</span></span> <span data-ttu-id="6bb8d-169">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-172">Nome della categoria del client usata dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-175">Versione del client usata dall'utente che ha partecipato alla sessione</span><span class="sxs-lookup"><span data-stu-id="6bb8d-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-177">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-177">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-178">Client usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="6bb8d-179">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-182">Nome della categoria del client usata dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-185">URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-188">Tipo di URI dell'utente di destinazione per la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="6bb8d-189">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-192">URI dell'utente per conto della quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-195">Tipo di URI dell'utente per conto della quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="6bb8d-196">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-199">Tenant dell'utente per cui è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="6bb8d-200">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-203">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-206">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="6bb8d-207">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-210">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="6bb8d-211">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-214">ID finestra di dialogo SIP.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-214">SIP dialog ID.</span></span> <span data-ttu-id="6bb8d-215">Il formato è:</span><span class="sxs-lookup"><span data-stu-id="6bb8d-215">The format is:</span></span></p>
<p><span data-ttu-id="6bb8d-216">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="6bb8d-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6bb8d-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-219">GUID usato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-221">DateTime</span><span class="sxs-lookup"><span data-stu-id="6bb8d-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-222">Ora della finestra di dialogo che è stata sostituita dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="6bb8d-223">Usato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco una finestra di dialogo che viene sostituita dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="6bb8d-224">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-226">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-226">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-227">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-227">ID number to identify the session.</span></span> <span data-ttu-id="6bb8d-228">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una finestra di dialogo che viene sostituita dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="6bb8d-229">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6bb8d-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-232">ID finestra di dialogo SIP che sostituisce la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="6bb8d-233">Il formato è:</span><span class="sxs-lookup"><span data-stu-id="6bb8d-233">The format is:</span></span></p>
<p><span data-ttu-id="6bb8d-234">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="6bb8d-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-236">DateTime</span><span class="sxs-lookup"><span data-stu-id="6bb8d-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-237">Ora della risposta al primo messaggio di invito.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="6bb8d-238">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="6bb8d-239">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="6bb8d-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-241">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-241">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-242">Codice di risposta SIP per l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="6bb8d-243">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="6bb8d-244">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="6bb8d-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-246">int</span><span class="sxs-lookup"><span data-stu-id="6bb8d-246">int</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-247">ID di diagnostica acquisito dalle intestazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-250">Tipo di contenuto per la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-253">Nome di dominio completo del server front-end che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-256">Nome di dominio completo del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-259">FQDN dell'Edge Server usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-262">FQDN dell'Edge Server usato dall'utente che ha avviato la sessione</span><span class="sxs-lookup"><span data-stu-id="6bb8d-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-264">po'</span><span class="sxs-lookup"><span data-stu-id="6bb8d-264">bit</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-265">Indica se l'utente che ha avviato la sessione ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-267">po'</span><span class="sxs-lookup"><span data-stu-id="6bb8d-267">bit</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-268">Indica se l'utente che ha partecipato alla sessione ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-271">Priorità chiamata della sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-273">smallint</span><span class="sxs-lookup"><span data-stu-id="6bb8d-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-274">Indica gli attributi dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="6bb8d-275">Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bb8d-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="6bb8d-276">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="6bb8d-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-278">smallint</span><span class="sxs-lookup"><span data-stu-id="6bb8d-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-279">Indica gli attributi dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="6bb8d-280">Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bb8d-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="6bb8d-281">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="6bb8d-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bb8d-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-283">smallint</span><span class="sxs-lookup"><span data-stu-id="6bb8d-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-284">Indica gli attributi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-284">Indicates the call attributes.</span></span> <span data-ttu-id="6bb8d-285">Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bb8d-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="6bb8d-286">0x01-Riprova sessione</span><span class="sxs-lookup"><span data-stu-id="6bb8d-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="6bb8d-287">0x02-chiamata effettuata dall'agente per conto di un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="6bb8d-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bb8d-288"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="6bb8d-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="6bb8d-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="6bb8d-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="6bb8d-290">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="6bb8d-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

