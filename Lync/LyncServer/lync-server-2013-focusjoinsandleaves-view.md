---
title: 'Lync Server 2013: visualizzazione FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="59ab1-102">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59ab1-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59ab1-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="59ab1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="59ab1-104">La visualizzazione FocusJoinsAndLeaves archivia le informazioni su come partecipare e abbandonare informazioni per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="59ab1-105">Ogni conferenza viene rappresentata in questa visualizzazione da un record scritto ogni volta che un utente si unisce e lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="59ab1-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59ab1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59ab1-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="59ab1-107">Column</span></span></th>
<th><span data-ttu-id="59ab1-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="59ab1-108">Data Type</span></span></th>
<th><span data-ttu-id="59ab1-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="59ab1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="59ab1-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="59ab1-112">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-112">Time of conference instance.</span></span> <span data-ttu-id="59ab1-113">Usato in combinazione con SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="59ab1-114">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-116">int</span><span class="sxs-lookup"><span data-stu-id="59ab1-116">int</span></span></p></td>
<td><p><span data-ttu-id="59ab1-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="59ab1-118">Usato in combinazione con SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="59ab1-119">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="59ab1-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-122">URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59ab1-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-125">Tipo di URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="59ab1-126">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59ab1-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-129">Tenant dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="59ab1-130">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="59ab1-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="59ab1-133">Identificatore univoco dell'utente per cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59ab1-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-136">Versione del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-138">int</span><span class="sxs-lookup"><span data-stu-id="59ab1-138">int</span></span></p></td>
<td><p><span data-ttu-id="59ab1-139">Client usato dall'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="59ab1-140">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="59ab1-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-143">Nome della categoria del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-145">int</span><span class="sxs-lookup"><span data-stu-id="59ab1-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-147">po'</span><span class="sxs-lookup"><span data-stu-id="59ab1-147">bit</span></span></p></td>
<td><p><span data-ttu-id="59ab1-148">Bit che indica se l'utente è un utente interno o meno.</span><span class="sxs-lookup"><span data-stu-id="59ab1-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="59ab1-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="59ab1-151">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="59ab1-151">Time of session request.</span></span> <span data-ttu-id="59ab1-152">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="59ab1-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="59ab1-153">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59ab1-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-155">int</span><span class="sxs-lookup"><span data-stu-id="59ab1-155">int</span></span></p></td>
<td><p><span data-ttu-id="59ab1-156">Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, UserInstance viene usato per identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59ab1-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="59ab1-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-159">ID finestra di dialogo SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="59ab1-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="59ab1-160">Il formato è: Dialog; from-tag; to-tag.</span><span class="sxs-lookup"><span data-stu-id="59ab1-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-162">DateTime</span><span class="sxs-lookup"><span data-stu-id="59ab1-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="59ab1-163">Ora in cui l'utente ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59ab1-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-165">DateTime</span><span class="sxs-lookup"><span data-stu-id="59ab1-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="59ab1-166">Ora in cui l'utente ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="59ab1-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59ab1-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="59ab1-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="59ab1-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59ab1-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59ab1-169">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="59ab1-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

