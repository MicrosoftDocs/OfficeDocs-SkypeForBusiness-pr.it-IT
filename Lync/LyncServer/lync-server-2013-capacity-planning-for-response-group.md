---
title: 'Lync Server 2013: Pianificazione della capacità per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="af6f3-102">Pianificazione della capacità per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af6f3-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af6f3-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="af6f3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="af6f3-104">La tabella seguente descrive il modello di Response Group User che puoi usare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="af6f3-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af6f3-105">I numeri nella tabella seguente presuppongono l'uso di file wave 16 kHz, mono, a 16 bit (WAV) per tutti i file audio del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="af6f3-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="af6f3-106">Se si usano altri formati di file, ad esempio Windows Media Audio (WMA), i numeri possono variare.</span><span class="sxs-lookup"><span data-stu-id="af6f3-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af6f3-107">Tieni presente che per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per tutti i gruppi di risposta in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="af6f3-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="af6f3-108">Modello di Response Group User</span><span class="sxs-lookup"><span data-stu-id="af6f3-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af6f3-109">Metrica</span><span class="sxs-lookup"><span data-stu-id="af6f3-109">Metric</span></span></th>
<th><span data-ttu-id="af6f3-110">Per pool Enterprise Edition (con 8 server front-end)</span><span class="sxs-lookup"><span data-stu-id="af6f3-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="af6f3-111">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="af6f3-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af6f3-112">Chiamate in arrivo al secondo</span><span class="sxs-lookup"><span data-stu-id="af6f3-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="af6f3-113">16</span><span class="sxs-lookup"><span data-stu-id="af6f3-113">16</span></span></p></td>
<td><p><span data-ttu-id="af6f3-114">2</span><span class="sxs-lookup"><span data-stu-id="af6f3-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6f3-115">Chiamate simultanee connesse a IVR o MoH</span><span class="sxs-lookup"><span data-stu-id="af6f3-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="af6f3-116">480</span><span class="sxs-lookup"><span data-stu-id="af6f3-116">480</span></span></p></td>
<td><p><span data-ttu-id="af6f3-117">60</span><span class="sxs-lookup"><span data-stu-id="af6f3-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6f3-118">Sessioni anonime simultanee (senza messaggi istantanei)</span><span class="sxs-lookup"><span data-stu-id="af6f3-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="af6f3-119">224</span><span class="sxs-lookup"><span data-stu-id="af6f3-119">224</span></span></p></td>
<td><p><span data-ttu-id="af6f3-120">28</span><span class="sxs-lookup"><span data-stu-id="af6f3-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6f3-121">Sessioni anonime simultanee (con messaggistica istantanea)</span><span class="sxs-lookup"><span data-stu-id="af6f3-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="af6f3-122">64</span><span class="sxs-lookup"><span data-stu-id="af6f3-122">64</span></span></p></td>
<td><p><span data-ttu-id="af6f3-123">8</span><span class="sxs-lookup"><span data-stu-id="af6f3-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6f3-124">Agenti attivi (formali e informali)</span><span class="sxs-lookup"><span data-stu-id="af6f3-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="af6f3-125">1200</span><span class="sxs-lookup"><span data-stu-id="af6f3-125">1200</span></span></p></td>
<td><p><span data-ttu-id="af6f3-126">1200</span><span class="sxs-lookup"><span data-stu-id="af6f3-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af6f3-127">Numero di gruppi di ricerca</span><span class="sxs-lookup"><span data-stu-id="af6f3-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="af6f3-128">400</span><span class="sxs-lookup"><span data-stu-id="af6f3-128">400</span></span></p></td>
<td><p><span data-ttu-id="af6f3-129">400</span><span class="sxs-lookup"><span data-stu-id="af6f3-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af6f3-130">Numero di gruppi IVR (usare il riconoscimento vocale)</span><span class="sxs-lookup"><span data-stu-id="af6f3-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="af6f3-131">200</span><span class="sxs-lookup"><span data-stu-id="af6f3-131">200</span></span></p></td>
<td><p><span data-ttu-id="af6f3-132">200</span><span class="sxs-lookup"><span data-stu-id="af6f3-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

