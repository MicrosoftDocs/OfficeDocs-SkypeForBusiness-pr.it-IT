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
ms.openlocfilehash: 85e13c744ed92dcbcb70b2da851b915e8c6f8104
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="9bd77-102">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bd77-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bd77-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9bd77-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9bd77-104">La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="9bd77-105">In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="9bd77-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bd77-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bd77-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="9bd77-107">Column</span></span></th>
<th><span data-ttu-id="9bd77-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9bd77-108">Data Type</span></span></th>
<th><span data-ttu-id="9bd77-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9bd77-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9bd77-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bd77-112">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-112">Time of conference instance.</span></span> <span data-ttu-id="9bd77-113">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="9bd77-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-116">int</span><span class="sxs-lookup"><span data-stu-id="9bd77-116">int</span></span></p></td>
<td><p><span data-ttu-id="9bd77-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="9bd77-118">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="9bd77-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bd77-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-122">URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bd77-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-125">Tipo di URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="9bd77-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bd77-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-129">Tenant dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="9bd77-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9bd77-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9bd77-133">Identificatore univoco dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bd77-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-136">Versione del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-138">int</span><span class="sxs-lookup"><span data-stu-id="9bd77-138">int</span></span></p></td>
<td><p><span data-ttu-id="9bd77-139">Client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="9bd77-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9bd77-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-143">Nome della categoria del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="9bd77-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-145">int</span><span class="sxs-lookup"><span data-stu-id="9bd77-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-147">po'</span><span class="sxs-lookup"><span data-stu-id="9bd77-147">bit</span></span></p></td>
<td><p><span data-ttu-id="9bd77-148">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="9bd77-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-150">datetime</span><span class="sxs-lookup"><span data-stu-id="9bd77-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bd77-151">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="9bd77-151">Time of session request.</span></span> <span data-ttu-id="9bd77-152">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="9bd77-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9bd77-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9bd77-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-155">int</span><span class="sxs-lookup"><span data-stu-id="9bd77-155">int</span></span></p></td>
<td><p><span data-ttu-id="9bd77-156">Se un utente è connesso a più computer o dispositivi contemporaneamente, UserInstance consente di identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bd77-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9bd77-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-p108">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="9bd77-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-162">datetime</span><span class="sxs-lookup"><span data-stu-id="9bd77-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bd77-163">Ora in cui l'utente inizia a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bd77-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-165">datetime</span><span class="sxs-lookup"><span data-stu-id="9bd77-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bd77-166">Ora in cui l'utente esce dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="9bd77-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bd77-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="9bd77-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="9bd77-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bd77-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bd77-169">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="9bd77-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

