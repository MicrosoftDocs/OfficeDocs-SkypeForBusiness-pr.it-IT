---
title: 'Lync Server 2013: Tabella McuJoinsAndLeaves'
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
ms.openlocfilehash: ae21b9a8ec2107d8a2bd0a99f1e21d6f182a830e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="137e6-102">Tabella McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137e6-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="137e6-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="137e6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="137e6-104">Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="137e6-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="137e6-105">Ad esempio, se un utente si unisce a una conferenza che include Web Conferencing e elementi audio/video, verrà creato un record per l'aggiunta di Web Conferencing per l'utente e verrà creato un altro record per l'aggiunta di conferenze audio/video dell'utente.</span><span class="sxs-lookup"><span data-stu-id="137e6-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="137e6-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="137e6-106">Column</span></span></th>
<th><span data-ttu-id="137e6-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="137e6-107">Data Type</span></span></th>
<th><span data-ttu-id="137e6-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="137e6-108">Key/Index</span></span></th>
<th><span data-ttu-id="137e6-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="137e6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="137e6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="137e6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="137e6-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="137e6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-113">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="137e6-113">Time of conference instance.</span></span> <span data-ttu-id="137e6-114">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="137e6-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="137e6-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137e6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-117">int</span><span class="sxs-lookup"><span data-stu-id="137e6-117">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="137e6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-119">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="137e6-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="137e6-120">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="137e6-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="137e6-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137e6-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-123">int</span><span class="sxs-lookup"><span data-stu-id="137e6-123">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-124">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="137e6-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-125">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="137e6-125">Unique number identifying this user.</span></span> <span data-ttu-id="137e6-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137e6-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-128">int</span><span class="sxs-lookup"><span data-stu-id="137e6-128">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-129">Principale</span><span class="sxs-lookup"><span data-stu-id="137e6-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="137e6-130">Se un utente ha effettuato l'accesso contemporaneamente a più computer o dispositivi, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="137e6-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137e6-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-132">po'</span><span class="sxs-lookup"><span data-stu-id="137e6-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="137e6-133">Se l'utente partecipa da una rete PSTN o meno.</span><span class="sxs-lookup"><span data-stu-id="137e6-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137e6-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-135">int</span><span class="sxs-lookup"><span data-stu-id="137e6-135">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-136">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="137e6-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-137">Numero univoco che identifica il server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="137e6-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="137e6-138">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mcus-table.md">tabella MCU in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137e6-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-140">datetime</span><span class="sxs-lookup"><span data-stu-id="137e6-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="137e6-141">Stranieri</span><span class="sxs-lookup"><span data-stu-id="137e6-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-142">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="137e6-142">Time of session request.</span></span> <span data-ttu-id="137e6-143">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="137e6-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="137e6-144">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137e6-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-146">int</span><span class="sxs-lookup"><span data-stu-id="137e6-146">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-147">Stranieri</span><span class="sxs-lookup"><span data-stu-id="137e6-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-148">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="137e6-148">ID number to identify the session.</span></span> <span data-ttu-id="137e6-149">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="137e6-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="137e6-150">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137e6-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-152">datetime</span><span class="sxs-lookup"><span data-stu-id="137e6-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="137e6-153">Data e ora in cui l'utente accede a questo server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="137e6-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="137e6-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-155">datetime</span><span class="sxs-lookup"><span data-stu-id="137e6-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="137e6-156">Data e ora in cui l'utente lascia questo server Conferencing.</span><span class="sxs-lookup"><span data-stu-id="137e6-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="137e6-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="137e6-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="137e6-158">int</span><span class="sxs-lookup"><span data-stu-id="137e6-158">int</span></span></p></td>
<td><p><span data-ttu-id="137e6-159">Stranieri</span><span class="sxs-lookup"><span data-stu-id="137e6-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="137e6-160">Identificatore che specifica il numero di versione dell'utilizzo del software client nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="137e6-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="137e6-161">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="137e6-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="137e6-162">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="137e6-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

