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
ms.openlocfilehash: 7bc6d1888753edbeb076d60d6725b6d9cffc509e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b5f22-102">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5f22-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5f22-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b5f22-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b5f22-104">Nella visualizzazione ConferenceSessionDetails sono archiviate informazioni sulle sessioni tra più utenti.</span><span class="sxs-lookup"><span data-stu-id="b5f22-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="b5f22-105">Ogni record rappresenta una sola sessione di conferenza, che può essere la sessione con Focus o con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="b5f22-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="b5f22-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5f22-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5f22-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="b5f22-107">Column</span></span></th>
<th><span data-ttu-id="b5f22-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b5f22-108">Data Type</span></span></th>
<th><span data-ttu-id="b5f22-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b5f22-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b5f22-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5f22-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-112">Time of session request.</span></span> <span data-ttu-id="b5f22-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b5f22-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-116">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-116">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-117">ID number to identify the session.</span></span> <span data-ttu-id="b5f22-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b5f22-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b5f22-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p104">Ora della prima richiesta INVITE. Questo campo in genere viene popolato dai dati generati dal messaggio INVITE iniziale della sessione. Se non ci sono messaggi INVITE, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="b5f22-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f22-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-127">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="b5f22-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-130">Tipo di URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="b5f22-130">Type of conference URI.</span></span> <span data-ttu-id="b5f22-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b5f22-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p106">Identificatore che consente di distinguere le istanze delle conferenze ricorrenti. Ogni istanza ha lo stesso ConferenceURI ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="b5f22-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f22-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-138">URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="b5f22-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-141">Tipo di URI del server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="b5f22-141">Type of conferencing server URI.</span></span> <span data-ttu-id="b5f22-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f22-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-145">URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-148">Tipo di URI dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="b5f22-149">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-152">Tenant dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="b5f22-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b5f22-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5f22-156">Identificatore univoco dell'utente che partecipa alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-158">datetime</span><span class="sxs-lookup"><span data-stu-id="b5f22-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5f22-159">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-162">Versione del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="b5f22-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-164">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-164">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-165">Tipo del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="b5f22-165">Type of conference server.</span></span> <span data-ttu-id="b5f22-166">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5f22-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-169">Categoria del Conference Server.</span><span class="sxs-lookup"><span data-stu-id="b5f22-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-172">Versione del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-174">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-174">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-175">Client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="b5f22-176">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5f22-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-179">Nome della categoria del client dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f22-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-182">URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-185">Tipo di URI dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b5f22-186">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-189">Tenant dell'utente per conto del quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b5f22-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f22-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-193">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-196">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b5f22-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-200">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b5f22-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="b5f22-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p116">ID del dialogo SIP. Il formato è</span><span class="sxs-lookup"><span data-stu-id="b5f22-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="b5f22-206">:d ialog; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="b5f22-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-208">datetime</span><span class="sxs-lookup"><span data-stu-id="b5f22-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5f22-209">Numero ID per identificare il dialogo sostituito dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="b5f22-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="b5f22-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-212">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-212">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-213">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-213">ID number to identify the session.</span></span> <span data-ttu-id="b5f22-214">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="b5f22-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="b5f22-215">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5f22-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b5f22-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p119">ID del dialogo SIP che la sessione sostituisce. Il formato è:</span><span class="sxs-lookup"><span data-stu-id="b5f22-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="b5f22-220">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="b5f22-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-222">po'</span><span class="sxs-lookup"><span data-stu-id="b5f22-222">bit</span></span></p></td>
<td><p><span data-ttu-id="b5f22-223">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="b5f22-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-225">po'</span><span class="sxs-lookup"><span data-stu-id="b5f22-225">bit</span></span></p></td>
<td><p><span data-ttu-id="b5f22-226">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="b5f22-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-228">po'</span><span class="sxs-lookup"><span data-stu-id="b5f22-228">bit</span></span></p></td>
<td><p><span data-ttu-id="b5f22-229">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="b5f22-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-231">datetime</span><span class="sxs-lookup"><span data-stu-id="b5f22-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p120">Ora della risposta al primo messaggio INVITE. Questo campo viene solitamente compilato con dati generati dal messaggio INVITE iniziale della sessione. In mancanza del messaggio INVITE, il campo viene compilato con la data e l'ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="b5f22-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-236">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-236">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="b5f22-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-241">int</span><span class="sxs-lookup"><span data-stu-id="b5f22-241">int</span></span></p></td>
<td><p><span data-ttu-id="b5f22-242">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-245">Tipo di contenuto della sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-248">FQDN del Front End Server che ha acquisito i dati della sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-251">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-254">Mediation Server dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-257">Gateway dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5f22-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5f22-260">FQDN del server perimetrale dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="b5f22-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5f22-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-262">smallint</span><span class="sxs-lookup"><span data-stu-id="b5f22-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p122">Indica gli attributi dell'utente che ha partecipato alla sessione. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5f22-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="b5f22-265">0x01 - Integrato con il telefono da scrivania</span><span class="sxs-lookup"><span data-stu-id="b5f22-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5f22-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5f22-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5f22-267">smallint</span><span class="sxs-lookup"><span data-stu-id="b5f22-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5f22-p123">Indica gli attributi della chiamata. Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5f22-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b5f22-270">0x01 - Sessione ripetuta</span><span class="sxs-lookup"><span data-stu-id="b5f22-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="b5f22-271">x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="b5f22-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

