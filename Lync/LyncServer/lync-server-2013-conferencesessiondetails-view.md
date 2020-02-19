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
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="5da51-102">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5da51-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5da51-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5da51-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5da51-104">Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti.</span><span class="sxs-lookup"><span data-stu-id="5da51-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="5da51-105">Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="5da51-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="5da51-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5da51-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5da51-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="5da51-107">Column</span></span></th>
<th><span data-ttu-id="5da51-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5da51-108">Data Type</span></span></th>
<th><span data-ttu-id="5da51-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5da51-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5da51-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5da51-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5da51-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-112">Time of session request.</span></span> <span data-ttu-id="5da51-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5da51-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-116">int</span><span class="sxs-lookup"><span data-stu-id="5da51-116">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-117">ID number to identify the session.</span></span> <span data-ttu-id="5da51-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5da51-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5da51-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="5da51-p104">Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5da51-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5da51-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5da51-127">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="5da51-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-130">Tipo di URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="5da51-130">Type of conference URI.</span></span> <span data-ttu-id="5da51-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5da51-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5da51-p106">Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="5da51-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5da51-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5da51-138">URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5da51-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-141">Tipo di URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5da51-141">Type of conferencing server URI.</span></span> <span data-ttu-id="5da51-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5da51-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5da51-145">URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-148">Tipo di URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="5da51-149">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-152">Tenant dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="5da51-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5da51-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5da51-156">Identificatore univoco dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-158">datetime</span><span class="sxs-lookup"><span data-stu-id="5da51-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="5da51-159">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-162">Versione del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="5da51-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-164">int</span><span class="sxs-lookup"><span data-stu-id="5da51-164">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-165">Tipo del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="5da51-165">Type of conference server.</span></span> <span data-ttu-id="5da51-166">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5da51-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5da51-169">Categoria del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="5da51-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-172">Versione del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-174">int</span><span class="sxs-lookup"><span data-stu-id="5da51-174">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-175">Client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="5da51-176">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5da51-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5da51-179">Nome della categoria del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5da51-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5da51-182">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-185">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="5da51-186">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-189">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="5da51-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5da51-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5da51-193">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-196">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="5da51-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-200">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="5da51-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="5da51-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5da51-p116">ID del dialogo SIP. Il formato è</span><span class="sxs-lookup"><span data-stu-id="5da51-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="5da51-206">:d ialog; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5da51-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-208">datetime</span><span class="sxs-lookup"><span data-stu-id="5da51-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="5da51-209">Numero ID per identificare il dialogo sostituito dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5da51-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5da51-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-212">int</span><span class="sxs-lookup"><span data-stu-id="5da51-212">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-213">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-213">ID number to identify the session.</span></span> <span data-ttu-id="5da51-214">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5da51-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5da51-215">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5da51-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5da51-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5da51-p119">ID del dialogo SIP che la sessione sostituisce. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="5da51-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="5da51-220">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5da51-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-222">po'</span><span class="sxs-lookup"><span data-stu-id="5da51-222">bit</span></span></p></td>
<td><p><span data-ttu-id="5da51-223">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5da51-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-225">po'</span><span class="sxs-lookup"><span data-stu-id="5da51-225">bit</span></span></p></td>
<td><p><span data-ttu-id="5da51-226">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5da51-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-228">po'</span><span class="sxs-lookup"><span data-stu-id="5da51-228">bit</span></span></p></td>
<td><p><span data-ttu-id="5da51-229">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="5da51-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-231">datetime</span><span class="sxs-lookup"><span data-stu-id="5da51-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="5da51-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5da51-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-236">int</span><span class="sxs-lookup"><span data-stu-id="5da51-236">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5da51-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-241">int</span><span class="sxs-lookup"><span data-stu-id="5da51-241">int</span></span></p></td>
<td><p><span data-ttu-id="5da51-242">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-245">Tipo di contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-248">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-251">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-254">Mediation Server dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-257">Gateway dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5da51-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5da51-260">FQDN del server perimetrale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5da51-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5da51-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-262">smallint</span><span class="sxs-lookup"><span data-stu-id="5da51-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="5da51-p122">Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5da51-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="5da51-265">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="5da51-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5da51-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5da51-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5da51-267">smallint</span><span class="sxs-lookup"><span data-stu-id="5da51-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="5da51-p123">Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5da51-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="5da51-270">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="5da51-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="5da51-271">x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="5da51-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

