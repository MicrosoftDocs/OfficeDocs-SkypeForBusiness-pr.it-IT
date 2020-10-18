---
title: 'Lync Server 2013: Tabella FocusJoinsAndLeaves'
description: 'Lync Server 2013: Tabella FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577442"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="ab15d-103">Tabella FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab15d-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab15d-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ab15d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ab15d-105">Ogni record contenuto in questa tabella contiene le informazioni di registrazione dettagli chiamata relative alle informazioni di partecipazione e di uscita di un utente per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="ab15d-106">Ogni conferenza è rappresentata in questa tabella da un record per ogni volta che un utente si unisce e lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab15d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="ab15d-107">Column</span></span></th>
<th><span data-ttu-id="ab15d-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ab15d-108">Data Type</span></span></th>
<th><span data-ttu-id="ab15d-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="ab15d-109">Key/Index</span></span></th>
<th><span data-ttu-id="ab15d-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ab15d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ab15d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab15d-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ab15d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-114">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-114">Time of conference instance.</span></span> <span data-ttu-id="ab15d-115">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ab15d-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab15d-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-118">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-118">int</span></span></p></td>
<td><p><span data-ttu-id="ab15d-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ab15d-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="ab15d-121">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ab15d-122">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab15d-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-124">datetime</span><span class="sxs-lookup"><span data-stu-id="ab15d-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab15d-125">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ab15d-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-126">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="ab15d-126">Time of session request.</span></span> <span data-ttu-id="ab15d-127">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ab15d-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ab15d-128">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab15d-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-130">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-130">int</span></span></p></td>
<td><p><span data-ttu-id="ab15d-131">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ab15d-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-132">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="ab15d-132">ID number to identify the session.</span></span> <span data-ttu-id="ab15d-133">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ab15d-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ab15d-134">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab15d-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-136">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-136">int</span></span></p></td>
<td><p><span data-ttu-id="ab15d-137">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ab15d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-138">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ab15d-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-140">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab15d-141">Se un utente ha effettuato l'accesso contemporaneamente a più computer o dispositivi, <strong>UserInstance</strong> viene utilizzato per identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab15d-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-143">po'</span><span class="sxs-lookup"><span data-stu-id="ab15d-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ab15d-144">Se l'utente ha effettuato l'accesso da interno o meno.</span><span class="sxs-lookup"><span data-stu-id="ab15d-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-146">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ab15d-147">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="ab15d-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-149">datetime</span><span class="sxs-lookup"><span data-stu-id="ab15d-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ab15d-150">Data e ora in cui l'utente accede alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-152">datetime</span><span class="sxs-lookup"><span data-stu-id="ab15d-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ab15d-153">Data e ora in cui l'utente lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab15d-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-155">int</span><span class="sxs-lookup"><span data-stu-id="ab15d-155">int</span></span></p></td>
<td><p><span data-ttu-id="ab15d-156">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ab15d-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab15d-157">Versione del software client dell'utente, a cui viene fatto riferimento alla <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ab15d-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab15d-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ab15d-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab15d-159">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ab15d-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab15d-160">Identificatore univoco globale (GUID) dell'endpoint utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="ab15d-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="ab15d-161">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab15d-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

