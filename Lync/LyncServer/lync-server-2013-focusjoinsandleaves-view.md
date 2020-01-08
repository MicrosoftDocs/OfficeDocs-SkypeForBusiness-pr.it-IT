---
title: 'Lync Server 2013: visualizzazione FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="3b3d4-102">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b3d4-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b3d4-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3b3d4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3b3d4-104">La visualizzazione FocusJoinsAndLeaves archivia le informazioni su come partecipare e abbandonare informazioni per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="3b3d4-105">Ogni conferenza viene rappresentata in questa visualizzazione da un record scritto ogni volta che un utente si unisce e lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="3b3d4-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b3d4-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="3b3d4-107">Column</span></span></th>
<th><span data-ttu-id="3b3d4-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3b3d4-108">Data Type</span></span></th>
<th><span data-ttu-id="3b3d4-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3b3d4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b3d4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-112">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-112">Time of conference instance.</span></span> <span data-ttu-id="3b3d4-113">Usato in combinazione con SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="3b3d4-114">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-116">int</span><span class="sxs-lookup"><span data-stu-id="3b3d4-116">int</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="3b3d4-118">Usato in combinazione con SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="3b3d4-119">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-122">URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-125">Tipo di URI dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="3b3d4-126">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-129">Tenant dell'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="3b3d4-130">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3b3d4-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-133">Identificatore univoco dell'utente per cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-136">Versione del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-138">int</span><span class="sxs-lookup"><span data-stu-id="3b3d4-138">int</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-139">Client usato dall'utente per cui sono state acquisite le informazioni di join/congedo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="3b3d4-140">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-143">Nome della categoria del client usata dall'utente in cui sono state acquisite le informazioni di join/leave di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-145">int</span><span class="sxs-lookup"><span data-stu-id="3b3d4-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-147">po'</span><span class="sxs-lookup"><span data-stu-id="3b3d4-147">bit</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-148">Bit che indica se l'utente è un utente interno o meno.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b3d4-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-151">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-151">Time of session request.</span></span> <span data-ttu-id="3b3d4-152">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="3b3d4-153">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b3d4-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-155">int</span><span class="sxs-lookup"><span data-stu-id="3b3d4-155">int</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-156">Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, UserInstance viene usato per identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-159">ID finestra di dialogo SIP della sessione.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="3b3d4-160">Il formato è: Dialog; from-tag; to-tag.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-162">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b3d4-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-163">Ora in cui l'utente ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b3d4-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-165">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b3d4-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-166">Ora in cui l'utente ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b3d4-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="3b3d4-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="3b3d4-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3b3d4-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3b3d4-169">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="3b3d4-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

