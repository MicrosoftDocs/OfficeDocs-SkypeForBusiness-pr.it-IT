---
title: Scalabilità di Lync Server 2013
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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="e4095-102">Scalabilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4095-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4095-103">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e4095-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e4095-104">Lync Server è disponibile in due edizioni, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4095-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="e4095-105">Le diverse edizioni sono destinate principalmente a diverse dimensioni delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e4095-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="e4095-106">Come illustrato nella tabella riportata di seguito, entrambe le edizioni supportano tutte le funzionalità in tutti i carichi di lavoro, ad eccezione della disponibilità elevata e del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e4095-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4095-107">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="e4095-107">Feature</span></span></th>
<th><span data-ttu-id="e4095-108">Supporto in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e4095-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="e4095-109">Supporto in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e4095-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4095-110">Servizi di messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="e4095-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="e4095-111">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-112">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4095-113">Conferenza</span><span class="sxs-lookup"><span data-stu-id="e4095-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="e4095-114">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-115">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4095-116">Servizi A/V conferencing</span><span class="sxs-lookup"><span data-stu-id="e4095-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="e4095-117">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-118">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4095-119">Conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="e4095-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="e4095-120">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-121">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4095-122">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e4095-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="e4095-123">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-124">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4095-125">Virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="e4095-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="e4095-126">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-127">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4095-128">Disponibilità elevata, failover e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="e4095-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="e4095-129">Sì</span><span class="sxs-lookup"><span data-stu-id="e4095-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4095-130">No</span><span class="sxs-lookup"><span data-stu-id="e4095-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

