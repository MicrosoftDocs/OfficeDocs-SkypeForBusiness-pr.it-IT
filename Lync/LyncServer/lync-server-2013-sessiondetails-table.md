---
title: 'Lync Server 2013: Tabella SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="031cc-102">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="031cc-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="031cc-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="031cc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="031cc-104">Ogni record rappresenta una sessione peer-to-peer, che potrebbe essere una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea a due parti o un altro tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="031cc-105">È possibile eseguire un join di tabella con la [tabella multimediale in Lync Server 2013](lync-server-2013-media-table.md) per trovare i dettagli di ogni elemento multimediale coinvolto in questa sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="031cc-106">Tieni presente che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="031cc-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="031cc-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="031cc-107">Column</span></span></th>
<th><span data-ttu-id="031cc-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="031cc-108">Data Type</span></span></th>
<th><span data-ttu-id="031cc-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="031cc-109">Key/Index</span></span></th>
<th><span data-ttu-id="031cc-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="031cc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="031cc-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="031cc-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="031cc-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="031cc-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-114">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-114">Time of session request.</span></span> <span data-ttu-id="031cc-115">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="031cc-116">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-118">int</span><span class="sxs-lookup"><span data-stu-id="031cc-118">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-119">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="031cc-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-120">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-120">ID number to identify the session.</span></span> <span data-ttu-id="031cc-121">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. \* vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="031cc-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="031cc-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-124">GUID per la correlazione di più sessioni.</span><span class="sxs-lookup"><span data-stu-id="031cc-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="031cc-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="031cc-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-128">Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="031cc-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="031cc-129">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-131">int</span><span class="sxs-lookup"><span data-stu-id="031cc-131">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-132">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-133">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-133">ID number to identify the session.</span></span> <span data-ttu-id="031cc-134">Usato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="031cc-135">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-137">int</span><span class="sxs-lookup"><span data-stu-id="031cc-137">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-138">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-139">ID di un utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-139">ID of one user in the session.</span></span> <span data-ttu-id="031cc-140">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-142">int</span><span class="sxs-lookup"><span data-stu-id="031cc-142">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-143">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-144">ID dell'altro utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-144">ID of the other user in the session.</span></span> <span data-ttu-id="031cc-145">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="031cc-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-148">GUID che identifica l'endpoint usato dal primo utente della sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="031cc-149">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="031cc-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="031cc-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-152">GUID che identifica l'endpoint usato dal secondo utente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="031cc-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="031cc-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-155">int</span><span class="sxs-lookup"><span data-stu-id="031cc-155">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-156">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-157">L'originale all'URI utente nella richiesta SIP.</span><span class="sxs-lookup"><span data-stu-id="031cc-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="031cc-158">per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-160">int</span><span class="sxs-lookup"><span data-stu-id="031cc-160">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-161">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-162">ID dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-162">ID of the user who started the session.</span></span> <span data-ttu-id="031cc-163">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-165">int</span><span class="sxs-lookup"><span data-stu-id="031cc-165">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-166">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-167">Indica l'ID dell'utente di chi è il chiamante per conto.</span><span class="sxs-lookup"><span data-stu-id="031cc-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="031cc-168">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-170">int</span><span class="sxs-lookup"><span data-stu-id="031cc-170">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-171">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-172">ID dell'utente con cui si fa riferimento alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="031cc-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="031cc-173">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-175">int</span><span class="sxs-lookup"><span data-stu-id="031cc-175">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-176">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-177">ID del server front-end usato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="031cc-178">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-180">int</span><span class="sxs-lookup"><span data-stu-id="031cc-180">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-181">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-182">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="031cc-183">Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-185">int</span><span class="sxs-lookup"><span data-stu-id="031cc-185">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-186">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-187">Tipo di contenuto usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-187">Content type used in the session.</span></span> <span data-ttu-id="031cc-188">Per altre informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-190">int</span><span class="sxs-lookup"><span data-stu-id="031cc-190">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-191">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-192">Versione client usata da User1.</span><span class="sxs-lookup"><span data-stu-id="031cc-192">Client version used by User1.</span></span> <span data-ttu-id="031cc-193">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-195">int</span><span class="sxs-lookup"><span data-stu-id="031cc-195">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-196">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-197">Versione client usata da User2.</span><span class="sxs-lookup"><span data-stu-id="031cc-197">Client version used by User2.</span></span> <span data-ttu-id="031cc-198">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-200">int</span><span class="sxs-lookup"><span data-stu-id="031cc-200">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-201">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-202">Server perimetrale usato da User1.</span><span class="sxs-lookup"><span data-stu-id="031cc-202">Edge Server used by User1.</span></span> <span data-ttu-id="031cc-203">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-205">int</span><span class="sxs-lookup"><span data-stu-id="031cc-205">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-206">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-207">Edge Server usato da User2.</span><span class="sxs-lookup"><span data-stu-id="031cc-207">Edge Server used by User2.</span></span> <span data-ttu-id="031cc-208">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-210">po'</span><span class="sxs-lookup"><span data-stu-id="031cc-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-211">Se l'utente User1 ha effettuato l'accesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="031cc-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-213">po'</span><span class="sxs-lookup"><span data-stu-id="031cc-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-214">Se User2 è connesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="031cc-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-216">DateTime</span><span class="sxs-lookup"><span data-stu-id="031cc-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-217">L'ora della prima richiesta di invito.</span><span class="sxs-lookup"><span data-stu-id="031cc-217">The time of the first INVITE request.</span></span> <span data-ttu-id="031cc-218">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="031cc-219">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="031cc-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="031cc-220">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="031cc-221">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="031cc-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-223">DateTime</span><span class="sxs-lookup"><span data-stu-id="031cc-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-224">L'ora della risposta al primo messaggio di invito.</span><span class="sxs-lookup"><span data-stu-id="031cc-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="031cc-225">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="031cc-226">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="031cc-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-228">int</span><span class="sxs-lookup"><span data-stu-id="031cc-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-229">Codice di risposta SIP per l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="031cc-230">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="031cc-231">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="031cc-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-233">int</span><span class="sxs-lookup"><span data-stu-id="031cc-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-234">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="031cc-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-236">int</span><span class="sxs-lookup"><span data-stu-id="031cc-236">int</span></span></p></td>
<td><p><span data-ttu-id="031cc-237">Esterna</span><span class="sxs-lookup"><span data-stu-id="031cc-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="031cc-238">Chiama priorità.</span><span class="sxs-lookup"><span data-stu-id="031cc-238">Call priority.</span></span> <span data-ttu-id="031cc-239">Per altre informazioni, vedere la <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="031cc-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-241">int</span><span class="sxs-lookup"><span data-stu-id="031cc-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-242">Numero di messaggi inviati da User1 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-244">int</span><span class="sxs-lookup"><span data-stu-id="031cc-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-245">Numero di messaggi inviati da User2 durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-247">DateTime</span><span class="sxs-lookup"><span data-stu-id="031cc-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-248">Ora alla fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-250">int</span><span class="sxs-lookup"><span data-stu-id="031cc-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-251">Set di bit che indica il tipo di elemento multimediale della sessione.</span><span class="sxs-lookup"><span data-stu-id="031cc-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="031cc-252">Sono elencate le definizioni dei tipi:</span><span class="sxs-lookup"><span data-stu-id="031cc-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="031cc-253">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="031cc-253">IM</span></span></p></td>
<td><p><span data-ttu-id="031cc-254">1</span><span class="sxs-lookup"><span data-stu-id="031cc-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="031cc-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="031cc-256">2</span><span class="sxs-lookup"><span data-stu-id="031cc-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="031cc-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="031cc-258">4</span><span class="sxs-lookup"><span data-stu-id="031cc-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="031cc-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="031cc-260">8</span><span class="sxs-lookup"><span data-stu-id="031cc-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="031cc-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="031cc-262">16</span><span class="sxs-lookup"><span data-stu-id="031cc-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-263">VIDEO</span><span class="sxs-lookup"><span data-stu-id="031cc-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="031cc-264">32</span><span class="sxs-lookup"><span data-stu-id="031cc-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="031cc-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="031cc-266">64</span><span class="sxs-lookup"><span data-stu-id="031cc-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-268">smallint</span><span class="sxs-lookup"><span data-stu-id="031cc-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-269">Set di bit che indica gli attributi User1.</span><span class="sxs-lookup"><span data-stu-id="031cc-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="031cc-270">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="031cc-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="031cc-271">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="031cc-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-273">smallint</span><span class="sxs-lookup"><span data-stu-id="031cc-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-274">Set di bit che indica gli attributi User2.</span><span class="sxs-lookup"><span data-stu-id="031cc-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="031cc-275">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="031cc-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="031cc-276">0x01-integrato con il telefono desktop</span><span class="sxs-lookup"><span data-stu-id="031cc-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="031cc-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-278">smallint</span><span class="sxs-lookup"><span data-stu-id="031cc-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-279">Set di bit che indica gli attributi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="031cc-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="031cc-280">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="031cc-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="031cc-281">0x01-Riprova sessione</span><span class="sxs-lookup"><span data-stu-id="031cc-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="031cc-282">0x02-chiamata effettuata dall'agente per conto di un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="031cc-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="031cc-283"><strong>Elaborate</strong></span><span class="sxs-lookup"><span data-stu-id="031cc-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="031cc-284">po'</span><span class="sxs-lookup"><span data-stu-id="031cc-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="031cc-285">Per l'uso interno da parte del servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="031cc-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="031cc-286">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="031cc-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="031cc-287">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="031cc-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="031cc-288">Se più sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1, per un altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="031cc-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

