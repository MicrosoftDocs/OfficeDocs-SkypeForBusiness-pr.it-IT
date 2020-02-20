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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="2f742-102">Scalabilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f742-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f742-103">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2f742-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2f742-104">Lync Server è disponibile in due edizioni, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2f742-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="2f742-105">Le diverse edizioni sono destinate principalmente a diverse dimensioni delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2f742-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="2f742-106">Come illustrato nella tabella riportata di seguito, entrambe le edizioni supportano tutte le funzionalità in tutti i carichi di lavoro, ad eccezione della disponibilità elevata e del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2f742-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f742-107">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="2f742-107">Feature</span></span></th>
<th><span data-ttu-id="2f742-108">Supporto in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2f742-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="2f742-109">Supporto in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2f742-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f742-110">Servizi di messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="2f742-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="2f742-111">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-112">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f742-113">Conferenza</span><span class="sxs-lookup"><span data-stu-id="2f742-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="2f742-114">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-115">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f742-116">Servizi A/V conferencing</span><span class="sxs-lookup"><span data-stu-id="2f742-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="2f742-117">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-118">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f742-119">Conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="2f742-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="2f742-120">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-121">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f742-122">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="2f742-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="2f742-123">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-124">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f742-125">Virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="2f742-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="2f742-126">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-127">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f742-128">Disponibilità elevata, failover e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="2f742-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="2f742-129">Sì</span><span class="sxs-lookup"><span data-stu-id="2f742-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="2f742-130">No</span><span class="sxs-lookup"><span data-stu-id="2f742-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

