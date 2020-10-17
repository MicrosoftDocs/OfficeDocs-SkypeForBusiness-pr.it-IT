---
title: 'Lync Server 2013: tabella VoipDetails'
description: 'Lync Server 2013: tabella VoipDetails.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566282"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="4dc65-103">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dc65-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc65-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4dc65-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4dc65-105">Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="4dc65-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dc65-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="4dc65-106">Column</span></span></th>
<th><span data-ttu-id="4dc65-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4dc65-107">Data Type</span></span></th>
<th><span data-ttu-id="4dc65-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="4dc65-108">Key/Index</span></span></th>
<th><span data-ttu-id="4dc65-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4dc65-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dc65-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4dc65-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4dc65-112">Principale</span><span class="sxs-lookup"><span data-stu-id="4dc65-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4dc65-113">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="4dc65-113">Time of session request.</span></span> <span data-ttu-id="4dc65-114">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4dc65-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4dc65-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc65-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-117">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-117">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-118">Principale</span><span class="sxs-lookup"><span data-stu-id="4dc65-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4dc65-119">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="4dc65-119">ID number to identify the session.</span></span> <span data-ttu-id="4dc65-120">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4dc65-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4dc65-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc65-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-123">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-123">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-124">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-125"><strong>PhoneId</strong> del chiamante.</span><span class="sxs-lookup"><span data-stu-id="4dc65-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="4dc65-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4dc65-127">Se questo valore è diverso da NULL e <strong>FromGatewayId</strong> è diverso da NULL, il chiamante è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dc65-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc65-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-129">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-129">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-130">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-131"><strong>PhoneId</strong> del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc65-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="4dc65-132">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4dc65-133">Se questo valore è diverso da NULL e <strong>ToGatewayId</strong> è diverso da NULL, il destinatario della chiamata è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dc65-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc65-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-135">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-135">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-136">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-137">Mediation Server da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc65-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="4dc65-138">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc65-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-140">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-140">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-141">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-142">Mediation Server a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc65-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="4dc65-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc65-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-145">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-145">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-146">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-147">Gateway da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc65-147">Gateway the call is coming from.</span></span> <span data-ttu-id="4dc65-148">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc65-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-150">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-150">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-151">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-152">Gateway a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc65-152">Gateway the call is going to.</span></span> <span data-ttu-id="4dc65-153">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc65-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-155">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-155">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-156">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-157">URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI.</span><span class="sxs-lookup"><span data-stu-id="4dc65-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="4dc65-158">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc65-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="4dc65-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc65-160">int</span><span class="sxs-lookup"><span data-stu-id="4dc65-160">int</span></span></p></td>
<td><p><span data-ttu-id="4dc65-161">Stranieri</span><span class="sxs-lookup"><span data-stu-id="4dc65-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4dc65-162">ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono.</span><span class="sxs-lookup"><span data-stu-id="4dc65-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="4dc65-163">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4dc65-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

