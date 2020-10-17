---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509483"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="c4bde-102">tblADUpdates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4bde-102">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4bde-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c4bde-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c4bde-104">tblADUpdates contiene le modifiche ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4bde-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="c4bde-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="c4bde-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4bde-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="c4bde-106">Column</span></span></th>
<th><span data-ttu-id="c4bde-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="c4bde-107">Type</span></span></th>
<th><span data-ttu-id="c4bde-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4bde-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4bde-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c4bde-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c4bde-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-111">GUID di entità dell'oggetto modificato.</span><span class="sxs-lookup"><span data-stu-id="c4bde-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4bde-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c4bde-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="c4bde-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-114">Nome distinto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4bde-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4bde-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="c4bde-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="c4bde-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-117">True se viene modificato almeno un attributo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4bde-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4bde-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="c4bde-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="c4bde-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-120">True se l'appartenenza è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="c4bde-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4bde-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="c4bde-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="c4bde-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-123">Non utilizzata.</span><span class="sxs-lookup"><span data-stu-id="c4bde-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4bde-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c4bde-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="c4bde-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-126">True se l'oggetto è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="c4bde-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4bde-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c4bde-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="c4bde-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="c4bde-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c4bde-129">Timestamp dell'inserimento della riga.</span><span class="sxs-lookup"><span data-stu-id="c4bde-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

