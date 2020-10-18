---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
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
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573642"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="3679f-103">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3679f-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3679f-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3679f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="3679f-105">tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3679f-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="3679f-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3679f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3679f-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="3679f-107">Column</span></span></th>
<th><span data-ttu-id="3679f-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="3679f-108">Type</span></span></th>
<th><span data-ttu-id="3679f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3679f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3679f-110">prinID</span><span class="sxs-lookup"><span data-stu-id="3679f-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="3679f-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="3679f-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3679f-112">ID entità.</span><span class="sxs-lookup"><span data-stu-id="3679f-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3679f-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="3679f-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="3679f-114">bit, non null</span><span class="sxs-lookup"><span data-stu-id="3679f-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3679f-115">True se le affiliazioni delle entità devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="3679f-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3679f-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="3679f-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="3679f-117">bit, non null</span><span class="sxs-lookup"><span data-stu-id="3679f-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3679f-118">True se gli attributi delle entità devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="3679f-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3679f-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3679f-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="3679f-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="3679f-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3679f-121">True se l'entità è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="3679f-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3679f-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="3679f-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="3679f-123">int</span><span class="sxs-lookup"><span data-stu-id="3679f-123">int</span></span></p></td>
<td><p><span data-ttu-id="3679f-124">Numero di tentativi di aggiornamento dell'entità eseguiti fino a questo momento da Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3679f-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3679f-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="3679f-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="3679f-126">datetime</span><span class="sxs-lookup"><span data-stu-id="3679f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="3679f-p101">Indicatore di data e ora del tentativo più recente di aggiornamento dell'entità. Può essere Null se non è ancora stato eseguito alcun tentativo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3679f-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3679f-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="3679f-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="3679f-130">datetime</span><span class="sxs-lookup"><span data-stu-id="3679f-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="3679f-p102">Indicatore di data e ora del successivo aggiornamento pianificato. Può essere Null se non sono stati pianificati ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="3679f-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3679f-133">Chiavi</span><span class="sxs-lookup"><span data-stu-id="3679f-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3679f-134">Colonna</span><span class="sxs-lookup"><span data-stu-id="3679f-134">Column</span></span></th>
<th><span data-ttu-id="3679f-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3679f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3679f-136">prinID</span><span class="sxs-lookup"><span data-stu-id="3679f-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="3679f-137">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3679f-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3679f-138">prinID</span><span class="sxs-lookup"><span data-stu-id="3679f-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="3679f-139">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="3679f-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

