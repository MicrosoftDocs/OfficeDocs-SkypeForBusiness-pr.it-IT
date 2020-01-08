---
title: 'Lync Server 2013: Visualizzazione McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="77a7e-102">Visualizzazione McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77a7e-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77a7e-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="77a7e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="77a7e-104">La Visualizzazione McuJoinsAndLeaves archivia le informazioni sugli utenti che partecipano e lasciano informazioni per un server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="77a7e-105">Ogni record in questa visualizzazione contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="77a7e-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="77a7e-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77a7e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77a7e-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="77a7e-107">Column</span></span></th>
<th><span data-ttu-id="77a7e-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="77a7e-108">Data Type</span></span></th>
<th><span data-ttu-id="77a7e-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="77a7e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="77a7e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="77a7e-112">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-112">Time of conference instance.</span></span> <span data-ttu-id="77a7e-113">Usato in combinazione con SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="77a7e-114">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-116">int</span><span class="sxs-lookup"><span data-stu-id="77a7e-116">int</span></span></p></td>
<td><p><span data-ttu-id="77a7e-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="77a7e-118">Usato in combinazione con SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="77a7e-119">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77a7e-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-122">URI del server dei servizi di conferenza a cui l'utente ha effettuato la connessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77a7e-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-125">URI del server dei servizi di conferenza a cui l'utente ha effettuato la connessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="77a7e-126">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77a7e-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-129">URI dell'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77a7e-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-132">Il tipo di URI dell'utente di cui è stata acquisita l'immissione/uscita delle informazioni sul server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="77a7e-133">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77a7e-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-136">Il tenant dell'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="77a7e-137">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="77a7e-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-140">La versione del client usata dall'utente di cui è stata acquisita l'entrata/uscita delle informazioni sul server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-142">int</span><span class="sxs-lookup"><span data-stu-id="77a7e-142">int</span></span></p></td>
<td><p><span data-ttu-id="77a7e-143">Il client usato dall'utente per cui sono state acquisite le informazioni di join/leave del server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="77a7e-144">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="77a7e-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-147">Nome della categoria del client usata dall'utente di cui è stata acquisita l'entrata/uscita delle informazioni del server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-149">int</span><span class="sxs-lookup"><span data-stu-id="77a7e-149">int</span></span></p></td>
<td><p><span data-ttu-id="77a7e-150">Identifica in modo univoco la combinazione utente/dispositivo per gli utenti che accedono simultaneamente a più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="77a7e-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-152">po'</span><span class="sxs-lookup"><span data-stu-id="77a7e-152">bit</span></span></p></td>
<td><p><span data-ttu-id="77a7e-153">Bit che indica se l'utente è un utente interno o meno.</span><span class="sxs-lookup"><span data-stu-id="77a7e-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-155">DateTime</span><span class="sxs-lookup"><span data-stu-id="77a7e-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="77a7e-156">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-156">Time of session request.</span></span> <span data-ttu-id="77a7e-157">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="77a7e-158">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-160">int</span><span class="sxs-lookup"><span data-stu-id="77a7e-160">int</span></span></p></td>
<td><p><span data-ttu-id="77a7e-161">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-161">ID number to identify the session.</span></span> <span data-ttu-id="77a7e-162">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="77a7e-163">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77a7e-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="77a7e-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="77a7e-166">ID finestra di dialogo SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="77a7e-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="77a7e-167">Il formato è: Dialog; from-tag; to-tag.</span><span class="sxs-lookup"><span data-stu-id="77a7e-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a7e-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="77a7e-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="77a7e-170">Volta che l'utente ha aderito al server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a7e-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="77a7e-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77a7e-172">DateTime</span><span class="sxs-lookup"><span data-stu-id="77a7e-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="77a7e-173">Volta che l'utente ha lasciato il server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77a7e-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

