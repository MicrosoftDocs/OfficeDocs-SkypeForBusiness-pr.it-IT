---
title: 'Lync Server 2013: Pianificazione della capacità per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd4cc9d10a3a3562c035c7bc2f64f551b70cc5da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f9152-102">Pianificazione della capacità per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9152-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9152-103">_**Argomento Ultima modifica:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f9152-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f9152-104">La tabella seguente descrive il modello utente di Call Park che puoi usare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="f9152-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9152-105">Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="f9152-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="f9152-106">Modello utente di Call Park</span><span class="sxs-lookup"><span data-stu-id="f9152-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9152-107">Metrica</span><span class="sxs-lookup"><span data-stu-id="f9152-107">Metric</span></span></th>
<th><span data-ttu-id="f9152-108">Per pool Front-End (con 8 server front-end)</span><span class="sxs-lookup"><span data-stu-id="f9152-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="f9152-109">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f9152-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9152-110">Tasso di parcheggio</span><span class="sxs-lookup"><span data-stu-id="f9152-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="f9152-111">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="f9152-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="f9152-112">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="f9152-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9152-113">Recuperare la frequenza delle chiamate parcheggiate</span><span class="sxs-lookup"><span data-stu-id="f9152-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="f9152-114">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="f9152-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="f9152-115">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="f9152-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9152-116">Durata media del parco</span><span class="sxs-lookup"><span data-stu-id="f9152-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="f9152-117">60 secondi</span><span class="sxs-lookup"><span data-stu-id="f9152-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="f9152-118">60 secondi</span><span class="sxs-lookup"><span data-stu-id="f9152-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

