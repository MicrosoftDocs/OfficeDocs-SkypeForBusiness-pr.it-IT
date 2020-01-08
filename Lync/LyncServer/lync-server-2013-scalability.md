---
title: 'Lync Server 2013: Scalabilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="f47cb-102">Scalabilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f47cb-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f47cb-103">_**Argomento Ultima modifica:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f47cb-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f47cb-104">Lync Server è disponibile in due edizioni, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f47cb-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="f47cb-105">Le diverse edizioni sono destinate principalmente alle diverse dimensioni delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f47cb-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="f47cb-106">Come illustrato nella tabella seguente, entrambe le edizioni supportano tutte le funzionalità in tutti i carichi di lavoro, ad eccezione della disponibilità elevata e del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f47cb-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f47cb-107">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="f47cb-107">Feature</span></span></th>
<th><span data-ttu-id="f47cb-108">Supportato in Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="f47cb-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="f47cb-109">Supportato in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f47cb-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f47cb-110">Messaggistica istantanea (IM) e presenza</span><span class="sxs-lookup"><span data-stu-id="f47cb-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="f47cb-111">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-112">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f47cb-113">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="f47cb-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="f47cb-114">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-115">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f47cb-116">Servizi di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="f47cb-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="f47cb-117">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-118">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f47cb-119">Chiamate in conferenza</span><span class="sxs-lookup"><span data-stu-id="f47cb-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f47cb-120">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-121">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f47cb-122">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="f47cb-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f47cb-123">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-124">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f47cb-125">La virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="f47cb-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="f47cb-126">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-127">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f47cb-128">Disponibilità elevata, failover e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="f47cb-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="f47cb-129">Sì</span><span class="sxs-lookup"><span data-stu-id="f47cb-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="f47cb-130">No</span><span class="sxs-lookup"><span data-stu-id="f47cb-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

