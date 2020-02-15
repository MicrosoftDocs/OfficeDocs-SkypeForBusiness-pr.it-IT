---
title: 'Lync Server 2013: tabella SessionDetails'
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
ms.openlocfilehash: fee9a2f2b59fc523224a778004b5c0beb041a12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="feeb5-102">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feeb5-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feeb5-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="feeb5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="feeb5-104">Ogni record rappresenta una sessione peer-to-peer, ovvero una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea con due partecipanti o un altro tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="feeb5-105">È possibile eseguire una tabella di join con la [tabella media in Lync Server 2013](lync-server-2013-media-table.md) per trovare i dettagli di ogni supporto coinvolto in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="feeb5-106">Si noti che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feeb5-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feeb5-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="feeb5-107">Column</span></span></th>
<th><span data-ttu-id="feeb5-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="feeb5-108">Data Type</span></span></th>
<th><span data-ttu-id="feeb5-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="feeb5-109">Key/Index</span></span></th>
<th><span data-ttu-id="feeb5-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="feeb5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="feeb5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="feeb5-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="feeb5-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-114">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-114">Time of session request.</span></span> <span data-ttu-id="feeb5-115">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="feeb5-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-118">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-118">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="feeb5-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-120">ID identificativo della sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-120">ID number to identify the session.</span></span> <span data-ttu-id="feeb5-121">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. \* vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="feeb5-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="feeb5-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-124">GUID per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="feeb5-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-126">datetime</span><span class="sxs-lookup"><span data-stu-id="feeb5-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="feeb5-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-128">Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="feeb5-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="feeb5-129">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-131">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-131">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-132">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-133">Numero ID per l'identificazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-133">ID number to identify the session.</span></span> <span data-ttu-id="feeb5-134">Valore utilizzato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="feeb5-135">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-137">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-137">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-138">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-139">ID di un utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-139">ID of one user in the session.</span></span> <span data-ttu-id="feeb5-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-142">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-142">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-143">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-144">ID dell'altro utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-144">ID of the other user in the session.</span></span> <span data-ttu-id="feeb5-145">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="feeb5-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-148">GUID che identifica l'endpoint utilizzato dal primo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="feeb5-149">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feeb5-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="feeb5-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-152">GUID che identifica l'endpoint utilizzato dal secondo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="feeb5-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feeb5-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-155">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-155">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-156">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-157">URI utente di destinazione originale nella richiesta SIP.</span><span class="sxs-lookup"><span data-stu-id="feeb5-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="feeb5-158">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-160">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-160">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-161">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-162">ID dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-162">ID of the user who started the session.</span></span> <span data-ttu-id="feeb5-163">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-165">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-165">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-166">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-167">Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="feeb5-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="feeb5-168">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-170">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-170">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-171">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-172">ID dell'utente da quale proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="feeb5-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="feeb5-173">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-175">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-175">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-176">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-177">ID del Front End Server utilizzato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="feeb5-178">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-180">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-180">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-181">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-182">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="feeb5-183">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-185">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-185">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-186">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-187">Tipo di contenuto utilizzato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-187">Content type used in the session.</span></span> <span data-ttu-id="feeb5-188">Per ulteriori informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-190">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-190">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-191">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-192">Versione del client utilizzata da User1.</span><span class="sxs-lookup"><span data-stu-id="feeb5-192">Client version used by User1.</span></span> <span data-ttu-id="feeb5-193">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-195">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-195">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-196">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-197">Versione del client utilizzata da User2.</span><span class="sxs-lookup"><span data-stu-id="feeb5-197">Client version used by User2.</span></span> <span data-ttu-id="feeb5-198">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-200">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-200">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-201">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-202">Server perimetrale utilizzato da User1.</span><span class="sxs-lookup"><span data-stu-id="feeb5-202">Edge Server used by User1.</span></span> <span data-ttu-id="feeb5-203">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-205">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-205">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-206">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-207">Server perimetrale utilizzato da User2.</span><span class="sxs-lookup"><span data-stu-id="feeb5-207">Edge Server used by User2.</span></span> <span data-ttu-id="feeb5-208">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-210">po'</span><span class="sxs-lookup"><span data-stu-id="feeb5-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-211">Indica se User1 è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="feeb5-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-213">po'</span><span class="sxs-lookup"><span data-stu-id="feeb5-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-214">Indica se User2 è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="feeb5-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-216">datetime</span><span class="sxs-lookup"><span data-stu-id="feeb5-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-217">Ora della prima richiesta INVITE.</span><span class="sxs-lookup"><span data-stu-id="feeb5-217">The time of the first INVITE request.</span></span> <span data-ttu-id="feeb5-218">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="feeb5-219">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="feeb5-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="feeb5-220">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="feeb5-221">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="feeb5-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-223">datetime</span><span class="sxs-lookup"><span data-stu-id="feeb5-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-224">Ora della risposta al primo messaggio INVITE.</span><span class="sxs-lookup"><span data-stu-id="feeb5-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="feeb5-225">I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="feeb5-226">Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="feeb5-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-228">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-p121">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="feeb5-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-233">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-234">ID diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="feeb5-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-236">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-236">int</span></span></p></td>
<td><p><span data-ttu-id="feeb5-237">Stranieri</span><span class="sxs-lookup"><span data-stu-id="feeb5-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="feeb5-238">Priorità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="feeb5-238">Call priority.</span></span> <span data-ttu-id="feeb5-239">Per ulteriori informazioni, vedere la <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="feeb5-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-241">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-242">Numero di messaggi inviati da User1 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-244">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-245">Numero di messaggi inviati da User2 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-247">datetime</span><span class="sxs-lookup"><span data-stu-id="feeb5-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-248">Orario al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="feeb5-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-250">int</span><span class="sxs-lookup"><span data-stu-id="feeb5-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-p123">Set di bit che indica il tipo di contenuto multimediale della sessione. Di seguito sono elencate le definizioni dei tipi:</span><span class="sxs-lookup"><span data-stu-id="feeb5-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-253">IM</span><span class="sxs-lookup"><span data-stu-id="feeb5-253">IM</span></span></p></td>
<td><p><span data-ttu-id="feeb5-254">1 </span><span class="sxs-lookup"><span data-stu-id="feeb5-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="feeb5-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="feeb5-256">2 </span><span class="sxs-lookup"><span data-stu-id="feeb5-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="feeb5-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="feeb5-258">4 </span><span class="sxs-lookup"><span data-stu-id="feeb5-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="feeb5-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="feeb5-260">8 </span><span class="sxs-lookup"><span data-stu-id="feeb5-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="feeb5-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="feeb5-262">16 </span><span class="sxs-lookup"><span data-stu-id="feeb5-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-263">VIDEO</span><span class="sxs-lookup"><span data-stu-id="feeb5-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="feeb5-264">32</span><span class="sxs-lookup"><span data-stu-id="feeb5-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="feeb5-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="feeb5-266">64</span><span class="sxs-lookup"><span data-stu-id="feeb5-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-268">smallint</span><span class="sxs-lookup"><span data-stu-id="feeb5-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-p124">Set di bit che indica gli attributi di User1. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="feeb5-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="feeb5-271">0x01 - Integrato con telefono da tavolo</span><span class="sxs-lookup"><span data-stu-id="feeb5-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-273">smallint</span><span class="sxs-lookup"><span data-stu-id="feeb5-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-p125">Set di bit che indica gli attributi di User2. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="feeb5-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="feeb5-276">0x01 - Integrato con telefono da tavolo</span><span class="sxs-lookup"><span data-stu-id="feeb5-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feeb5-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-278">smallint</span><span class="sxs-lookup"><span data-stu-id="feeb5-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-p126">Set di bit che indica gli attributi della chiamata. Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="feeb5-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="feeb5-281">0x01 - Nuovi tentativi di sessione</span><span class="sxs-lookup"><span data-stu-id="feeb5-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="feeb5-282">0x02 - Chiamata effettuata da un agente per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="feeb5-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feeb5-283"><strong>Elaborati</strong></span><span class="sxs-lookup"><span data-stu-id="feeb5-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="feeb5-284">po'</span><span class="sxs-lookup"><span data-stu-id="feeb5-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="feeb5-285">Per uso interno del servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="feeb5-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="feeb5-286">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feeb5-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="feeb5-287">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="feeb5-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="feeb5-288">Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="feeb5-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

