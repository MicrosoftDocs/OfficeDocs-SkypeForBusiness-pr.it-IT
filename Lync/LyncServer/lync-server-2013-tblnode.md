---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547552"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="edbbd-103">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edbbd-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edbbd-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="edbbd-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="edbbd-105">tblNode contiene l'albero degli oggetti (con nodi categoria o chat room) come gestito nel pannello di controllo di Lync Server 2013 e nei cmdlet amministrativi.</span><span class="sxs-lookup"><span data-stu-id="edbbd-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="edbbd-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="edbbd-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edbbd-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="edbbd-107">Column</span></span></th>
<th><span data-ttu-id="edbbd-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="edbbd-108">Type</span></span></th>
<th><span data-ttu-id="edbbd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbbd-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="edbbd-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-112">ID nodo (numero univoco).</span><span class="sxs-lookup"><span data-stu-id="edbbd-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="edbbd-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="edbbd-114">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-115">GUID nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-116">parentID</span><span class="sxs-lookup"><span data-stu-id="edbbd-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-117">int</span><span class="sxs-lookup"><span data-stu-id="edbbd-117">int</span></span></p></td>
<td><p><span data-ttu-id="edbbd-p101">ID nodo del padre. Il nodo radice (con ID 1) contiene se stesso come padre.</span><span class="sxs-lookup"><span data-stu-id="edbbd-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="edbbd-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="edbbd-121">bit, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-122">True se il nodo è una categoria.</span><span class="sxs-lookup"><span data-stu-id="edbbd-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="edbbd-123">False se il nodo è una chat room.</span><span class="sxs-lookup"><span data-stu-id="edbbd-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="edbbd-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="edbbd-125">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-126">Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="edbbd-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="edbbd-128">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-129">Descrizione nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-130">invitare</span><span class="sxs-lookup"><span data-stu-id="edbbd-130">invite</span></span></p></td>
<td><p><span data-ttu-id="edbbd-131">po'</span><span class="sxs-lookup"><span data-stu-id="edbbd-131">bit</span></span></p></td>
<td><p><span data-ttu-id="edbbd-132">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="edbbd-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-133">True se gli inviti sono attivi.</span><span class="sxs-lookup"><span data-stu-id="edbbd-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="edbbd-134">False se gli inviti sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="edbbd-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="edbbd-135">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="edbbd-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-136">False se gli inviti sono disattivati (la categoria padre viene ignorata).</span><span class="sxs-lookup"><span data-stu-id="edbbd-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="edbbd-137">Null se l'impostazione degli inviti viene ereditata dalla categoria padre.</span><span class="sxs-lookup"><span data-stu-id="edbbd-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-138">registrato</span><span class="sxs-lookup"><span data-stu-id="edbbd-138">logged</span></span></p></td>
<td><p><span data-ttu-id="edbbd-139">po'</span><span class="sxs-lookup"><span data-stu-id="edbbd-139">bit</span></span></p></td>
<td><p><span data-ttu-id="edbbd-140">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="edbbd-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-141">True se la cronologia della chat è attiva.</span><span class="sxs-lookup"><span data-stu-id="edbbd-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="edbbd-142">False se la cronologia della chat è inattiva.</span><span class="sxs-lookup"><span data-stu-id="edbbd-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="edbbd-143">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="edbbd-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-144">Null.</span><span class="sxs-lookup"><span data-stu-id="edbbd-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-145">filePost</span><span class="sxs-lookup"><span data-stu-id="edbbd-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="edbbd-146">po'</span><span class="sxs-lookup"><span data-stu-id="edbbd-146">bit</span></span></p></td>
<td><p><span data-ttu-id="edbbd-147">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="edbbd-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-148">True se i caricamenti di file sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="edbbd-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="edbbd-149">False se i caricamenti di file non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="edbbd-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="edbbd-150">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="edbbd-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-151">Null.</span><span class="sxs-lookup"><span data-stu-id="edbbd-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-152">disabilitati</span><span class="sxs-lookup"><span data-stu-id="edbbd-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="edbbd-153">bit, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-p102">True se la chat room è disabilitata. Si applica solo alle chat room. False per le categorie.</span><span class="sxs-lookup"><span data-stu-id="edbbd-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-157">comportamento</span><span class="sxs-lookup"><span data-stu-id="edbbd-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="edbbd-158">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-159">Comportamento (cercato nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="edbbd-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-160">4: Normale (chat room normali)</span><span class="sxs-lookup"><span data-stu-id="edbbd-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="edbbd-161">5: Auditorium (chat room in modalità auditorium, solo i relatori possono contribuire)</span><span class="sxs-lookup"><span data-stu-id="edbbd-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="edbbd-162">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="edbbd-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-163">visibilità</span><span class="sxs-lookup"><span data-stu-id="edbbd-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="edbbd-164">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-165">Visibilità (cercata nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="edbbd-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="edbbd-166">2: Privato</span><span class="sxs-lookup"><span data-stu-id="edbbd-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="edbbd-167">3: Con ambito</span><span class="sxs-lookup"><span data-stu-id="edbbd-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="edbbd-168">6: Aperto</span><span class="sxs-lookup"><span data-stu-id="edbbd-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="edbbd-169">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="edbbd-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-170">siopID</span><span class="sxs-lookup"><span data-stu-id="edbbd-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-171">GUID</span><span class="sxs-lookup"><span data-stu-id="edbbd-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-p103">GUID del componente aggiuntivo, se alla chat room è associato un componente aggiuntivo. Le categorie non hanno componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="edbbd-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="edbbd-174">Le informazioni relative al componente aggiuntivo vengono cercate nella tabella SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="edbbd-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="edbbd-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="edbbd-176">int, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-177">ID dell'entità che ha creato questo nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="edbbd-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="edbbd-179">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-180">Indicatore di data e ora della creazione del nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="edbbd-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="edbbd-182">int, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-183">ID dell'entità che ha eseguito l'ultimo aggiornamento del nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="edbbd-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="edbbd-185">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="edbbd-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="edbbd-186">Indicatore di data e ora dell'ultimo aggiornamento del nodo.</span><span class="sxs-lookup"><span data-stu-id="edbbd-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="edbbd-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="edbbd-188">datetime</span><span class="sxs-lookup"><span data-stu-id="edbbd-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="edbbd-p104">Ora dell'ultima operazione di eliminazione (rimozione degli ambiti dalla tabella tblScopedPrincipal e dei ruoli dalla tabella tblPrincipalRole) che ha interessato il nodo. Utilizzata dal meccanismo di aggiornamento della cache interna del servizio Chat.</span><span class="sxs-lookup"><span data-stu-id="edbbd-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="edbbd-191">Chiavi</span><span class="sxs-lookup"><span data-stu-id="edbbd-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edbbd-192">Colonna</span><span class="sxs-lookup"><span data-stu-id="edbbd-192">Column</span></span></th>
<th><span data-ttu-id="edbbd-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbbd-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="edbbd-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-195">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="edbbd-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-196">comportamento</span><span class="sxs-lookup"><span data-stu-id="edbbd-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="edbbd-197">Chiave esterna con ricerca nella tabella tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="edbbd-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-198">visibilità</span><span class="sxs-lookup"><span data-stu-id="edbbd-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="edbbd-199">Chiave esterna con ricerca nella tabella tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="edbbd-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbbd-200">parentID</span><span class="sxs-lookup"><span data-stu-id="edbbd-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-201">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="edbbd-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbbd-202">siopID</span><span class="sxs-lookup"><span data-stu-id="edbbd-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="edbbd-203">Chiave esterna con ricerca nella tabella tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="edbbd-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

