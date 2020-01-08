---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="3f8d7-102">tblPrincipalInvites in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f8d7-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f8d7-103">_**Argomento Ultima modifica:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="3f8d7-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="3f8d7-104">tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="3f8d7-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="3f8d7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f8d7-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="3f8d7-106">Column</span></span></th>
<th><span data-ttu-id="3f8d7-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f8d7-107">Type</span></span></th>
<th><span data-ttu-id="3f8d7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f8d7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f8d7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3f8d7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="3f8d7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f8d7-112">invID</span><span class="sxs-lookup"><span data-stu-id="3f8d7-112">invID</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="3f8d7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-114">Numero sequenziale univoco (per ID entità) generato dalla tabella tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f8d7-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="3f8d7-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="3f8d7-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-117">ID nodo (solo chat room).</span><span class="sxs-lookup"><span data-stu-id="3f8d7-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f8d7-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="3f8d7-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="3f8d7-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-120">Ora della creazione.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3f8d7-121">Tasti</span><span class="sxs-lookup"><span data-stu-id="3f8d7-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f8d7-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="3f8d7-122">Column</span></span></th>
<th><span data-ttu-id="3f8d7-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f8d7-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f8d7-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="3f8d7-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f8d7-126">prinID</span><span class="sxs-lookup"><span data-stu-id="3f8d7-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-127">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f8d7-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="3f8d7-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="3f8d7-129">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="3f8d7-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

