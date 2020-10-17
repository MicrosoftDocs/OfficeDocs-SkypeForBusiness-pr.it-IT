---
title: 'Lync Server 2013: pianificazione della capacità per il parcheggio di chiamata'
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
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512833"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="e4f86-102">Pianificazione della capacità per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4f86-102">Capacity planning for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f86-103">_**Ultimo argomento modificato:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="e4f86-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="e4f86-104">Nella tabella seguente viene descritto il modello utente del parcheggio di chiamata che è possibile utilizzare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="e4f86-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4f86-105">Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi parcheggio di chiamata in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="e4f86-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="e4f86-106">Modello utente del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="e4f86-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f86-107">Metrica</span><span class="sxs-lookup"><span data-stu-id="e4f86-107">Metric</span></span></th>
<th><span data-ttu-id="e4f86-108">Per pool Front End (con 8 Front End Server)</span><span class="sxs-lookup"><span data-stu-id="e4f86-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="e4f86-109">Per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e4f86-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f86-110">Frequenza di parcheggio</span><span class="sxs-lookup"><span data-stu-id="e4f86-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="e4f86-111">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="e4f86-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="e4f86-112">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="e4f86-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f86-113">Frequenza di recupero delle chiamate parcheggiate</span><span class="sxs-lookup"><span data-stu-id="e4f86-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="e4f86-114">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="e4f86-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="e4f86-115">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="e4f86-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f86-116">Durata media del parcheggio</span><span class="sxs-lookup"><span data-stu-id="e4f86-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="e4f86-117">60 secondi</span><span class="sxs-lookup"><span data-stu-id="e4f86-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="e4f86-118">60 secondi</span><span class="sxs-lookup"><span data-stu-id="e4f86-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

