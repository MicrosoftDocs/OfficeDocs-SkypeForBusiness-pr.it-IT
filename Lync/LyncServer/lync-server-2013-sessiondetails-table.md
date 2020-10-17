---
title: 'Lync Server 2013: tabella SessionDetails'
description: 'Lync Server 2013: tabella SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569932"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="7ee85-103">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ee85-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ee85-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7ee85-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7ee85-105">Ogni record rappresenta una sessione peer-to-peer, ovvero una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea con due partecipanti o un altro tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="7ee85-106">È possibile eseguire una tabella di join con la [tabella media in Lync Server 2013](lync-server-2013-media-table.md) per trovare i dettagli di ogni supporto coinvolto in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="7ee85-107">Si noti che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ee85-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ee85-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="7ee85-108">Column</span></span></th>
<th><span data-ttu-id="7ee85-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7ee85-109">Data Type</span></span></th>
<th><span data-ttu-id="7ee85-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="7ee85-110">Key/Index</span></span></th>
<th><span data-ttu-id="7ee85-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7ee85-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7ee85-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ee85-114">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="7ee85-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-115">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-115">Time of session request.</span></span> <span data-ttu-id="7ee85-116">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7ee85-117">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-119">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-119">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-120">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="7ee85-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-121">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-121">ID number to identify the session.</span></span> <span data-ttu-id="7ee85-122">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. \* vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="7ee85-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-124">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7ee85-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-125">GUID per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="7ee85-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-127">datetime</span><span class="sxs-lookup"><span data-stu-id="7ee85-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ee85-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-129">Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="7ee85-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="7ee85-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-132">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-132">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-133">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-134">Numero ID per l'identificazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-134">ID number to identify the session.</span></span> <span data-ttu-id="7ee85-135">Valore utilizzato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="7ee85-136">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-138">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-138">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-139">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-140">ID di un utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-140">ID of one user in the session.</span></span> <span data-ttu-id="7ee85-141">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-143">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-143">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-144">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-145">ID dell'altro utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-145">ID of the other user in the session.</span></span> <span data-ttu-id="7ee85-146">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-148">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ee85-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-149">GUID che identifica l'endpoint utilizzato dal primo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="7ee85-150">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ee85-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-152">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ee85-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-153">GUID che identifica l'endpoint utilizzato dal secondo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="7ee85-154">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ee85-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-156">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-156">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-157">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-158">URI utente di destinazione originale nella richiesta SIP.</span><span class="sxs-lookup"><span data-stu-id="7ee85-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="7ee85-159">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-161">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-161">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-162">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-163">ID dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-163">ID of the user who started the session.</span></span> <span data-ttu-id="7ee85-164">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-166">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-166">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-167">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-168">Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee85-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="7ee85-169">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-171">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-171">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-172">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-173">ID dell'utente da quale proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee85-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="7ee85-174">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-176">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-176">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-177">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-178">ID del Front End Server utilizzato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="7ee85-179">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-181">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-181">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-182">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-183">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="7ee85-184">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-186">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-186">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-187">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-188">Tipo di contenuto utilizzato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-188">Content type used in the session.</span></span> <span data-ttu-id="7ee85-189">Per ulteriori informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-191">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-191">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-192">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-193">Versione del client utilizzata da User1.</span><span class="sxs-lookup"><span data-stu-id="7ee85-193">Client version used by User1.</span></span> <span data-ttu-id="7ee85-194">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-196">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-196">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-197">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-198">Versione del client utilizzata da User2.</span><span class="sxs-lookup"><span data-stu-id="7ee85-198">Client version used by User2.</span></span> <span data-ttu-id="7ee85-199">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-201">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-201">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-202">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-203">Server perimetrale utilizzato da User1.</span><span class="sxs-lookup"><span data-stu-id="7ee85-203">Edge Server used by User1.</span></span> <span data-ttu-id="7ee85-204">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-206">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-206">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-207">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-208">Server perimetrale utilizzato da User2.</span><span class="sxs-lookup"><span data-stu-id="7ee85-208">Edge Server used by User2.</span></span> <span data-ttu-id="7ee85-209">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-211">po'</span><span class="sxs-lookup"><span data-stu-id="7ee85-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-212">Indica se User1 è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="7ee85-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-214">po'</span><span class="sxs-lookup"><span data-stu-id="7ee85-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-215">Indica se User2 è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="7ee85-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-217">datetime</span><span class="sxs-lookup"><span data-stu-id="7ee85-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-218">Ora della prima richiesta INVITE.</span><span class="sxs-lookup"><span data-stu-id="7ee85-218">The time of the first INVITE request.</span></span> <span data-ttu-id="7ee85-219">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7ee85-220">Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="7ee85-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="7ee85-221">I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7ee85-222">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="7ee85-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-224">datetime</span><span class="sxs-lookup"><span data-stu-id="7ee85-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-225">Ora della risposta al primo messaggio INVITE.</span><span class="sxs-lookup"><span data-stu-id="7ee85-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="7ee85-226">I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7ee85-227">Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="7ee85-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-229">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="7ee85-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-234">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-235">ID diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="7ee85-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-237">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-237">int</span></span></p></td>
<td><p><span data-ttu-id="7ee85-238">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7ee85-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7ee85-239">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee85-239">Call priority.</span></span> <span data-ttu-id="7ee85-240">Per ulteriori informazioni, vedere la <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7ee85-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-242">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-243">Numero di messaggi inviati da User1 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-245">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-246">Numero di messaggi inviati da User2 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-248">datetime</span><span class="sxs-lookup"><span data-stu-id="7ee85-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-249">Orario al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="7ee85-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-251">int</span><span class="sxs-lookup"><span data-stu-id="7ee85-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-p123">Set di bit che indica il tipo di contenuto multimediale della sessione. Di seguito sono elencate le definizioni dei tipi:</span><span class="sxs-lookup"><span data-stu-id="7ee85-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-254">IM</span><span class="sxs-lookup"><span data-stu-id="7ee85-254">IM</span></span></p></td>
<td><p><span data-ttu-id="7ee85-255">1 </span><span class="sxs-lookup"><span data-stu-id="7ee85-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="7ee85-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="7ee85-257">2</span><span class="sxs-lookup"><span data-stu-id="7ee85-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="7ee85-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="7ee85-259">4 </span><span class="sxs-lookup"><span data-stu-id="7ee85-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="7ee85-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="7ee85-261">8 </span><span class="sxs-lookup"><span data-stu-id="7ee85-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-262">AUDIO</span><span class="sxs-lookup"><span data-stu-id="7ee85-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="7ee85-263">16 </span><span class="sxs-lookup"><span data-stu-id="7ee85-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-264">VIDEO</span><span class="sxs-lookup"><span data-stu-id="7ee85-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="7ee85-265">32</span><span class="sxs-lookup"><span data-stu-id="7ee85-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="7ee85-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="7ee85-267">64</span><span class="sxs-lookup"><span data-stu-id="7ee85-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-269">smallint</span><span class="sxs-lookup"><span data-stu-id="7ee85-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-p124">Set di bit che indica gli attributi di User1. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ee85-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ee85-272">0x01 - Integrato con telefono da tavolo</span><span class="sxs-lookup"><span data-stu-id="7ee85-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-274">smallint</span><span class="sxs-lookup"><span data-stu-id="7ee85-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-p125">Set di bit che indica gli attributi di User2. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ee85-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ee85-277">0x01 - Integrato con telefono da tavolo</span><span class="sxs-lookup"><span data-stu-id="7ee85-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ee85-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-279">smallint</span><span class="sxs-lookup"><span data-stu-id="7ee85-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-p126">Set di bit che indica gli attributi della chiamata. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ee85-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ee85-282">0x01 - Nuovi tentativi di sessione</span><span class="sxs-lookup"><span data-stu-id="7ee85-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="7ee85-283">0x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="7ee85-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ee85-284"><strong>Elaborati</strong></span><span class="sxs-lookup"><span data-stu-id="7ee85-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="7ee85-285">po'</span><span class="sxs-lookup"><span data-stu-id="7ee85-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ee85-286">Per uso interno del servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7ee85-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="7ee85-287">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ee85-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7ee85-288">\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="7ee85-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="7ee85-289">Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="7ee85-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

