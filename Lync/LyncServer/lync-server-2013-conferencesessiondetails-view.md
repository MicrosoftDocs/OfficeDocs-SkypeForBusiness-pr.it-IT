---
title: 'Lync Server 2013: visualizzazione ConferenceSessionDetails'
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
ms.openlocfilehash: be9d3566a951ee1b65d87e423627f556254173b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="3be61-102">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be61-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3be61-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="3be61-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="3be61-104">Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti.</span><span class="sxs-lookup"><span data-stu-id="3be61-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="3be61-105">Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="3be61-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="3be61-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3be61-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3be61-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="3be61-107">Column</span></span></th>
<th><span data-ttu-id="3be61-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3be61-108">Data Type</span></span></th>
<th><span data-ttu-id="3be61-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3be61-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3be61-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3be61-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be61-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-112">Time of session request.</span></span> <span data-ttu-id="3be61-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="3be61-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-116">int</span><span class="sxs-lookup"><span data-stu-id="3be61-116">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-117">ID number to identify the session.</span></span> <span data-ttu-id="3be61-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="3be61-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-121">datetime</span><span class="sxs-lookup"><span data-stu-id="3be61-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be61-p104">Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="3be61-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be61-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be61-127">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="3be61-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-130">Tipo di URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="3be61-130">Type of conference URI.</span></span> <span data-ttu-id="3be61-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3be61-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3be61-p106">Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="3be61-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be61-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be61-138">URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="3be61-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-141">Tipo di URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="3be61-141">Type of conferencing server URI.</span></span> <span data-ttu-id="3be61-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be61-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be61-145">URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-148">Tipo di URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="3be61-149">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-152">Tenant dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="3be61-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3be61-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3be61-156">Identificatore univoco dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-158">datetime</span><span class="sxs-lookup"><span data-stu-id="3be61-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be61-159">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-162">Versione del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="3be61-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-164">int</span><span class="sxs-lookup"><span data-stu-id="3be61-164">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-165">Tipo del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="3be61-165">Type of conference server.</span></span> <span data-ttu-id="3be61-166">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3be61-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3be61-169">Categoria del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="3be61-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-172">Versione del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-174">int</span><span class="sxs-lookup"><span data-stu-id="3be61-174">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-175">Client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="3be61-176">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3be61-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3be61-179">Nome della categoria del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be61-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be61-182">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-185">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="3be61-186">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-189">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="3be61-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3be61-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3be61-193">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-196">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="3be61-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-200">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="3be61-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="3be61-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="3be61-p116">ID del dialogo SIP. Il formato è</span><span class="sxs-lookup"><span data-stu-id="3be61-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="3be61-206">:d ialog; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="3be61-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-208">datetime</span><span class="sxs-lookup"><span data-stu-id="3be61-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be61-209">Numero ID per identificare il dialogo sostituito dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="3be61-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="3be61-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-212">int</span><span class="sxs-lookup"><span data-stu-id="3be61-212">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-213">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-213">ID number to identify the session.</span></span> <span data-ttu-id="3be61-214">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="3be61-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="3be61-215">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3be61-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="3be61-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="3be61-p119">ID del dialogo SIP che la sessione sostituisce. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="3be61-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="3be61-220">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="3be61-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-222">po'</span><span class="sxs-lookup"><span data-stu-id="3be61-222">bit</span></span></p></td>
<td><p><span data-ttu-id="3be61-223">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="3be61-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-225">po'</span><span class="sxs-lookup"><span data-stu-id="3be61-225">bit</span></span></p></td>
<td><p><span data-ttu-id="3be61-226">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="3be61-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-228">po'</span><span class="sxs-lookup"><span data-stu-id="3be61-228">bit</span></span></p></td>
<td><p><span data-ttu-id="3be61-229">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="3be61-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-231">datetime</span><span class="sxs-lookup"><span data-stu-id="3be61-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="3be61-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="3be61-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-236">int</span><span class="sxs-lookup"><span data-stu-id="3be61-236">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="3be61-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-241">int</span><span class="sxs-lookup"><span data-stu-id="3be61-241">int</span></span></p></td>
<td><p><span data-ttu-id="3be61-242">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-245">Tipo di contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-248">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-251">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-254">Mediation Server dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-257">Gateway dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3be61-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3be61-260">FQDN del server perimetrale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="3be61-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be61-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-262">smallint</span><span class="sxs-lookup"><span data-stu-id="3be61-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="3be61-p122">Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="3be61-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="3be61-265">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="3be61-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be61-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3be61-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3be61-267">smallint</span><span class="sxs-lookup"><span data-stu-id="3be61-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="3be61-p123">Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="3be61-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="3be61-270">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="3be61-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="3be61-271">x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="3be61-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

