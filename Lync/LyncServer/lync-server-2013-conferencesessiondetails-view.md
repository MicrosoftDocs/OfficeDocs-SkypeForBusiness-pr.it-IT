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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="26df9-102">Visualizzazione ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26df9-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26df9-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="26df9-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="26df9-104">La visualizzazione ConferenceSessionDetails archivia le informazioni sulle sessioni multiparte.</span><span class="sxs-lookup"><span data-stu-id="26df9-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="26df9-105">Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="26df9-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26df9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26df9-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="26df9-107">Column</span></span></th>
<th><span data-ttu-id="26df9-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="26df9-108">Data Type</span></span></th>
<th><span data-ttu-id="26df9-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="26df9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26df9-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="26df9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="26df9-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-112">Time of session request.</span></span> <span data-ttu-id="26df9-113">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="26df9-114">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-116">int</span><span class="sxs-lookup"><span data-stu-id="26df9-116">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-117">ID number to identify the session.</span></span> <span data-ttu-id="26df9-118">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="26df9-119">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-121">DateTime</span><span class="sxs-lookup"><span data-stu-id="26df9-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="26df9-122">Ora della prima richiesta di invito.</span><span class="sxs-lookup"><span data-stu-id="26df9-122">Time of the first INVITE request.</span></span> <span data-ttu-id="26df9-123">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="26df9-124">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="26df9-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26df9-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26df9-127">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-130">URI del tipo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-130">Type of conference URI.</span></span> <span data-ttu-id="26df9-131">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="26df9-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="26df9-134">Identificatore che distingue tra le istanze delle conferenze periodiche.</span><span class="sxs-lookup"><span data-stu-id="26df9-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="26df9-135">Ogni istanza di conferenza ricorrente ha lo stesso ConferenceURI, ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="26df9-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26df9-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26df9-138">URI del server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-141">Tipo di URI di conferenza server.</span><span class="sxs-lookup"><span data-stu-id="26df9-141">Type of conferencing server URI.</span></span> <span data-ttu-id="26df9-142">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26df9-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26df9-145">URI dell'utente coinvolto nella sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-148">Tipo di URI dell'utente di cui è stata parte della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="26df9-149">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-152">Tenant dell'utente di cui è stata parte della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="26df9-153">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="26df9-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="26df9-156">Identificatore univoco dell'utente di cui faceva parte della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="26df9-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="26df9-159">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-162">Versione di Conference Server.</span><span class="sxs-lookup"><span data-stu-id="26df9-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-164">int</span><span class="sxs-lookup"><span data-stu-id="26df9-164">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-165">Tipo di server conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-165">Type of conference server.</span></span> <span data-ttu-id="26df9-166">Per altre informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="26df9-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="26df9-169">Categoria Server conferenze.</span><span class="sxs-lookup"><span data-stu-id="26df9-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-172">Versione del client usata dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-174">int</span><span class="sxs-lookup"><span data-stu-id="26df9-174">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-175">Client usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="26df9-176">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="26df9-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="26df9-179">Nome della categoria del client usata dall'utente che faceva parte della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26df9-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26df9-182">URI dell'utente per conto della quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-185">Tipo di URI dell'utente per conto della quale è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="26df9-186">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-189">Tenant dell'utente per cui è stata avviata la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="26df9-190">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26df9-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26df9-193">URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-196">Tipo di URI dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="26df9-197">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-200">Tenant dell'utente che ha fatto riferimento alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="26df9-201">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="26df9-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="26df9-204">ID finestra di dialogo SIP.</span><span class="sxs-lookup"><span data-stu-id="26df9-204">SIP dialog ID.</span></span> <span data-ttu-id="26df9-205">Il formato è</span><span class="sxs-lookup"><span data-stu-id="26df9-205">The format is</span></span></p>
<p><span data-ttu-id="26df9-206">:d ialog; from-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="26df9-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-208">DateTime</span><span class="sxs-lookup"><span data-stu-id="26df9-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="26df9-209">Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="26df9-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="26df9-210">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-212">int</span><span class="sxs-lookup"><span data-stu-id="26df9-212">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-213">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-213">ID number to identify the session.</span></span> <span data-ttu-id="26df9-214">Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="26df9-215">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26df9-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="26df9-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="26df9-218">ID finestra di dialogo SIP che sostituisce la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="26df9-219">Il formato dell'is:</span><span class="sxs-lookup"><span data-stu-id="26df9-219">The format of the is:</span></span></p>
<p><span data-ttu-id="26df9-220">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="26df9-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-222">po'</span><span class="sxs-lookup"><span data-stu-id="26df9-222">bit</span></span></p></td>
<td><p><span data-ttu-id="26df9-223">Indica se la sessione è stata avviata dal server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-225">po'</span><span class="sxs-lookup"><span data-stu-id="26df9-225">bit</span></span></p></td>
<td><p><span data-ttu-id="26df9-226">Indica se la sessione è stata terminata dal server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="26df9-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-228">po'</span><span class="sxs-lookup"><span data-stu-id="26df9-228">bit</span></span></p></td>
<td><p><span data-ttu-id="26df9-229">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="26df9-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-231">DateTime</span><span class="sxs-lookup"><span data-stu-id="26df9-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="26df9-232">Ora della risposta al primo messaggio di invito.</span><span class="sxs-lookup"><span data-stu-id="26df9-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="26df9-233">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="26df9-234">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="26df9-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-236">int</span><span class="sxs-lookup"><span data-stu-id="26df9-236">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-237">Codice di risposta SIP per l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="26df9-238">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="26df9-239">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="26df9-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-241">int</span><span class="sxs-lookup"><span data-stu-id="26df9-241">int</span></span></p></td>
<td><p><span data-ttu-id="26df9-242">ID di diagnostica acquisito dalle intestazioni SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-245">Tipo di contenuto per la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-248">Nome di dominio completo del server front-end che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-251">Nome di dominio completo del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-254">Mediation Server usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-257">Gateway usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26df9-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26df9-260">FQDN dell'Edge Server usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26df9-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-262">smallint</span><span class="sxs-lookup"><span data-stu-id="26df9-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="26df9-263">Indica gli attributi dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="26df9-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="26df9-264">Le definizioni di attributo seguenti sono consentite:</span><span class="sxs-lookup"><span data-stu-id="26df9-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="26df9-265">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="26df9-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26df9-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="26df9-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="26df9-267">smallint</span><span class="sxs-lookup"><span data-stu-id="26df9-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="26df9-268">Indica gli attributi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="26df9-268">Indicates the call attributes.</span></span> <span data-ttu-id="26df9-269">Sono consentite le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="26df9-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="26df9-270">0x01-riprovato Session0</span><span class="sxs-lookup"><span data-stu-id="26df9-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="26df9-271">X02-chiamata effettuata dall'agente per conto di un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="26df9-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

