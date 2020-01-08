---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="ee40a-102">tblADUpdates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee40a-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee40a-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ee40a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ee40a-104">tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.</span><span class="sxs-lookup"><span data-stu-id="ee40a-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="ee40a-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="ee40a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee40a-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="ee40a-106">Column</span></span></th>
<th><span data-ttu-id="ee40a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee40a-107">Type</span></span></th>
<th><span data-ttu-id="ee40a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee40a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee40a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ee40a-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ee40a-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="ee40a-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-111">GUID principale dell'oggetto modificato.</span><span class="sxs-lookup"><span data-stu-id="ee40a-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee40a-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="ee40a-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="ee40a-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-114">Nome distinto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ee40a-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee40a-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="ee40a-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="ee40a-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-117">True se almeno un attributo dell'oggetto è cambiato.</span><span class="sxs-lookup"><span data-stu-id="ee40a-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee40a-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="ee40a-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="ee40a-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-120">True se l'appartenenza è cambiata.</span><span class="sxs-lookup"><span data-stu-id="ee40a-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee40a-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="ee40a-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="ee40a-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-123">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ee40a-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee40a-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ee40a-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ee40a-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-126">True se l'oggetto è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="ee40a-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee40a-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ee40a-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="ee40a-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="ee40a-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="ee40a-129">Indicatore di data e ora di quando è stata inserita la riga.</span><span class="sxs-lookup"><span data-stu-id="ee40a-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

