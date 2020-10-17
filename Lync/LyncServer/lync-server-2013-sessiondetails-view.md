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
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510063"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="5d085-102">Visualizzazione SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d085-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d085-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5d085-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5d085-104">Nella visualizzazione SessionDetails vengono archiviate informazioni relative alle sessioni peer-to-peer, ovvero le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea tra due utenti e altri tipi di sessioni.</span><span class="sxs-lookup"><span data-stu-id="5d085-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="5d085-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d085-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d085-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="5d085-106">Column</span></span></th>
<th><span data-ttu-id="5d085-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5d085-107">Data Type</span></span></th>
<th><span data-ttu-id="5d085-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5d085-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d085-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-110">datetime</span><span class="sxs-lookup"><span data-stu-id="5d085-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d085-111">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-111">Time of session request.</span></span> <span data-ttu-id="5d085-112">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5d085-113">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-115">int</span><span class="sxs-lookup"><span data-stu-id="5d085-115">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-116">ID number to identify the session.</span></span> <span data-ttu-id="5d085-117">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5d085-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-120">datetime</span><span class="sxs-lookup"><span data-stu-id="5d085-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d085-p104">Ora della prima richiesta INVITE. Questo campo è solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5d085-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-128">URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-131">URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-134">Tipo di URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="5d085-135">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-138">Tipo di URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="5d085-139">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-142">Tenant dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="5d085-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-144"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-146">Tenant dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="5d085-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5d085-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5d085-150">Identificatore univoco dell'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5d085-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5d085-153">Identificatore univoco dell'endpoint dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-155">datetime</span><span class="sxs-lookup"><span data-stu-id="5d085-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d085-156">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-158">int</span><span class="sxs-lookup"><span data-stu-id="5d085-158">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-159">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-161">int</span><span class="sxs-lookup"><span data-stu-id="5d085-161">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-162">Numero di messaggi inviati dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-165">Versione del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-167">int</span><span class="sxs-lookup"><span data-stu-id="5d085-167">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-168">Client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-168">Client used by the user who started the session.</span></span> <span data-ttu-id="5d085-169">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5d085-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5d085-172">Nome della categoria del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-175">Versione del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-177">int</span><span class="sxs-lookup"><span data-stu-id="5d085-177">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-178">Client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="5d085-179">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5d085-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5d085-182">Nome della categoria del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-185">URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-188">Tipo di URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="5d085-189">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-192">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-195">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="5d085-196">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-199">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="5d085-200">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d085-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d085-203">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-206">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="5d085-207">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-210">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="5d085-211">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5d085-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5d085-p116">ID del dialogo SIP. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="5d085-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="5d085-216">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5d085-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5d085-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5d085-219">GUID utilizzato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="5d085-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-221">datetime</span><span class="sxs-lookup"><span data-stu-id="5d085-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d085-222">Ora del dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="5d085-223">Valore utilizzato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="5d085-224">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-226">int</span><span class="sxs-lookup"><span data-stu-id="5d085-226">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-227">Numero di ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-227">ID number to identify the session.</span></span> <span data-ttu-id="5d085-228">Valore utilizzato in combinazione con ReplaceDialogIdTime per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="5d085-229">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d085-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5d085-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5d085-p119">ID del dialogo SIP sostituito dalla sessione. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="5d085-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="5d085-234">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5d085-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-236">datetime</span><span class="sxs-lookup"><span data-stu-id="5d085-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d085-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5d085-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-241">int</span><span class="sxs-lookup"><span data-stu-id="5d085-241">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5d085-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-246">int</span><span class="sxs-lookup"><span data-stu-id="5d085-246">int</span></span></p></td>
<td><p><span data-ttu-id="5d085-247">ID di diagnostica acquisito dalle intestazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="5d085-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-250">Tipo del contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-253">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-256">FQDN del pool che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-259">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-262">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione</span><span class="sxs-lookup"><span data-stu-id="5d085-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-264">po'</span><span class="sxs-lookup"><span data-stu-id="5d085-264">bit</span></span></p></td>
<td><p><span data-ttu-id="5d085-265">Indica se l'utente che ha avviato la sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="5d085-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-267">po'</span><span class="sxs-lookup"><span data-stu-id="5d085-267">bit</span></span></p></td>
<td><p><span data-ttu-id="5d085-268">Indica se l'utente che si è unito alla sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="5d085-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d085-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d085-271">Priorità di chiamata della sessione.</span><span class="sxs-lookup"><span data-stu-id="5d085-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-273">smallint</span><span class="sxs-lookup"><span data-stu-id="5d085-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="5d085-p122">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d085-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="5d085-276">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="5d085-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-278">smallint</span><span class="sxs-lookup"><span data-stu-id="5d085-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="5d085-p123">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d085-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="5d085-281">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="5d085-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d085-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-283">smallint</span><span class="sxs-lookup"><span data-stu-id="5d085-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="5d085-p124">Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d085-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="5d085-286">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="5d085-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="5d085-287">0x02 - Chiamata eseguita da agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="5d085-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d085-288"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="5d085-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="5d085-289">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="5d085-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5d085-290">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="5d085-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

