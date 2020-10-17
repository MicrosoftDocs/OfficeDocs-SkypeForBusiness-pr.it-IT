---
title: 'Lync Server 2013: tabella VoipDetails'
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
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535413"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="c7a1d-102">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7a1d-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a1d-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c7a1d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c7a1d-104">Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a1d-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="c7a1d-105">Column</span></span></th>
<th><span data-ttu-id="c7a1d-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c7a1d-106">Data Type</span></span></th>
<th><span data-ttu-id="c7a1d-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c7a1d-107">Key/Index</span></span></th>
<th><span data-ttu-id="c7a1d-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c7a1d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a1d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="c7a1d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-111">Principale</span><span class="sxs-lookup"><span data-stu-id="c7a1d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-112">Time of session request.</span></span> <span data-ttu-id="c7a1d-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7a1d-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a1d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-116">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-116">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-117">Principale</span><span class="sxs-lookup"><span data-stu-id="c7a1d-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-118">ID number to identify the session.</span></span> <span data-ttu-id="c7a1d-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7a1d-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a1d-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-122">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-122">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-124"><strong>PhoneId</strong> del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="c7a1d-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="c7a1d-126">Se questo valore è diverso da NULL e <strong>FromGatewayId</strong> è diverso da NULL, il chiamante è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a1d-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-128">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-128">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-129">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-130"><strong>PhoneId</strong> del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="c7a1d-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="c7a1d-132">Se questo valore è diverso da NULL e <strong>ToGatewayId</strong> è diverso da NULL, il destinatario della chiamata è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a1d-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-134">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-134">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-135">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-136">Mediation Server da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="c7a1d-137">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a1d-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-139">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-139">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-141">Mediation Server a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="c7a1d-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a1d-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-144">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-144">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-145">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-146">Gateway da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-146">Gateway the call is coming from.</span></span> <span data-ttu-id="c7a1d-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a1d-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-149">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-149">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-150">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-151">Gateway a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-151">Gateway the call is going to.</span></span> <span data-ttu-id="c7a1d-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a1d-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-154">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-154">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-156">URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="c7a1d-157">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a1d-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="c7a1d-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a1d-159">int</span><span class="sxs-lookup"><span data-stu-id="c7a1d-159">int</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="c7a1d-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7a1d-161">ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono.</span><span class="sxs-lookup"><span data-stu-id="c7a1d-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="c7a1d-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7a1d-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

