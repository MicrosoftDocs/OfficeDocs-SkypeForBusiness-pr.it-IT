---
title: 'Lync Server 2013: Visualizzazione McuJoinsAndLeaves'
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
ms.openlocfilehash: 329396549a02a354939b166c8785b875faee2f78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524723"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="e28ae-102">Visualizzazione McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e28ae-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e28ae-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e28ae-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e28ae-104">La visualizzazione McuJoinsAndLeaves contiene informazioni sulla partecipazione e l'abbandono da parte degli utenti in un server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e28ae-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="e28ae-105">In ogni record di questa visualizzazione sono inclusi dettagli di chiamata su una combinazione di partecipazione o abbandono di un utente e un server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e28ae-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="e28ae-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e28ae-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e28ae-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="e28ae-107">Column</span></span></th>
<th><span data-ttu-id="e28ae-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e28ae-108">Data Type</span></span></th>
<th><span data-ttu-id="e28ae-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e28ae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e28ae-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e28ae-112">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e28ae-112">Time of conference instance.</span></span> <span data-ttu-id="e28ae-113">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e28ae-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="e28ae-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-116">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-116">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e28ae-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="e28ae-118">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e28ae-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="e28ae-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-122">URI del server per le conferenze al quale l'utente è connesso.</span><span class="sxs-lookup"><span data-stu-id="e28ae-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-125">URI del server per le conferenze al quale l'utente è connesso.</span><span class="sxs-lookup"><span data-stu-id="e28ae-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="e28ae-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e28ae-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-129">URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-132">Tipo di URI dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e28ae-133">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-136">Tenant dell'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e28ae-137">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e28ae-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-140">Versione del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-142">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-142">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-143">Client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e28ae-144">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e28ae-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-147">Nome di categoria del client utilizzato dall'utente le cui informazioni di accesso e abbandono relative al server per le conferenze sono state raccolte.</span><span class="sxs-lookup"><span data-stu-id="e28ae-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-149">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-149">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-150">Identifica in maniera univoca la combinazione utente/dispositivo per gli utenti connessi a più di un dispositivo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e28ae-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-152">po'</span><span class="sxs-lookup"><span data-stu-id="e28ae-152">bit</span></span></p></td>
<td><p><span data-ttu-id="e28ae-153">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="e28ae-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-155">datetime</span><span class="sxs-lookup"><span data-stu-id="e28ae-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="e28ae-156">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="e28ae-156">Time of session request.</span></span> <span data-ttu-id="e28ae-157">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e28ae-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e28ae-158">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-160">int</span><span class="sxs-lookup"><span data-stu-id="e28ae-160">int</span></span></p></td>
<td><p><span data-ttu-id="e28ae-161">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e28ae-161">ID number to identify the session.</span></span> <span data-ttu-id="e28ae-162">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e28ae-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e28ae-163">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e28ae-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e28ae-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e28ae-p110">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="e28ae-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e28ae-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-169">datetime</span><span class="sxs-lookup"><span data-stu-id="e28ae-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="e28ae-170">Ora di connessione dell'utente al server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e28ae-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e28ae-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e28ae-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e28ae-172">datetime</span><span class="sxs-lookup"><span data-stu-id="e28ae-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="e28ae-173">Ora di disconnessione dell'utente dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="e28ae-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

