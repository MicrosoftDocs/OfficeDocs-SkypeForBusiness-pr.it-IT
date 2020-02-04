---
title: 'Lync Server 2013: Tabella SessionDetails'
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
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="88d7e-102">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88d7e-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88d7e-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="88d7e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="88d7e-104">Ogni record rappresenta una sessione peer-to-peer, che potrebbe essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="88d7e-105">È possibile eseguire un join di tabella con la [tabella multimediale in Lync Server 2013](lync-server-2013-media-table.md) per trovare i dettagli di ogni elemento multimediale coinvolto in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="88d7e-106">Tieni presente che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88d7e-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88d7e-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="88d7e-107">Column</span></span></th>
<th><span data-ttu-id="88d7e-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="88d7e-108">Data Type</span></span></th>
<th><span data-ttu-id="88d7e-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="88d7e-109">Key/Index</span></span></th>
<th><span data-ttu-id="88d7e-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="88d7e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="88d7e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="88d7e-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="88d7e-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-114">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-114">Time of session request.</span></span> <span data-ttu-id="88d7e-115">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="88d7e-116">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-118">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-118">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-119">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="88d7e-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-120">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-120">ID number to identify the session.</span></span> <span data-ttu-id="88d7e-121">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. \* vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="88d7e-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="88d7e-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-124">GUID per la correlazione di più sessioni.</span><span class="sxs-lookup"><span data-stu-id="88d7e-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="88d7e-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="88d7e-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-128">Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="88d7e-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="88d7e-129">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-131">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-131">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-132">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-133">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-133">ID number to identify the session.</span></span> <span data-ttu-id="88d7e-134">Usato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="88d7e-135">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-137">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-137">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-138">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-139">ID di un utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-139">ID of one user in the session.</span></span> <span data-ttu-id="88d7e-140">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-142">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-142">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-143">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-144">ID dell'altro utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-144">ID of the other user in the session.</span></span> <span data-ttu-id="88d7e-145">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="88d7e-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-148">GUID che identifica l'endpoint usato dal primo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="88d7e-149">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88d7e-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="88d7e-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-152">GUID che identifica l'endpoint usato dal secondo utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="88d7e-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88d7e-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-155">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-155">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-156">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-157">L'originale all'URI utente nella richiesta SIP.</span><span class="sxs-lookup"><span data-stu-id="88d7e-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="88d7e-158">per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-160">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-160">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-161">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-162">ID dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-162">ID of the user who started the session.</span></span> <span data-ttu-id="88d7e-163">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-165">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-165">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-166">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-167">Indica l'ID dell'utente di chi è il chiamante per conto.</span><span class="sxs-lookup"><span data-stu-id="88d7e-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="88d7e-168">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-170">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-170">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-171">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-172">ID dell'utente con cui si fa riferimento alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="88d7e-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="88d7e-173">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-175">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-175">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-176">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-177">ID del server front-end usato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="88d7e-178">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-180">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-180">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-181">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-182">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="88d7e-183">Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-185">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-185">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-186">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-187">Tipo di contenuto usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-187">Content type used in the session.</span></span> <span data-ttu-id="88d7e-188">Per altre informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-190">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-190">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-191">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-192">Versione client usata da User1.</span><span class="sxs-lookup"><span data-stu-id="88d7e-192">Client version used by User1.</span></span> <span data-ttu-id="88d7e-193">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-195">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-195">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-196">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-197">Versione client usata da User2.</span><span class="sxs-lookup"><span data-stu-id="88d7e-197">Client version used by User2.</span></span> <span data-ttu-id="88d7e-198">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-200">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-200">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-201">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-202">Server perimetrale usato da User1.</span><span class="sxs-lookup"><span data-stu-id="88d7e-202">Edge Server used by User1.</span></span> <span data-ttu-id="88d7e-203">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-205">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-205">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-206">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-207">Edge Server usato da User2.</span><span class="sxs-lookup"><span data-stu-id="88d7e-207">Edge Server used by User2.</span></span> <span data-ttu-id="88d7e-208">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-210">po'</span><span class="sxs-lookup"><span data-stu-id="88d7e-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-211">Se l'utente User1 ha effettuato l'accesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="88d7e-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-213">po'</span><span class="sxs-lookup"><span data-stu-id="88d7e-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-214">Se User2 è connesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="88d7e-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-216">DateTime</span><span class="sxs-lookup"><span data-stu-id="88d7e-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-217">L'ora della prima richiesta di invito.</span><span class="sxs-lookup"><span data-stu-id="88d7e-217">The time of the first INVITE request.</span></span> <span data-ttu-id="88d7e-218">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="88d7e-219">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="88d7e-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="88d7e-220">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="88d7e-221">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="88d7e-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-223">DateTime</span><span class="sxs-lookup"><span data-stu-id="88d7e-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-224">L'ora della risposta al primo messaggio di invito.</span><span class="sxs-lookup"><span data-stu-id="88d7e-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="88d7e-225">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="88d7e-226">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="88d7e-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-228">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-229">Codice di risposta SIP per l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="88d7e-230">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="88d7e-231">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="88d7e-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-233">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-234">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="88d7e-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-236">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-236">int</span></span></p></td>
<td><p><span data-ttu-id="88d7e-237">Esterna</span><span class="sxs-lookup"><span data-stu-id="88d7e-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88d7e-238">Chiama priorità.</span><span class="sxs-lookup"><span data-stu-id="88d7e-238">Call priority.</span></span> <span data-ttu-id="88d7e-239">Per altre informazioni, vedere la <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88d7e-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-241">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-242">Numero di messaggi inviati da User1 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-244">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-245">Numero di messaggi inviati da User2 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-247">DateTime</span><span class="sxs-lookup"><span data-stu-id="88d7e-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-248">Ora alla fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-250">int</span><span class="sxs-lookup"><span data-stu-id="88d7e-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-251">Set di bit che indica il tipo di elemento multimediale della sessione.</span><span class="sxs-lookup"><span data-stu-id="88d7e-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="88d7e-252">Sono elencate le definizioni dei tipi:</span><span class="sxs-lookup"><span data-stu-id="88d7e-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-253">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="88d7e-253">IM</span></span></p></td>
<td><p><span data-ttu-id="88d7e-254">1</span><span class="sxs-lookup"><span data-stu-id="88d7e-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="88d7e-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="88d7e-256">2</span><span class="sxs-lookup"><span data-stu-id="88d7e-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="88d7e-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="88d7e-258">4</span><span class="sxs-lookup"><span data-stu-id="88d7e-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="88d7e-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="88d7e-260">8</span><span class="sxs-lookup"><span data-stu-id="88d7e-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="88d7e-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="88d7e-262">16</span><span class="sxs-lookup"><span data-stu-id="88d7e-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-263">VIDEO</span><span class="sxs-lookup"><span data-stu-id="88d7e-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="88d7e-264">32</span><span class="sxs-lookup"><span data-stu-id="88d7e-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="88d7e-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="88d7e-266">64</span><span class="sxs-lookup"><span data-stu-id="88d7e-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-268">smallint</span><span class="sxs-lookup"><span data-stu-id="88d7e-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-269">Set di bit che indica gli attributi User1.</span><span class="sxs-lookup"><span data-stu-id="88d7e-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="88d7e-270">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="88d7e-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="88d7e-271">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="88d7e-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-273">smallint</span><span class="sxs-lookup"><span data-stu-id="88d7e-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-274">Set di bit che indica gli attributi User2.</span><span class="sxs-lookup"><span data-stu-id="88d7e-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="88d7e-275">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="88d7e-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="88d7e-276">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="88d7e-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88d7e-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-278">smallint</span><span class="sxs-lookup"><span data-stu-id="88d7e-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-279">Set di bit che indica gli attributi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="88d7e-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="88d7e-280">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="88d7e-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="88d7e-281">0x01-Riprova sessione</span><span class="sxs-lookup"><span data-stu-id="88d7e-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="88d7e-282">0x02-chiamata effettuata dall'agente per conto di un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="88d7e-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88d7e-283"><strong>Elaborate</strong></span><span class="sxs-lookup"><span data-stu-id="88d7e-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="88d7e-284">po'</span><span class="sxs-lookup"><span data-stu-id="88d7e-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88d7e-285">Per l'uso interno da parte del servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="88d7e-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="88d7e-286">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88d7e-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88d7e-287">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="88d7e-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="88d7e-288">Se più sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1, per un altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="88d7e-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

