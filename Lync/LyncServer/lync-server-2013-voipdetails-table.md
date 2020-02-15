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
ms.openlocfilehash: fe3d41021016d6d6e21e7112597bb6206dc46d95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="6a2d7-102">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a2d7-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a2d7-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6a2d7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6a2d7-104">Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a2d7-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="6a2d7-105">Column</span></span></th>
<th><span data-ttu-id="6a2d7-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6a2d7-106">Data Type</span></span></th>
<th><span data-ttu-id="6a2d7-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="6a2d7-107">Key/Index</span></span></th>
<th><span data-ttu-id="6a2d7-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6a2d7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a2d7-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6a2d7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-111">Principale</span><span class="sxs-lookup"><span data-stu-id="6a2d7-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-112">Time of session request.</span></span> <span data-ttu-id="6a2d7-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6a2d7-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2d7-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-116">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-116">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-117">Principale</span><span class="sxs-lookup"><span data-stu-id="6a2d7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-118">ID number to identify the session.</span></span> <span data-ttu-id="6a2d7-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6a2d7-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a2d7-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-122">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-122">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-124"><strong>PhoneId</strong> del chiamante.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="6a2d7-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="6a2d7-126">Se questo valore è diverso da NULL e <strong>FromGatewayId</strong> è diverso da NULL, il chiamante è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2d7-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-128">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-128">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-129">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-130"><strong>PhoneId</strong> del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="6a2d7-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="6a2d7-132">Se questo valore è diverso da NULL e <strong>ToGatewayId</strong> è diverso da NULL, il destinatario della chiamata è un utente PSTN.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a2d7-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-134">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-134">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-135">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-136">Mediation Server da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="6a2d7-137">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2d7-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-139">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-139">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-141">Mediation Server a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="6a2d7-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a2d7-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-144">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-144">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-145">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-146">Gateway da cui proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-146">Gateway the call is coming from.</span></span> <span data-ttu-id="6a2d7-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2d7-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-149">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-149">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-150">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-151">Gateway a cui andrà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-151">Gateway the call is going to.</span></span> <span data-ttu-id="6a2d7-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a2d7-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-154">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-154">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-156">URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="6a2d7-157">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2d7-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2d7-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2d7-159">int</span><span class="sxs-lookup"><span data-stu-id="6a2d7-159">int</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6a2d7-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2d7-161">ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono.</span><span class="sxs-lookup"><span data-stu-id="6a2d7-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="6a2d7-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-phones-table.md">tabella Phones in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2d7-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

