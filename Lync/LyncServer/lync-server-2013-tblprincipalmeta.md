---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="42431-102">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42431-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42431-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="42431-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="42431-104">tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42431-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="42431-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="42431-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42431-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="42431-106">Column</span></span></th>
<th><span data-ttu-id="42431-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="42431-107">Type</span></span></th>
<th><span data-ttu-id="42431-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42431-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42431-109">prinID</span><span class="sxs-lookup"><span data-stu-id="42431-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="42431-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="42431-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42431-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="42431-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42431-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="42431-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="42431-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="42431-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="42431-114">True se le affiliazioni principali devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="42431-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42431-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="42431-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="42431-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="42431-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="42431-117">True se gli attributi Principal devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="42431-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42431-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="42431-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="42431-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="42431-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="42431-120">True se l'entità è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="42431-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42431-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="42431-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="42431-122">int</span><span class="sxs-lookup"><span data-stu-id="42431-122">int</span></span></p></td>
<td><p><span data-ttu-id="42431-123">Numero di tentativi di aggiornare l'oggetto Principal da servizi di dominio Active Directory che si sono verificati finora.</span><span class="sxs-lookup"><span data-stu-id="42431-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42431-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="42431-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="42431-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="42431-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="42431-126">Indicatore di data e ora dal tentativo più recente di aggiornare l'entità.</span><span class="sxs-lookup"><span data-stu-id="42431-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="42431-127">Può essere null se non è ancora stato tentato l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="42431-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42431-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="42431-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="42431-129">DateTime</span><span class="sxs-lookup"><span data-stu-id="42431-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="42431-130">Indicatore di data e ora per il successivo aggiornamento programmato.</span><span class="sxs-lookup"><span data-stu-id="42431-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="42431-131">Può essere null se non è stato programmato un ulteriore aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="42431-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="42431-132">Tasti</span><span class="sxs-lookup"><span data-stu-id="42431-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42431-133">Colonna</span><span class="sxs-lookup"><span data-stu-id="42431-133">Column</span></span></th>
<th><span data-ttu-id="42431-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42431-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42431-135">prinID</span><span class="sxs-lookup"><span data-stu-id="42431-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="42431-136">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="42431-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42431-137">prinID</span><span class="sxs-lookup"><span data-stu-id="42431-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="42431-138">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="42431-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

