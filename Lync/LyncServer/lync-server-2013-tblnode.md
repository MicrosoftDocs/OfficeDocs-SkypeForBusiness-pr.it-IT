---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: 81a57d54663b1adf837a4ca38896dd7da3eff883
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="1dcbb-102">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcbb-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dcbb-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1dcbb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1dcbb-104">tblNode contiene l'albero degli oggetti (con nodi categoria o chat room) come gestito nel pannello di controllo di Lync Server 2013 e nei cmdlet amministrativi.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="1dcbb-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="1dcbb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dcbb-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="1dcbb-106">Column</span></span></th>
<th><span data-ttu-id="1dcbb-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1dcbb-107">Type</span></span></th>
<th><span data-ttu-id="1dcbb-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dcbb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-111">ID nodo (numero univoco).</span><span class="sxs-lookup"><span data-stu-id="1dcbb-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="1dcbb-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-114">GUID nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-115">parentID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-116">int</span><span class="sxs-lookup"><span data-stu-id="1dcbb-116">int</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-p101">ID nodo del padre. Il nodo radice (con ID 1) contiene se stesso come padre.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="1dcbb-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-121">True se il nodo è una categoria.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="1dcbb-122">False se il nodo è una chat room.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="1dcbb-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-124">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-125">Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="1dcbb-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-127">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-128">Descrizione nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-129">invitare</span><span class="sxs-lookup"><span data-stu-id="1dcbb-129">invite</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-130">po'</span><span class="sxs-lookup"><span data-stu-id="1dcbb-130">bit</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-131">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-132">True se gli inviti sono attivi.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-133">False se gli inviti sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="1dcbb-134">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-135">False se gli inviti sono disattivati (la categoria padre viene ignorata).</span><span class="sxs-lookup"><span data-stu-id="1dcbb-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-136">Null se l'impostazione degli inviti viene ereditata dalla categoria padre.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-137">registrato</span><span class="sxs-lookup"><span data-stu-id="1dcbb-137">logged</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-138">po'</span><span class="sxs-lookup"><span data-stu-id="1dcbb-138">bit</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-139">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-140">True se la cronologia della chat è attiva.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-141">False se la cronologia della chat è inattiva.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="1dcbb-142">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-143">Null.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-144">filePost</span><span class="sxs-lookup"><span data-stu-id="1dcbb-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-145">po'</span><span class="sxs-lookup"><span data-stu-id="1dcbb-145">bit</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-146">Per le categorie:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-147">True se i caricamenti di file sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-148">False se i caricamenti di file non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="1dcbb-149">Per le chat room:</span><span class="sxs-lookup"><span data-stu-id="1dcbb-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-150">Null.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-151">disabili</span><span class="sxs-lookup"><span data-stu-id="1dcbb-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-p102">True se la chat room è disabilitata. Si applica solo alle chat room. False per le categorie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-156">comportamento</span><span class="sxs-lookup"><span data-stu-id="1dcbb-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-157">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-158">Comportamento (cercato nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="1dcbb-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-159">4: Normale (chat room normali)</span><span class="sxs-lookup"><span data-stu-id="1dcbb-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-160">5: Auditorium (chat room in modalità auditorium, solo i relatori possono contribuire)</span><span class="sxs-lookup"><span data-stu-id="1dcbb-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="1dcbb-161">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-162">visibilità</span><span class="sxs-lookup"><span data-stu-id="1dcbb-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-163">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-164">Visibilità (cercata nella tabella EnumValue):</span><span class="sxs-lookup"><span data-stu-id="1dcbb-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcbb-165">2: Privato</span><span class="sxs-lookup"><span data-stu-id="1dcbb-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-166">3: Con ambito</span><span class="sxs-lookup"><span data-stu-id="1dcbb-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="1dcbb-167">6: Aperto</span><span class="sxs-lookup"><span data-stu-id="1dcbb-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="1dcbb-168">Si applica solo alle chat room.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-169">siopID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-170">GUID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-p103">GUID del componente aggiuntivo, se alla chat room è associato un componente aggiuntivo. Le categorie non hanno componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="1dcbb-173">Le informazioni relative al componente aggiuntivo vengono cercate nella tabella SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="1dcbb-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-175">int, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-176">ID dell'entità che ha creato questo nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="1dcbb-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-178">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-179">Indicatore di data e ora della creazione del nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1dcbb-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-181">int, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-182">ID dell'entità che ha eseguito l'ultimo aggiornamento del nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="1dcbb-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-184">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="1dcbb-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-185">Indicatore di data e ora dell'ultimo aggiornamento del nodo.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="1dcbb-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-187">datetime</span><span class="sxs-lookup"><span data-stu-id="1dcbb-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-p104">Ora dell'ultima operazione di eliminazione (rimozione degli ambiti dalla tabella tblScopedPrincipal e dei ruoli dalla tabella tblPrincipalRole) che ha interessato il nodo. Utilizzata dal meccanismo di aggiornamento della cache interna del servizio Chat.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1dcbb-190">Chiavi</span><span class="sxs-lookup"><span data-stu-id="1dcbb-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dcbb-191">Colonna</span><span class="sxs-lookup"><span data-stu-id="1dcbb-191">Column</span></span></th>
<th><span data-ttu-id="1dcbb-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dcbb-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-194">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-195">comportamento</span><span class="sxs-lookup"><span data-stu-id="1dcbb-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-196">Chiave esterna con ricerca nella tabella tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-197">visibilità</span><span class="sxs-lookup"><span data-stu-id="1dcbb-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-198">Chiave esterna con ricerca nella tabella tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcbb-199">parentID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-200">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcbb-201">siopID</span><span class="sxs-lookup"><span data-stu-id="1dcbb-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="1dcbb-202">Chiave esterna con ricerca nella tabella tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

