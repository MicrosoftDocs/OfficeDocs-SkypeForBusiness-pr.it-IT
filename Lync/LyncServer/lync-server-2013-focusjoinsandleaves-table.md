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
ms.openlocfilehash: 4365e5bbfe92168047165adf6504333e1c34fab6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e3b55-102">Tabella FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3b55-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3b55-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e3b55-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e3b55-104">Ogni record in questa tabella contiene le informazioni CDR relative alle informazioni di partecipazione e di uscita di un utente per una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="e3b55-105">Ogni conferenza viene rappresentata in questa tabella da un record per ogni volta che un utente si unisce e lascia la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3b55-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e3b55-106">Column</span></span></th>
<th><span data-ttu-id="e3b55-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e3b55-107">Data Type</span></span></th>
<th><span data-ttu-id="e3b55-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="e3b55-108">Key/Index</span></span></th>
<th><span data-ttu-id="e3b55-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e3b55-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="e3b55-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3b55-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e3b55-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-113">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-113">Time of conference instance.</span></span> <span data-ttu-id="e3b55-114">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e3b55-115">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3b55-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-117">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-117">int</span></span></p></td>
<td><p><span data-ttu-id="e3b55-118">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e3b55-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-119">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="e3b55-120">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e3b55-121">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3b55-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-123">DateTime</span><span class="sxs-lookup"><span data-stu-id="e3b55-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3b55-124">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e3b55-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-125">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="e3b55-125">Time of session request.</span></span> <span data-ttu-id="e3b55-126">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e3b55-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3b55-127">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3b55-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-129">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-129">int</span></span></p></td>
<td><p><span data-ttu-id="e3b55-130">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e3b55-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-131">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e3b55-131">ID number to identify the session.</span></span> <span data-ttu-id="e3b55-132">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e3b55-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3b55-133">per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3b55-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-135">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-135">int</span></span></p></td>
<td><p><span data-ttu-id="e3b55-136">Esterna</span><span class="sxs-lookup"><span data-stu-id="e3b55-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-137">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3b55-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-139">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3b55-140">Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, <strong>UserInstance</strong> viene usato per identificare in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3b55-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-142">po'</span><span class="sxs-lookup"><span data-stu-id="e3b55-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3b55-143">Se l'utente ha effettuato l'accesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="e3b55-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-145">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3b55-146">Ruolo di questo utente nella conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="e3b55-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="e3b55-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3b55-149">L'ora in cui l'utente partecipa alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-151">DateTime</span><span class="sxs-lookup"><span data-stu-id="e3b55-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e3b55-152">L'ora in cui l'utente esce dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b55-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-154">int</span><span class="sxs-lookup"><span data-stu-id="e3b55-154">int</span></span></p></td>
<td><p><span data-ttu-id="e3b55-155">Esterna</span><span class="sxs-lookup"><span data-stu-id="e3b55-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3b55-156">Versione del software client dell'utente, a cui si fa riferimento alla <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3b55-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b55-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e3b55-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b55-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="e3b55-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3b55-159">Identificatore univoco globale (GUID) dell'endpoint usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="e3b55-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="e3b55-160">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3b55-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

