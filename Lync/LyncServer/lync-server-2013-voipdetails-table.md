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
ms.openlocfilehash: d459262d5126dc6d55f930b20e54cbb1e69e04e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="b2304-102">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2304-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2304-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b2304-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b2304-104">Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="b2304-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2304-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="b2304-105">Column</span></span></th>
<th><span data-ttu-id="b2304-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b2304-106">Data Type</span></span></th>
<th><span data-ttu-id="b2304-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="b2304-107">Key/Index</span></span></th>
<th><span data-ttu-id="b2304-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b2304-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2304-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b2304-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b2304-111">Principale</span><span class="sxs-lookup"><span data-stu-id="b2304-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2304-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="b2304-112">Time of session request.</span></span> <span data-ttu-id="b2304-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b2304-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b2304-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2304-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-116">int</span><span class="sxs-lookup"><span data-stu-id="b2304-116">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-117">Principale</span><span class="sxs-lookup"><span data-stu-id="b2304-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2304-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="b2304-118">ID number to identify the session.</span></span> <span data-ttu-id="b2304-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b2304-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b2304-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2304-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-122">int</span><span class="sxs-lookup"><span data-stu-id="b2304-122">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-124"><strong>PhoneId</strong> del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b2304-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="b2304-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b2304-126">Se questo valore è diverso da NULL e <strong>FromGatewayId</strong> è diverso da NULL, il chiamante è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="b2304-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2304-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-128">int</span><span class="sxs-lookup"><span data-stu-id="b2304-128">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-129">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-130"><strong>PhoneId</strong> del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2304-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="b2304-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b2304-132">Se questo valore è diverso da NULL e <strong>ToGatewayId</strong> è diverso da NULL, il destinatario della chiamata è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="b2304-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2304-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-134">int</span><span class="sxs-lookup"><span data-stu-id="b2304-134">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-135">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-136">Mediation Server da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2304-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="b2304-137">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2304-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-139">int</span><span class="sxs-lookup"><span data-stu-id="b2304-139">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-141">Mediation Server a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2304-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="b2304-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2304-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-144">int</span><span class="sxs-lookup"><span data-stu-id="b2304-144">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-145">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-146">Gateway da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2304-146">Gateway the call is coming from.</span></span> <span data-ttu-id="b2304-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2304-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-149">int</span><span class="sxs-lookup"><span data-stu-id="b2304-149">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-150">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-151">Gateway a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2304-151">Gateway the call is going to.</span></span> <span data-ttu-id="b2304-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2304-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-154">int</span><span class="sxs-lookup"><span data-stu-id="b2304-154">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-156">URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI.</span><span class="sxs-lookup"><span data-stu-id="b2304-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="b2304-157">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2304-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b2304-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2304-159">int</span><span class="sxs-lookup"><span data-stu-id="b2304-159">int</span></span></p></td>
<td><p><span data-ttu-id="b2304-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b2304-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2304-161">ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono.</span><span class="sxs-lookup"><span data-stu-id="b2304-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="b2304-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2304-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

