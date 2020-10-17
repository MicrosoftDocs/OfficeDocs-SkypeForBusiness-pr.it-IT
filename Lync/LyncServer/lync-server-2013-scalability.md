---
title: Scalabilità di Lync Server 2013
description: Lync Server 2013 scalabilità.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543792"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="807aa-103">Scalabilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="807aa-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="807aa-104">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="807aa-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="807aa-105">Lync Server è disponibile in due edizioni, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="807aa-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="807aa-106">Le diverse edizioni sono destinate principalmente a diverse dimensioni delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="807aa-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="807aa-107">Come illustrato nella tabella riportata di seguito, entrambe le edizioni supportano tutte le funzionalità in tutti i carichi di lavoro, ad eccezione della disponibilità elevata e del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="807aa-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="807aa-108">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="807aa-108">Feature</span></span></th>
<th><span data-ttu-id="807aa-109">Supporto in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="807aa-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="807aa-110">Supporto in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="807aa-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="807aa-111">Servizi di messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="807aa-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="807aa-112">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-113">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="807aa-114">Conferenze</span><span class="sxs-lookup"><span data-stu-id="807aa-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="807aa-115">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-116">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="807aa-117">Servizi A/V conferencing</span><span class="sxs-lookup"><span data-stu-id="807aa-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="807aa-118">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-119">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="807aa-120">Conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="807aa-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="807aa-121">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-122">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="807aa-123">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="807aa-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="807aa-124">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-125">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="807aa-126">Virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="807aa-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="807aa-127">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-128">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="807aa-129">Disponibilità elevata, failover e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="807aa-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="807aa-130">Sì</span><span class="sxs-lookup"><span data-stu-id="807aa-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="807aa-131">No</span><span class="sxs-lookup"><span data-stu-id="807aa-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

