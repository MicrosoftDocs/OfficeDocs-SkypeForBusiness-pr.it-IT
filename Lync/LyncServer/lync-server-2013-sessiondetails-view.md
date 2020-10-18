---
title: 'Lync Server 2013: Visualizzazione SessionDetails'
description: 'Lync Server 2013: Visualizzazione SessionDetails.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573242"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="d9f59-103">Visualizzazione SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9f59-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9f59-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d9f59-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d9f59-105">Nella visualizzazione SessionDetails vengono archiviate informazioni relative alle sessioni peer-to-peer, ovvero le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea tra due utenti e altri tipi di sessioni.</span><span class="sxs-lookup"><span data-stu-id="d9f59-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="d9f59-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9f59-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9f59-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="d9f59-107">Column</span></span></th>
<th><span data-ttu-id="d9f59-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d9f59-108">Data Type</span></span></th>
<th><span data-ttu-id="d9f59-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d9f59-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d9f59-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9f59-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-112">Time of session request.</span></span> <span data-ttu-id="d9f59-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="d9f59-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-116">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-116">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-117">ID number to identify the session.</span></span> <span data-ttu-id="d9f59-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="d9f59-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d9f59-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p104">Ora della prima richiesta INVITE. Questo campo è solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d9f59-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-129">URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-132">URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-135">Tipo di URI dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="d9f59-136">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-139">Tipo di URI dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="d9f59-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-143">Tenant dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="d9f59-144">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-145"><strong>Totenant</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-147">Tenant dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="d9f59-148">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-150">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d9f59-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d9f59-151">Identificatore univoco dell'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-153">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d9f59-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d9f59-154">Identificatore univoco dell'endpoint dell'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-156">datetime</span><span class="sxs-lookup"><span data-stu-id="d9f59-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9f59-157">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-159">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-159">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-160">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-162">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-162">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-163">Numero di messaggi inviati dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-166">Versione del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-168">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-168">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-169">Client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-169">Client used by the user who started the session.</span></span> <span data-ttu-id="d9f59-170">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d9f59-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-173">Nome della categoria del client utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-176">Versione del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-178">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-178">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-179">Client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="d9f59-180">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d9f59-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-183">Nome della categoria del client utilizzato dall'utente che si è unito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-186">URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-189">Tipo di URI dell'utente di destinazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="d9f59-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-193">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-196">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="d9f59-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-200">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="d9f59-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d9f59-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-204">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-207">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="d9f59-208">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-211">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="d9f59-212">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="d9f59-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p116">ID del dialogo SIP. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="d9f59-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="d9f59-217">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="d9f59-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-219">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d9f59-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d9f59-220">GUID utilizzato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="d9f59-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-222">datetime</span><span class="sxs-lookup"><span data-stu-id="d9f59-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9f59-223">Ora del dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="d9f59-224">Valore utilizzato in combinazione con ReplaceDialogIdSeq per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d9f59-225">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-227">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-227">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-228">Numero di ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-228">ID number to identify the session.</span></span> <span data-ttu-id="d9f59-229">Valore utilizzato in combinazione con ReplaceDialogIdTime per identificare in modo univoco un dialogo sostituito dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d9f59-230">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d9f59-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="d9f59-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p119">ID del dialogo SIP sostituito dalla sessione. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="d9f59-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="d9f59-235">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="d9f59-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-237">datetime</span><span class="sxs-lookup"><span data-stu-id="d9f59-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d9f59-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-242">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-242">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d9f59-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-247">int</span><span class="sxs-lookup"><span data-stu-id="d9f59-247">int</span></span></p></td>
<td><p><span data-ttu-id="d9f59-248">ID di diagnostica acquisito dalle intestazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="d9f59-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-251">Tipo del contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-254">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-257">FQDN del pool che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-260">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-263">FQDN del server perimetrale utilizzato dall'utente che ha avviato la sessione</span><span class="sxs-lookup"><span data-stu-id="d9f59-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-265">po'</span><span class="sxs-lookup"><span data-stu-id="d9f59-265">bit</span></span></p></td>
<td><p><span data-ttu-id="d9f59-266">Indica se l'utente che ha avviato la sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="d9f59-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-268">po'</span><span class="sxs-lookup"><span data-stu-id="d9f59-268">bit</span></span></p></td>
<td><p><span data-ttu-id="d9f59-269">Indica se l'utente che si è unito alla sessione ha eseguito l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="d9f59-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9f59-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-272">Priorità di chiamata della sessione.</span><span class="sxs-lookup"><span data-stu-id="d9f59-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-274">smallint</span><span class="sxs-lookup"><span data-stu-id="d9f59-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p122">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9f59-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d9f59-277">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="d9f59-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-279">smallint</span><span class="sxs-lookup"><span data-stu-id="d9f59-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p123">Indica gli attributi dell'utente che ha avviato la sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9f59-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d9f59-282">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="d9f59-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f59-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-284">smallint</span><span class="sxs-lookup"><span data-stu-id="d9f59-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="d9f59-p124">Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9f59-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d9f59-287">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="d9f59-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="d9f59-288">0x02 - Chiamata eseguita da agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="d9f59-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f59-289"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="d9f59-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="d9f59-290">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="d9f59-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d9f59-291">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d9f59-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

