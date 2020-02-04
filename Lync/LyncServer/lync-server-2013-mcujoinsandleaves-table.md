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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="a22ee-102">Tabella McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a22ee-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a22ee-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a22ee-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a22ee-104">Ogni record in questa tabella contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="a22ee-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="a22ee-105">Ad esempio, se un utente partecipa a una conferenza che include Web Conferencing e audio/video Elements, verrà creato un record per il Web Conferencing di tale utente e verrà creato un altro record per la partecipazione a conferenze audio/video dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a22ee-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a22ee-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="a22ee-106">Column</span></span></th>
<th><span data-ttu-id="a22ee-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a22ee-107">Data Type</span></span></th>
<th><span data-ttu-id="a22ee-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a22ee-108">Key/Index</span></span></th>
<th><span data-ttu-id="a22ee-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a22ee-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="a22ee-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a22ee-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a22ee-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-113">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-113">Time of conference instance.</span></span> <span data-ttu-id="a22ee-114">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a22ee-115">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a22ee-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-117">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-117">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-118">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a22ee-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-119">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="a22ee-120">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a22ee-121">Per altre informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-123">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-123">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-124">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a22ee-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-125">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="a22ee-125">Unique number identifying this user.</span></span> <span data-ttu-id="a22ee-126">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a22ee-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-128">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-128">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-129">Principale</span><span class="sxs-lookup"><span data-stu-id="a22ee-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="a22ee-130">Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a22ee-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-132">po'</span><span class="sxs-lookup"><span data-stu-id="a22ee-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a22ee-133">Se l'utente partecipa da una rete PSTN o meno.</span><span class="sxs-lookup"><span data-stu-id="a22ee-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a22ee-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-135">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-135">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-136">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a22ee-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-137">Numero univoco che identifica questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="a22ee-138">Per altre informazioni, vedere la <a href="lync-server-2013-mcus-table.md">tabella MCU in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="a22ee-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="a22ee-141">Esterna</span><span class="sxs-lookup"><span data-stu-id="a22ee-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-142">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="a22ee-142">Time of session request.</span></span> <span data-ttu-id="a22ee-143">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a22ee-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a22ee-144">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a22ee-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-146">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-146">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-147">Esterna</span><span class="sxs-lookup"><span data-stu-id="a22ee-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-148">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a22ee-148">ID number to identify the session.</span></span> <span data-ttu-id="a22ee-149">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a22ee-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a22ee-150">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-152">DateTime</span><span class="sxs-lookup"><span data-stu-id="a22ee-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a22ee-153">L'ora in cui l'utente partecipa a questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a22ee-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-155">DateTime</span><span class="sxs-lookup"><span data-stu-id="a22ee-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a22ee-156">L'ora in cui l'utente lascia questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a22ee-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="a22ee-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a22ee-158">int</span><span class="sxs-lookup"><span data-stu-id="a22ee-158">int</span></span></p></td>
<td><p><span data-ttu-id="a22ee-159">Esterna</span><span class="sxs-lookup"><span data-stu-id="a22ee-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a22ee-160">Identificatore che specifica il numero di versione dell'uso del software client nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="a22ee-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="a22ee-161">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a22ee-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a22ee-162">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22ee-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

