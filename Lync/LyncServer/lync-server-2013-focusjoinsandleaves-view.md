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
ms.openlocfilehash: 9e97346929851bec53ab228988d72fb4813316d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="706cc-102">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706cc-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="706cc-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="706cc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="706cc-104">La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="706cc-105">In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="706cc-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="706cc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="706cc-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="706cc-107">Column</span></span></th>
<th><span data-ttu-id="706cc-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="706cc-108">Data Type</span></span></th>
<th><span data-ttu-id="706cc-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="706cc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="706cc-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="706cc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="706cc-112">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-112">Time of conference instance.</span></span> <span data-ttu-id="706cc-113">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="706cc-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-116">int</span><span class="sxs-lookup"><span data-stu-id="706cc-116">int</span></span></p></td>
<td><p><span data-ttu-id="706cc-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="706cc-118">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="706cc-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="706cc-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="706cc-122">URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="706cc-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="706cc-125">Tipo di URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="706cc-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="706cc-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="706cc-129">Tenant dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="706cc-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="706cc-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="706cc-133">Identificatore univoco dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="706cc-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="706cc-136">Versione del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-138">int</span><span class="sxs-lookup"><span data-stu-id="706cc-138">int</span></span></p></td>
<td><p><span data-ttu-id="706cc-139">Client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="706cc-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="706cc-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="706cc-143">Nome della categoria del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="706cc-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-145">int</span><span class="sxs-lookup"><span data-stu-id="706cc-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-147">po'</span><span class="sxs-lookup"><span data-stu-id="706cc-147">bit</span></span></p></td>
<td><p><span data-ttu-id="706cc-148">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="706cc-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-150">datetime</span><span class="sxs-lookup"><span data-stu-id="706cc-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="706cc-151">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="706cc-151">Time of session request.</span></span> <span data-ttu-id="706cc-152">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="706cc-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="706cc-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="706cc-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-155">int</span><span class="sxs-lookup"><span data-stu-id="706cc-155">int</span></span></p></td>
<td><p><span data-ttu-id="706cc-156">Se un utente è connesso a più computer o dispositivi contemporaneamente, UserInstance consente di identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="706cc-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="706cc-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="706cc-p108">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="706cc-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-162">datetime</span><span class="sxs-lookup"><span data-stu-id="706cc-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="706cc-163">Ora in cui l'utente inizia a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706cc-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-165">datetime</span><span class="sxs-lookup"><span data-stu-id="706cc-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="706cc-166">Ora in cui l'utente esce dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="706cc-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706cc-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="706cc-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="706cc-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="706cc-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="706cc-169">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="706cc-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

