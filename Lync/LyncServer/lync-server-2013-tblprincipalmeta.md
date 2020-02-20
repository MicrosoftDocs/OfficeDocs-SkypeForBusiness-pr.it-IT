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
ms.openlocfilehash: 5a1b4161a04b3107e3aff7b55ab82840ac6680e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="06329-102">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06329-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06329-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="06329-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="06329-104">tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06329-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="06329-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="06329-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06329-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="06329-106">Column</span></span></th>
<th><span data-ttu-id="06329-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="06329-107">Type</span></span></th>
<th><span data-ttu-id="06329-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06329-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06329-109">prinID</span><span class="sxs-lookup"><span data-stu-id="06329-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="06329-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="06329-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="06329-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="06329-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06329-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="06329-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="06329-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="06329-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="06329-114">True se le affiliazioni delle entità devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="06329-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06329-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="06329-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="06329-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="06329-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="06329-117">True se gli attributi delle entità devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="06329-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06329-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="06329-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="06329-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="06329-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="06329-120">True se l'entità è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="06329-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06329-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="06329-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="06329-122">int</span><span class="sxs-lookup"><span data-stu-id="06329-122">int</span></span></p></td>
<td><p><span data-ttu-id="06329-123">Numero di tentativi di aggiornamento dell'entità eseguiti fino a questo momento da Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06329-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06329-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="06329-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="06329-125">datetime</span><span class="sxs-lookup"><span data-stu-id="06329-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="06329-p101">Indicatore di data e ora del tentativo più recente di aggiornamento dell'entità. Può essere Null se non è ancora stato eseguito alcun tentativo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="06329-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06329-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="06329-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="06329-129">datetime</span><span class="sxs-lookup"><span data-stu-id="06329-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="06329-p102">Indicatore di data e ora del successivo aggiornamento pianificato. Può essere Null se non sono stati pianificati ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="06329-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="06329-132">Chiavi</span><span class="sxs-lookup"><span data-stu-id="06329-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06329-133">Colonna</span><span class="sxs-lookup"><span data-stu-id="06329-133">Column</span></span></th>
<th><span data-ttu-id="06329-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06329-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06329-135">prinID</span><span class="sxs-lookup"><span data-stu-id="06329-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="06329-136">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="06329-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06329-137">prinID</span><span class="sxs-lookup"><span data-stu-id="06329-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="06329-138">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="06329-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

