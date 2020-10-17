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
ms.openlocfilehash: cf8023408990b7f0243aaf0e937e2d1095dff0c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529183"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="499ce-102">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="499ce-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="499ce-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="499ce-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="499ce-104">Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti.</span><span class="sxs-lookup"><span data-stu-id="499ce-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="499ce-105">Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="499ce-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="499ce-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="499ce-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="499ce-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="499ce-107">Column</span></span></th>
<th><span data-ttu-id="499ce-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="499ce-108">Data Type</span></span></th>
<th><span data-ttu-id="499ce-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="499ce-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="499ce-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-111">datetime</span><span class="sxs-lookup"><span data-stu-id="499ce-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="499ce-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-112">Time of session request.</span></span> <span data-ttu-id="499ce-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="499ce-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-116">int</span><span class="sxs-lookup"><span data-stu-id="499ce-116">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-117">ID number to identify the session.</span></span> <span data-ttu-id="499ce-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="499ce-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-121">datetime</span><span class="sxs-lookup"><span data-stu-id="499ce-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="499ce-p104">Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="499ce-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="499ce-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="499ce-127">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="499ce-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-130">Tipo di URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="499ce-130">Type of conference URI.</span></span> <span data-ttu-id="499ce-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="499ce-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="499ce-p106">Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="499ce-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="499ce-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="499ce-138">URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="499ce-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-141">Tipo di URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="499ce-141">Type of conferencing server URI.</span></span> <span data-ttu-id="499ce-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="499ce-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="499ce-145">URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-148">Tipo di URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="499ce-149">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-152">Tenant dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="499ce-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="499ce-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="499ce-156">Identificatore univoco dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-158">datetime</span><span class="sxs-lookup"><span data-stu-id="499ce-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="499ce-159">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-162">Versione del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="499ce-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-164">int</span><span class="sxs-lookup"><span data-stu-id="499ce-164">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-165">Tipo del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="499ce-165">Type of conference server.</span></span> <span data-ttu-id="499ce-166">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="499ce-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="499ce-169">Categoria del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="499ce-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-172">Versione del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-174">int</span><span class="sxs-lookup"><span data-stu-id="499ce-174">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-175">Client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="499ce-176">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="499ce-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="499ce-179">Nome della categoria del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="499ce-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="499ce-182">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-185">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="499ce-186">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-189">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="499ce-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="499ce-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="499ce-193">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-196">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="499ce-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-200">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="499ce-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="499ce-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="499ce-p116">ID del dialogo SIP. Il formato è</span><span class="sxs-lookup"><span data-stu-id="499ce-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="499ce-206">:d ialog; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="499ce-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-208">datetime</span><span class="sxs-lookup"><span data-stu-id="499ce-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="499ce-209">Numero ID per identificare il dialogo sostituito dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="499ce-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="499ce-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-212">int</span><span class="sxs-lookup"><span data-stu-id="499ce-212">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-213">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-213">ID number to identify the session.</span></span> <span data-ttu-id="499ce-214">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="499ce-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="499ce-215">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="499ce-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="499ce-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="499ce-p119">ID del dialogo SIP che la sessione sostituisce. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="499ce-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="499ce-220">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="499ce-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-222">po'</span><span class="sxs-lookup"><span data-stu-id="499ce-222">bit</span></span></p></td>
<td><p><span data-ttu-id="499ce-223">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="499ce-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-225">po'</span><span class="sxs-lookup"><span data-stu-id="499ce-225">bit</span></span></p></td>
<td><p><span data-ttu-id="499ce-226">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="499ce-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-228">po'</span><span class="sxs-lookup"><span data-stu-id="499ce-228">bit</span></span></p></td>
<td><p><span data-ttu-id="499ce-229">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="499ce-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-231">datetime</span><span class="sxs-lookup"><span data-stu-id="499ce-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="499ce-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="499ce-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-236">int</span><span class="sxs-lookup"><span data-stu-id="499ce-236">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="499ce-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-241">int</span><span class="sxs-lookup"><span data-stu-id="499ce-241">int</span></span></p></td>
<td><p><span data-ttu-id="499ce-242">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-245">Tipo di contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-248">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-251">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-254">Mediation Server dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-257">Gateway dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="499ce-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="499ce-260">FQDN del server perimetrale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="499ce-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="499ce-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-262">smallint</span><span class="sxs-lookup"><span data-stu-id="499ce-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="499ce-p122">Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="499ce-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="499ce-265">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="499ce-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="499ce-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="499ce-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="499ce-267">smallint</span><span class="sxs-lookup"><span data-stu-id="499ce-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="499ce-p123">Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="499ce-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="499ce-270">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="499ce-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="499ce-271">x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="499ce-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

