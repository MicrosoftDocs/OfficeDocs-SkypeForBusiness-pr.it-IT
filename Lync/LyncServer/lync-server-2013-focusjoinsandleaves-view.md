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
ms.openlocfilehash: 8b71678b9fbd19cfd52c81976de0955ea39ce9e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500823"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="98c6a-102">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c6a-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c6a-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="98c6a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="98c6a-104">La visualizzazione FocusJoinsAndLeaves contiene informazioni sulle partecipazioni e le uscite per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="98c6a-105">In questa visualizzazione ogni conferenza è rappresentata da un record scritto ogni volta che un utente partecipa o esce da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="98c6a-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c6a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98c6a-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="98c6a-107">Column</span></span></th>
<th><span data-ttu-id="98c6a-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="98c6a-108">Data Type</span></span></th>
<th><span data-ttu-id="98c6a-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="98c6a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="98c6a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="98c6a-112">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-112">Time of conference instance.</span></span> <span data-ttu-id="98c6a-113">Valore utilizzato insieme a SessionIdSeq per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="98c6a-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-116">int</span><span class="sxs-lookup"><span data-stu-id="98c6a-116">int</span></span></p></td>
<td><p><span data-ttu-id="98c6a-117">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="98c6a-118">Valore utilizzato insieme a SessionIdTime per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="98c6a-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="98c6a-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-122">URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="98c6a-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-125">Tipo di URI dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="98c6a-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="98c6a-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-129">Tenant dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="98c6a-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="98c6a-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="98c6a-133">Identificatore univoco dell'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="98c6a-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-136">Versione del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-138">int</span><span class="sxs-lookup"><span data-stu-id="98c6a-138">int</span></span></p></td>
<td><p><span data-ttu-id="98c6a-139">Client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="98c6a-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="98c6a-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-143">Nome della categoria del client usato dall'utente le cui informazioni di partecipazione o uscita da una conferenza sono state acquisite.</span><span class="sxs-lookup"><span data-stu-id="98c6a-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-145">int</span><span class="sxs-lookup"><span data-stu-id="98c6a-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-147">po'</span><span class="sxs-lookup"><span data-stu-id="98c6a-147">bit</span></span></p></td>
<td><p><span data-ttu-id="98c6a-148">Bit che determina se l'utente è interno o meno.</span><span class="sxs-lookup"><span data-stu-id="98c6a-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-150">datetime</span><span class="sxs-lookup"><span data-stu-id="98c6a-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="98c6a-151">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="98c6a-151">Time of session request.</span></span> <span data-ttu-id="98c6a-152">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="98c6a-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="98c6a-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="98c6a-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-155">int</span><span class="sxs-lookup"><span data-stu-id="98c6a-155">int</span></span></p></td>
<td><p><span data-ttu-id="98c6a-156">Se un utente è connesso a più computer o dispositivi contemporaneamente, UserInstance consente di identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c6a-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="98c6a-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-p108">ID dialogo SIP della sessione, nel formato: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="98c6a-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-162">datetime</span><span class="sxs-lookup"><span data-stu-id="98c6a-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="98c6a-163">Ora in cui l'utente inizia a partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c6a-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-165">datetime</span><span class="sxs-lookup"><span data-stu-id="98c6a-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="98c6a-166">Ora in cui l'utente esce dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="98c6a-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c6a-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="98c6a-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="98c6a-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="98c6a-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98c6a-169">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="98c6a-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

