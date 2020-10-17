---
title: 'Lync Server 2013: Tabella McuJoinsAndLeaves'
description: 'Lync Server 2013: Tabella McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556502"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="db4be-103">Tabella McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db4be-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db4be-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="db4be-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="db4be-105">Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="db4be-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="db4be-106">Ad esempio, se un utente si unisce a una conferenza che include Web Conferencing e elementi audio/video, verrà creato un record per l'aggiunta di Web Conferencing per l'utente e verrà creato un altro record per l'aggiunta di conferenze audio/video dell'utente.</span><span class="sxs-lookup"><span data-stu-id="db4be-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db4be-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="db4be-107">Column</span></span></th>
<th><span data-ttu-id="db4be-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db4be-108">Data Type</span></span></th>
<th><span data-ttu-id="db4be-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="db4be-109">Key/Index</span></span></th>
<th><span data-ttu-id="db4be-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db4be-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db4be-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-112">datetime</span><span class="sxs-lookup"><span data-stu-id="db4be-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="db4be-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="db4be-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-114">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="db4be-114">Time of conference instance.</span></span> <span data-ttu-id="db4be-115">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="db4be-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="db4be-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4be-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-118">int</span><span class="sxs-lookup"><span data-stu-id="db4be-118">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="db4be-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="db4be-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="db4be-121">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="db4be-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="db4be-122">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db4be-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-124">int</span><span class="sxs-lookup"><span data-stu-id="db4be-124">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-125">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="db4be-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-126">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="db4be-126">Unique number identifying this user.</span></span> <span data-ttu-id="db4be-127">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4be-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-129">int</span><span class="sxs-lookup"><span data-stu-id="db4be-129">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-130">Principale</span><span class="sxs-lookup"><span data-stu-id="db4be-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="db4be-131">Se un utente ha effettuato l'accesso contemporaneamente a più computer o dispositivi, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db4be-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db4be-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-133">po'</span><span class="sxs-lookup"><span data-stu-id="db4be-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db4be-134">Se l'utente partecipa da una rete PSTN o meno.</span><span class="sxs-lookup"><span data-stu-id="db4be-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4be-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-136">int</span><span class="sxs-lookup"><span data-stu-id="db4be-136">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-137">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="db4be-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-138">Numero univoco che identifica il server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="db4be-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="db4be-139">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mcus-table.md">tabella MCU in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db4be-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-141">datetime</span><span class="sxs-lookup"><span data-stu-id="db4be-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="db4be-142">Stranieri</span><span class="sxs-lookup"><span data-stu-id="db4be-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-143">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="db4be-143">Time of session request.</span></span> <span data-ttu-id="db4be-144">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="db4be-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="db4be-145">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4be-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-147">int</span><span class="sxs-lookup"><span data-stu-id="db4be-147">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-148">Stranieri</span><span class="sxs-lookup"><span data-stu-id="db4be-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-149">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="db4be-149">ID number to identify the session.</span></span> <span data-ttu-id="db4be-150">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="db4be-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="db4be-151">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db4be-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-153">datetime</span><span class="sxs-lookup"><span data-stu-id="db4be-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db4be-154">Data e ora in cui l'utente accede a questo server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="db4be-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4be-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-156">datetime</span><span class="sxs-lookup"><span data-stu-id="db4be-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db4be-157">Data e ora in cui l'utente lascia questo server Conferencing.</span><span class="sxs-lookup"><span data-stu-id="db4be-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db4be-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="db4be-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="db4be-159">int</span><span class="sxs-lookup"><span data-stu-id="db4be-159">int</span></span></p></td>
<td><p><span data-ttu-id="db4be-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="db4be-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="db4be-161">Identificatore che specifica il numero di versione dell'utilizzo del software client nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="db4be-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="db4be-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db4be-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="db4be-163">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db4be-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

