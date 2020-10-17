---
title: 'Lync Server 2013: Visualizzazione McuJoinsAndLeaves'
description: 'Lync Server 2013: Visualizzazione McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556492"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="e664e-103">Visualizzazione McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e664e-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e664e-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e664e-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e664e-105">La visualizzazione McuJoinsAndLeaves contiene informazioni sulla partecipazione e l'abbandono da parte degli utenti in un server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e664e-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="e664e-106">In ogni record di questa visualizzazione sono inclusi dettagli di chiamata su una combinazione di partecipazione o abbandono di un utente e un server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e664e-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="e664e-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e664e-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e664e-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="e664e-108">Column</span></span></th>
<th><span data-ttu-id="e664e-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e664e-109">Data Type</span></span></th>
<th><span data-ttu-id="e664e-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e664e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e664e-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e664e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e664e-113">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e664e-113">Time of conference instance.</span></span> <span data-ttu-id="e664e-114">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e664e-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="e664e-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-117">int</span><span class="sxs-lookup"><span data-stu-id="e664e-117">int</span></span></p></td>
<td><p><span data-ttu-id="e664e-118">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e664e-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="e664e-119">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e664e-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="e664e-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e664e-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e664e-123">URI del server per le conferenze al quale l'utente è connesso.</span><span class="sxs-lookup"><span data-stu-id="e664e-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e664e-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e664e-126">URI del server per le conferenze al quale l'utente è connesso.</span><span class="sxs-lookup"><span data-stu-id="e664e-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="e664e-127">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e664e-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e664e-130">URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e664e-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e664e-133">Tipo di URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e664e-134">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e664e-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e664e-137">Tenant dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e664e-138">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e664e-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e664e-141">Versione del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-143">int</span><span class="sxs-lookup"><span data-stu-id="e664e-143">int</span></span></p></td>
<td><p><span data-ttu-id="e664e-144">Client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e664e-145">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e664e-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e664e-148">Nome di categoria del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e664e-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-150">int</span><span class="sxs-lookup"><span data-stu-id="e664e-150">int</span></span></p></td>
<td><p><span data-ttu-id="e664e-151">Identifica in maniera univoca la combinazione utente/dispositivo per gli utenti connessi a più di un dispositivo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e664e-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-153">po'</span><span class="sxs-lookup"><span data-stu-id="e664e-153">bit</span></span></p></td>
<td><p><span data-ttu-id="e664e-154">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="e664e-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-156">datetime</span><span class="sxs-lookup"><span data-stu-id="e664e-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="e664e-157">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="e664e-157">Time of session request.</span></span> <span data-ttu-id="e664e-158">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e664e-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e664e-159">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-161">int</span><span class="sxs-lookup"><span data-stu-id="e664e-161">int</span></span></p></td>
<td><p><span data-ttu-id="e664e-162">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e664e-162">ID number to identify the session.</span></span> <span data-ttu-id="e664e-163">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e664e-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e664e-164">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e664e-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e664e-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e664e-p110">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="e664e-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e664e-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-170">datetime</span><span class="sxs-lookup"><span data-stu-id="e664e-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="e664e-171">Ora di connessione dell'utente al server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e664e-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e664e-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e664e-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e664e-173">datetime</span><span class="sxs-lookup"><span data-stu-id="e664e-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="e664e-174">Ora di disconnessione dell'utente dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e664e-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

