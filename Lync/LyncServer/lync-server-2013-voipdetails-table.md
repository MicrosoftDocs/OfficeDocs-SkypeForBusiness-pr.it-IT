---
title: 'Lync Server 2013: Tabella VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="bef72-102">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bef72-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bef72-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bef72-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bef72-104">Ogni record rappresenta una chiamata di 1 2-Party in cui almeno un utente è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="bef72-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bef72-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="bef72-105">Column</span></span></th>
<th><span data-ttu-id="bef72-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bef72-106">Data Type</span></span></th>
<th><span data-ttu-id="bef72-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="bef72-107">Key/Index</span></span></th>
<th><span data-ttu-id="bef72-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bef72-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bef72-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="bef72-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="bef72-111">Principale</span><span class="sxs-lookup"><span data-stu-id="bef72-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="bef72-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="bef72-112">Time of session request.</span></span> <span data-ttu-id="bef72-113">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="bef72-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bef72-114">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef72-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-116">int</span><span class="sxs-lookup"><span data-stu-id="bef72-116">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-117">Principale</span><span class="sxs-lookup"><span data-stu-id="bef72-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="bef72-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="bef72-118">ID number to identify the session.</span></span> <span data-ttu-id="bef72-119">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="bef72-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bef72-120">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef72-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-122">int</span><span class="sxs-lookup"><span data-stu-id="bef72-122">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-124"><strong>PhoneId</strong> del chiamante.</span><span class="sxs-lookup"><span data-stu-id="bef72-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="bef72-125">Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="bef72-126">Se non è NULL e <strong>FromGatewayId</strong> non è null, il chiamante era un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="bef72-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef72-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-128">int</span><span class="sxs-lookup"><span data-stu-id="bef72-128">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-129">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-130"><strong>PhoneId</strong> del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bef72-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="bef72-131">Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="bef72-132">Se non è NULL e <strong>ToGatewayId</strong> non è null, il destinatario della chiamata è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="bef72-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef72-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-134">int</span><span class="sxs-lookup"><span data-stu-id="bef72-134">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-135">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-136">Server di mediazione da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bef72-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="bef72-137">Per altre informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef72-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-139">int</span><span class="sxs-lookup"><span data-stu-id="bef72-139">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-140">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-141">Il server di mediazione chiamato sta andando.</span><span class="sxs-lookup"><span data-stu-id="bef72-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="bef72-142">Per altre informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef72-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-144">int</span><span class="sxs-lookup"><span data-stu-id="bef72-144">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-145">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-146">Gateway da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bef72-146">Gateway the call is coming from.</span></span> <span data-ttu-id="bef72-147">Per altre informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef72-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-149">int</span><span class="sxs-lookup"><span data-stu-id="bef72-149">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-150">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-151">Gateway che la chiamata sta per.</span><span class="sxs-lookup"><span data-stu-id="bef72-151">Gateway the call is going to.</span></span> <span data-ttu-id="bef72-152">Per altre informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef72-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-154">int</span><span class="sxs-lookup"><span data-stu-id="bef72-154">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-155">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-156">URI dell'utente che ha scollegato la chiamata, se l'utente ha un URI.</span><span class="sxs-lookup"><span data-stu-id="bef72-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="bef72-157">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef72-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="bef72-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="bef72-159">int</span><span class="sxs-lookup"><span data-stu-id="bef72-159">int</span></span></p></td>
<td><p><span data-ttu-id="bef72-160">Esterna</span><span class="sxs-lookup"><span data-stu-id="bef72-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bef72-161">ID del telefono che ha scollegato la chiamata è stata disconnessa da un telefono.</span><span class="sxs-lookup"><span data-stu-id="bef72-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="bef72-162">Per altre informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella telefoni in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bef72-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

