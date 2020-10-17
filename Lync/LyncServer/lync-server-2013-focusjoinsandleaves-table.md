---
title: 'Lync Server 2013: Tabella FocusJoinsAndLeaves'
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
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500833"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e2ca6-102">Tabella FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ca6-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ca6-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e2ca6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e2ca6-104">Ogni record contenuto in questa tabella contiene le informazioni di registrazione dettagli chiamata relative alle informazioni di partecipazione e di uscita di un utente per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="e2ca6-105">Ogni conferenza è rappresentata in questa tabella da un record per ogni volta che un utente si unisce e lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2ca6-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e2ca6-106">Column</span></span></th>
<th><span data-ttu-id="e2ca6-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e2ca6-107">Data Type</span></span></th>
<th><span data-ttu-id="e2ca6-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="e2ca6-108">Key/Index</span></span></th>
<th><span data-ttu-id="e2ca6-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e2ca6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e2ca6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e2ca6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-113">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-113">Time of conference instance.</span></span> <span data-ttu-id="e2ca6-114">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e2ca6-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e2ca6-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-117">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-117">int</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e2ca6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-119">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="e2ca6-120">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e2ca6-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e2ca6-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e2ca6-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-124">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e2ca6-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-125">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-125">Time of session request.</span></span> <span data-ttu-id="e2ca6-126">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e2ca6-127">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e2ca6-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-129">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-129">int</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-130">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e2ca6-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-131">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-131">ID number to identify the session.</span></span> <span data-ttu-id="e2ca6-132">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e2ca6-133">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e2ca6-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-135">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-135">int</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-136">Stranieri</span><span class="sxs-lookup"><span data-stu-id="e2ca6-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-137">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-139">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2ca6-140">Se un utente ha effettuato l'accesso contemporaneamente a più computer o dispositivi, <strong>UserInstance</strong> viene utilizzato per identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-142">po'</span><span class="sxs-lookup"><span data-stu-id="e2ca6-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2ca6-143">Se l'utente ha effettuato l'accesso da interno o meno.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-145">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2ca6-146">Ruolo dell'utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-148">datetime</span><span class="sxs-lookup"><span data-stu-id="e2ca6-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2ca6-149">Data e ora in cui l'utente accede alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-151">datetime</span><span class="sxs-lookup"><span data-stu-id="e2ca6-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2ca6-152">Data e ora in cui l'utente lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ca6-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-154">int</span><span class="sxs-lookup"><span data-stu-id="e2ca6-154">int</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="e2ca6-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e2ca6-156">Versione del software client dell'utente, a cui viene fatto riferimento alla <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ca6-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e2ca6-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2ca6-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="e2ca6-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2ca6-159">Identificatore univoco globale (GUID) dell'endpoint utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="e2ca6-160">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2ca6-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

