---
title: 'Lync Server 2013: visualizzazione FocusJoinsAndLeaves'
description: 'Lync Server 2013: visualizzazione FocusJoinsAndLeaves.'
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
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577452"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="0a4db-103">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a4db-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a4db-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0a4db-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0a4db-105">La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="0a4db-106">In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="0a4db-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a4db-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a4db-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="0a4db-108">Column</span></span></th>
<th><span data-ttu-id="0a4db-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0a4db-109">Data Type</span></span></th>
<th><span data-ttu-id="0a4db-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0a4db-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0a4db-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a4db-113">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-113">Time of conference instance.</span></span> <span data-ttu-id="0a4db-114">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="0a4db-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-117">int</span><span class="sxs-lookup"><span data-stu-id="0a4db-117">int</span></span></p></td>
<td><p><span data-ttu-id="0a4db-118">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="0a4db-119">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="0a4db-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0a4db-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-123">URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0a4db-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-126">Tipo di URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="0a4db-127">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0a4db-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-130">Tenant dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="0a4db-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="0a4db-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0a4db-134">Identificatore univoco dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0a4db-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-137">Versione del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-139">int</span><span class="sxs-lookup"><span data-stu-id="0a4db-139">int</span></span></p></td>
<td><p><span data-ttu-id="0a4db-140">Client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="0a4db-141">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0a4db-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-144">Nome della categoria del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="0a4db-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-146">int</span><span class="sxs-lookup"><span data-stu-id="0a4db-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-148">po'</span><span class="sxs-lookup"><span data-stu-id="0a4db-148">bit</span></span></p></td>
<td><p><span data-ttu-id="0a4db-149">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="0a4db-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-151">datetime</span><span class="sxs-lookup"><span data-stu-id="0a4db-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a4db-152">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="0a4db-152">Time of session request.</span></span> <span data-ttu-id="0a4db-153">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="0a4db-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="0a4db-154">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0a4db-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-156">int</span><span class="sxs-lookup"><span data-stu-id="0a4db-156">int</span></span></p></td>
<td><p><span data-ttu-id="0a4db-157">Se un utente è connesso a più computer o dispositivi contemporaneamente, UserInstance consente di identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a4db-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="0a4db-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-p108">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="0a4db-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-163">datetime</span><span class="sxs-lookup"><span data-stu-id="0a4db-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a4db-164">Ora in cui l'utente inizia a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4db-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-166">datetime</span><span class="sxs-lookup"><span data-stu-id="0a4db-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a4db-167">Ora in cui l'utente esce dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0a4db-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a4db-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="0a4db-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="0a4db-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0a4db-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0a4db-170">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="0a4db-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

