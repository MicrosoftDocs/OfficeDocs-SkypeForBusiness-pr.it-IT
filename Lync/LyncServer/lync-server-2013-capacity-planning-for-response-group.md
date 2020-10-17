---
title: 'Lync Server 2013: pianificazione della capacità per Response Group'
description: 'Lync Server 2013: pianificazione della capacità per Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544432"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="f840f-103">Pianificazione della capacità per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f840f-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f840f-104">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f840f-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f840f-105">Nella tabella seguente viene descritto il modello utente di Response Group che è possibile utilizzare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="f840f-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f840f-p101">I numeri nella tabella seguente presuppongono l'utilizzo di file Wave (con estensione wav) a 16 bit, 16 kHz, mono per tutti i file audio Response Group. Se si utilizzano altri formati, ad esempio Windows Media Audio ( con estensione wma), i numeri possono variare.</span><span class="sxs-lookup"><span data-stu-id="f840f-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f840f-108">Tenere presente che, per la pianificazione della capacità per il ripristino di emergenza, ogni pool di un pool accoppiato deve poter gestire i carichi di lavoro per tutti i Response Group in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="f840f-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="f840f-109">Modello utente Response Group</span><span class="sxs-lookup"><span data-stu-id="f840f-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f840f-110">Metrica</span><span class="sxs-lookup"><span data-stu-id="f840f-110">Metric</span></span></th>
<th><span data-ttu-id="f840f-111">Per pool Enterprise Edition (con 8 Front End Server)</span><span class="sxs-lookup"><span data-stu-id="f840f-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="f840f-112">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f840f-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f840f-113">Chiamate in entrata al secondo</span><span class="sxs-lookup"><span data-stu-id="f840f-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="f840f-114">16 </span><span class="sxs-lookup"><span data-stu-id="f840f-114">16</span></span></p></td>
<td><p><span data-ttu-id="f840f-115">2</span><span class="sxs-lookup"><span data-stu-id="f840f-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f840f-116">Chiamate simultanee connesse a IVR o MoH</span><span class="sxs-lookup"><span data-stu-id="f840f-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="f840f-117">480</span><span class="sxs-lookup"><span data-stu-id="f840f-117">480</span></span></p></td>
<td><p><span data-ttu-id="f840f-118">60</span><span class="sxs-lookup"><span data-stu-id="f840f-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f840f-119">Sessioni anonime simultanee (senza messaggistica istantanea)</span><span class="sxs-lookup"><span data-stu-id="f840f-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="f840f-120">224</span><span class="sxs-lookup"><span data-stu-id="f840f-120">224</span></span></p></td>
<td><p><span data-ttu-id="f840f-121">28</span><span class="sxs-lookup"><span data-stu-id="f840f-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f840f-122">Sessioni anonime simultanee (con messaggistica istantanea)</span><span class="sxs-lookup"><span data-stu-id="f840f-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="f840f-123">64</span><span class="sxs-lookup"><span data-stu-id="f840f-123">64</span></span></p></td>
<td><p><span data-ttu-id="f840f-124">8 </span><span class="sxs-lookup"><span data-stu-id="f840f-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f840f-125">Agenti attivi (formali e informali)</span><span class="sxs-lookup"><span data-stu-id="f840f-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="f840f-126">1200</span><span class="sxs-lookup"><span data-stu-id="f840f-126">1200</span></span></p></td>
<td><p><span data-ttu-id="f840f-127">1200</span><span class="sxs-lookup"><span data-stu-id="f840f-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f840f-128">Numero di gruppi di risposta</span><span class="sxs-lookup"><span data-stu-id="f840f-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="f840f-129">400</span><span class="sxs-lookup"><span data-stu-id="f840f-129">400</span></span></p></td>
<td><p><span data-ttu-id="f840f-130">400</span><span class="sxs-lookup"><span data-stu-id="f840f-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f840f-131">Numero di gruppi IVR (utilizzo del riconoscimento vocale)</span><span class="sxs-lookup"><span data-stu-id="f840f-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="f840f-132">200</span><span class="sxs-lookup"><span data-stu-id="f840f-132">200</span></span></p></td>
<td><p><span data-ttu-id="f840f-133">200</span><span class="sxs-lookup"><span data-stu-id="f840f-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

