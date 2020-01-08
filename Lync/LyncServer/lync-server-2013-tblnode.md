---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="e855b-102">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e855b-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e855b-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e855b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e855b-104">tblNode contiene l'albero di oggetti (con nodi Category o chat room) come gestito nel pannello di controllo di Lync Server 2013 e nei cmdlet amministrativi.</span><span class="sxs-lookup"><span data-stu-id="e855b-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="e855b-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="e855b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e855b-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e855b-106">Column</span></span></th>
<th><span data-ttu-id="e855b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e855b-107">Type</span></span></th>
<th><span data-ttu-id="e855b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e855b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e855b-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="e855b-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e855b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e855b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-111">ID nodo (numero univoco).</span><span class="sxs-lookup"><span data-stu-id="e855b-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="e855b-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="e855b-113">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="e855b-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-114">GUID del nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-115">parentID</span><span class="sxs-lookup"><span data-stu-id="e855b-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="e855b-116">int</span><span class="sxs-lookup"><span data-stu-id="e855b-116">int</span></span></p></td>
<td><p><span data-ttu-id="e855b-117">ID nodo dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e855b-117">Node ID of parent.</span></span> <span data-ttu-id="e855b-118">Il nodo radice (con ID 1) si include anche come padre.</span><span class="sxs-lookup"><span data-stu-id="e855b-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="e855b-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="e855b-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e855b-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-121">True se il nodo è una categoria.</span><span class="sxs-lookup"><span data-stu-id="e855b-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="e855b-122">False se il nodo è una chat room.</span><span class="sxs-lookup"><span data-stu-id="e855b-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="e855b-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="e855b-124">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="e855b-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-125">Nome del nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="e855b-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="e855b-127">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="e855b-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-128">Descrizione del nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-129">invitare</span><span class="sxs-lookup"><span data-stu-id="e855b-129">invite</span></span></p></td>
<td><p><span data-ttu-id="e855b-130">po'</span><span class="sxs-lookup"><span data-stu-id="e855b-130">bit</span></span></p></td>
<td><p><span data-ttu-id="e855b-131">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="e855b-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-132">True se gli inviti sono attivati.</span><span class="sxs-lookup"><span data-stu-id="e855b-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="e855b-133">False se gli inviti sono spenti.</span><span class="sxs-lookup"><span data-stu-id="e855b-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="e855b-134">Per le camere:</span><span class="sxs-lookup"><span data-stu-id="e855b-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-135">False se gli inviti sono disattivati (esegue l'override della categoria padre).</span><span class="sxs-lookup"><span data-stu-id="e855b-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="e855b-136">Null se l'impostazione invita viene ereditata dalla categoria padre.</span><span class="sxs-lookup"><span data-stu-id="e855b-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-137">connessi</span><span class="sxs-lookup"><span data-stu-id="e855b-137">logged</span></span></p></td>
<td><p><span data-ttu-id="e855b-138">po'</span><span class="sxs-lookup"><span data-stu-id="e855b-138">bit</span></span></p></td>
<td><p><span data-ttu-id="e855b-139">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="e855b-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-140">True se la cronologia chat è attivata.</span><span class="sxs-lookup"><span data-stu-id="e855b-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="e855b-141">False se la cronologia chat è disinserita.</span><span class="sxs-lookup"><span data-stu-id="e855b-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="e855b-142">Per le camere:</span><span class="sxs-lookup"><span data-stu-id="e855b-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-143">Null.</span><span class="sxs-lookup"><span data-stu-id="e855b-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-144">filePost</span><span class="sxs-lookup"><span data-stu-id="e855b-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="e855b-145">po'</span><span class="sxs-lookup"><span data-stu-id="e855b-145">bit</span></span></p></td>
<td><p><span data-ttu-id="e855b-146">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="e855b-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-147">True se gli upload di file sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e855b-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="e855b-148">False se gli upload di file non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e855b-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="e855b-149">Per le camere:</span><span class="sxs-lookup"><span data-stu-id="e855b-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-150">Null.</span><span class="sxs-lookup"><span data-stu-id="e855b-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-151">disabilitato</span><span class="sxs-lookup"><span data-stu-id="e855b-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="e855b-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e855b-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-153">True se la chat room è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e855b-153">True if the chat room is disabled.</span></span> <span data-ttu-id="e855b-154">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="e855b-154">Applies only to chat rooms.</span></span> <span data-ttu-id="e855b-155">(False per le categorie)</span><span class="sxs-lookup"><span data-stu-id="e855b-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-156">comportamento</span><span class="sxs-lookup"><span data-stu-id="e855b-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="e855b-157">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="e855b-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-158">Comportamento (ricercato nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="e855b-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-159">4: normale (normale chat room).</span><span class="sxs-lookup"><span data-stu-id="e855b-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="e855b-160">5: Auditorium (auditorium chat room, solo i relatori possono collaborare).</span><span class="sxs-lookup"><span data-stu-id="e855b-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="e855b-161">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="e855b-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-162">visibilità</span><span class="sxs-lookup"><span data-stu-id="e855b-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="e855b-163">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="e855b-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-164">Visibilità (ricercata nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="e855b-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="e855b-165">2: privato</span><span class="sxs-lookup"><span data-stu-id="e855b-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="e855b-166">3: ambito</span><span class="sxs-lookup"><span data-stu-id="e855b-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="e855b-167">6: aprire</span><span class="sxs-lookup"><span data-stu-id="e855b-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="e855b-168">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="e855b-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-169">siopID</span><span class="sxs-lookup"><span data-stu-id="e855b-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="e855b-170">GUID</span><span class="sxs-lookup"><span data-stu-id="e855b-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="e855b-171">GUID del componente aggiuntivo se un componente aggiuntivo è associato a questa chat room.</span><span class="sxs-lookup"><span data-stu-id="e855b-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="e855b-172">(Le categorie non hanno componenti aggiuntivi)</span><span class="sxs-lookup"><span data-stu-id="e855b-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="e855b-173">Le informazioni del componente aggiuntivo sono ricercate nella tabella SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="e855b-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="e855b-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="e855b-175">int, not null</span><span class="sxs-lookup"><span data-stu-id="e855b-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-176">ID dell'entità che ha creato questo nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="e855b-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="e855b-178">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="e855b-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-179">Indicatore di data e ora della creazione di nodi.</span><span class="sxs-lookup"><span data-stu-id="e855b-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e855b-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="e855b-181">int, not null</span><span class="sxs-lookup"><span data-stu-id="e855b-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-182">ID dell'entità che ha eseguito l'aggiornamento più recente di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="e855b-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="e855b-184">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="e855b-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e855b-185">Indicatore di data e ora dell'ultimo aggiornamento di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="e855b-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="e855b-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="e855b-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="e855b-188">Ora dell'ultima operazione di eliminazione dei ripulimenti (rimozione degli ambiti da tabella tblScopedPrincipal e ruoli della tabella tblPrincipalRole) che hanno interessato questo nodo.</span><span class="sxs-lookup"><span data-stu-id="e855b-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="e855b-189">Viene usato dal meccanismo di aggiornamento della cache interno del servizio chat.</span><span class="sxs-lookup"><span data-stu-id="e855b-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e855b-190">Tasti</span><span class="sxs-lookup"><span data-stu-id="e855b-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e855b-191">Colonna</span><span class="sxs-lookup"><span data-stu-id="e855b-191">Column</span></span></th>
<th><span data-ttu-id="e855b-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e855b-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e855b-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="e855b-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e855b-194">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="e855b-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-195">comportamento</span><span class="sxs-lookup"><span data-stu-id="e855b-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="e855b-196">Chiave esterna con ricerca nella tabella tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="e855b-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-197">visibilità</span><span class="sxs-lookup"><span data-stu-id="e855b-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="e855b-198">Chiave esterna con ricerca nella tabella tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="e855b-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e855b-199">parentID</span><span class="sxs-lookup"><span data-stu-id="e855b-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="e855b-200">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="e855b-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e855b-201">siopID</span><span class="sxs-lookup"><span data-stu-id="e855b-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="e855b-202">Chiave esterna con ricerca nella tabella tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="e855b-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

