---
title: 'Lync Server 2013: visualizzazione ConferenceSessionDetails'
description: 'Lync Server 2013: visualizzazione ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566772"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="ce6f6-103">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce6f6-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce6f6-104">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ce6f6-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ce6f6-105">Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="ce6f6-106">Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="ce6f6-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce6f6-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="ce6f6-108">Column</span></span></th>
<th><span data-ttu-id="ce6f6-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ce6f6-109">Data Type</span></span></th>
<th><span data-ttu-id="ce6f6-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ce6f6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ce6f6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-113">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-113">Time of session request.</span></span> <span data-ttu-id="ce6f6-114">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ce6f6-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-117">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-117">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-118">ID number to identify the session.</span></span> <span data-ttu-id="ce6f6-119">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ce6f6-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ce6f6-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p104">Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-128">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-131">Tipo di URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-131">Type of conference URI.</span></span> <span data-ttu-id="ce6f6-132">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ce6f6-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p106">Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-139">URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-142">Tipo di URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-142">Type of conferencing server URI.</span></span> <span data-ttu-id="ce6f6-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-146">URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-149">Tipo di URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="ce6f6-150">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-153">Tenant dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="ce6f6-154">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-156">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ce6f6-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-157">Identificatore univoco dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-159">datetime</span><span class="sxs-lookup"><span data-stu-id="ce6f6-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-160">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-163">Versione del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-165">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-165">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-166">Tipo del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-166">Type of conference server.</span></span> <span data-ttu-id="ce6f6-167">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-170">Categoria del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-173">Versione del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-175">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-175">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-176">Client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="ce6f6-177">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-180">Nome della categoria del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-183">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-186">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="ce6f6-187">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-190">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="ce6f6-191">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-194">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-197">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="ce6f6-198">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-201">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="ce6f6-202">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p116">ID del dialogo SIP. Il formato è</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="ce6f6-207">:d ialog; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="ce6f6-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-209">datetime</span><span class="sxs-lookup"><span data-stu-id="ce6f6-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-210">Numero ID per identificare il dialogo sostituito dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ce6f6-211">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-213">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-213">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-214">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-214">ID number to identify the session.</span></span> <span data-ttu-id="ce6f6-215">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ce6f6-216">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce6f6-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p119">ID del dialogo SIP che la sessione sostituisce. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="ce6f6-221">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="ce6f6-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-223">po'</span><span class="sxs-lookup"><span data-stu-id="ce6f6-223">bit</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-224">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-226">po'</span><span class="sxs-lookup"><span data-stu-id="ce6f6-226">bit</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-227">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-229">po'</span><span class="sxs-lookup"><span data-stu-id="ce6f6-229">bit</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-230">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-232">datetime</span><span class="sxs-lookup"><span data-stu-id="ce6f6-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-237">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-237">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-242">int</span><span class="sxs-lookup"><span data-stu-id="ce6f6-242">int</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-243">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-246">Tipo di contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-249">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-252">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-255">Mediation Server dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-256"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-258">Gateway dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce6f6-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-261">FQDN del server perimetrale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ce6f6-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce6f6-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-263">smallint</span><span class="sxs-lookup"><span data-stu-id="ce6f6-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p122">Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="ce6f6-266">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="ce6f6-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce6f6-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ce6f6-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ce6f6-268">smallint</span><span class="sxs-lookup"><span data-stu-id="ce6f6-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="ce6f6-p123">Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce6f6-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ce6f6-271">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="ce6f6-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="ce6f6-272">x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="ce6f6-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

