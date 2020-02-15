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
ms.openlocfilehash: fb7b664761aa8506b01e114366016b98637eb30e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="52228-102">Visualizzazione SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52228-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52228-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="52228-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="52228-104">Nella visualizzazione SessionDetails vengono archiviate informazioni relative alle sessioni peer-to-peer, ovvero le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea tra due utenti e altri tipi di sessioni.</span><span class="sxs-lookup"><span data-stu-id="52228-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="52228-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52228-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52228-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="52228-106">Column</span></span></th>
<th><span data-ttu-id="52228-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="52228-107">Data Type</span></span></th>
<th><span data-ttu-id="52228-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="52228-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52228-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="52228-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-110">datetime</span><span class="sxs-lookup"><span data-stu-id="52228-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="52228-111">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-111">Time of session request.</span></span> <span data-ttu-id="52228-112">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="52228-113">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52228-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-115">int</span><span class="sxs-lookup"><span data-stu-id="52228-115">int</span></span></p></td>
<td><p><span data-ttu-id="52228-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-116">ID number to identify the session.</span></span> <span data-ttu-id="52228-117">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="52228-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="52228-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-120">datetime</span><span class="sxs-lookup"><span data-stu-id="52228-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="52228-p104">Ora della prima richiesta INVITE. Questo campo è solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="52228-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="52228-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-128">URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="52228-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-131">URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-134">Tipo di URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="52228-135">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-138">Tipo di URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="52228-139">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="52228-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-142">Tenant dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="52228-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="52228-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-146">Tenant dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="52228-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="52228-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="52228-150">Identificatore univoco dell'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="52228-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="52228-153">Identificatore univoco dell'endpoint dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="52228-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-155">datetime</span><span class="sxs-lookup"><span data-stu-id="52228-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="52228-156">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="52228-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-158">int</span><span class="sxs-lookup"><span data-stu-id="52228-158">int</span></span></p></td>
<td><p><span data-ttu-id="52228-159">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="52228-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-161">int</span><span class="sxs-lookup"><span data-stu-id="52228-161">int</span></span></p></td>
<td><p><span data-ttu-id="52228-162">Numero di messaggi inviati dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="52228-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-165">Versione del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-167">int</span><span class="sxs-lookup"><span data-stu-id="52228-167">int</span></span></p></td>
<td><p><span data-ttu-id="52228-168">Client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-168">Client used by the user who started the session.</span></span> <span data-ttu-id="52228-169">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="52228-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="52228-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="52228-172">Nome della categoria del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="52228-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-175">Versione del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-177">int</span><span class="sxs-lookup"><span data-stu-id="52228-177">int</span></span></p></td>
<td><p><span data-ttu-id="52228-178">Client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="52228-179">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="52228-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="52228-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="52228-182">Nome della categoria del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="52228-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-185">URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-188">Tipo di URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="52228-189">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="52228-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-192">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-195">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="52228-196">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="52228-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-199">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="52228-200">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="52228-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52228-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52228-203">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-206">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="52228-207">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="52228-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-210">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="52228-211">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="52228-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="52228-p116">ID del dialogo SIP. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="52228-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="52228-216">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="52228-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="52228-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="52228-219">GUID utilizzato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="52228-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="52228-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-221">datetime</span><span class="sxs-lookup"><span data-stu-id="52228-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="52228-222">Ora del dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="52228-223">Valore utilizzato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="52228-224">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52228-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-226">int</span><span class="sxs-lookup"><span data-stu-id="52228-226">int</span></span></p></td>
<td><p><span data-ttu-id="52228-227">Numero di ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-227">ID number to identify the session.</span></span> <span data-ttu-id="52228-228">Valore utilizzato in combinazione con ReplaceDialogIdTime per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="52228-229">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52228-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="52228-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="52228-p119">ID del dialogo SIP sostituito dalla sessione. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="52228-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="52228-234">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="52228-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="52228-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-236">datetime</span><span class="sxs-lookup"><span data-stu-id="52228-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="52228-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="52228-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="52228-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-241">int</span><span class="sxs-lookup"><span data-stu-id="52228-241">int</span></span></p></td>
<td><p><span data-ttu-id="52228-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="52228-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="52228-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-246">int</span><span class="sxs-lookup"><span data-stu-id="52228-246">int</span></span></p></td>
<td><p><span data-ttu-id="52228-247">ID di diagnostica acquisito dalle intestazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="52228-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="52228-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-250">Tipo del contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="52228-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-253">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="52228-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-256">FQDN del pool che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="52228-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-259">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="52228-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-262">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione</span><span class="sxs-lookup"><span data-stu-id="52228-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="52228-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-264">po'</span><span class="sxs-lookup"><span data-stu-id="52228-264">bit</span></span></p></td>
<td><p><span data-ttu-id="52228-265">Indica se l'utente che ha avviato la sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="52228-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="52228-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-267">po'</span><span class="sxs-lookup"><span data-stu-id="52228-267">bit</span></span></p></td>
<td><p><span data-ttu-id="52228-268">Indica se l'utente che si è unito alla sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="52228-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="52228-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52228-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52228-271">Priorità di chiamata della sessione.</span><span class="sxs-lookup"><span data-stu-id="52228-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="52228-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-273">smallint</span><span class="sxs-lookup"><span data-stu-id="52228-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="52228-p122">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="52228-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="52228-276">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="52228-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="52228-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-278">smallint</span><span class="sxs-lookup"><span data-stu-id="52228-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="52228-p123">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="52228-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="52228-281">0x01 - Integrato con telefono da tavolo</span><span class="sxs-lookup"><span data-stu-id="52228-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52228-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="52228-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-283">smallint</span><span class="sxs-lookup"><span data-stu-id="52228-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="52228-p124">Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="52228-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="52228-286">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="52228-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="52228-287">0x02 - Chiamata eseguita da agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="52228-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52228-288"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="52228-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="52228-289">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="52228-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="52228-290">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="52228-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

