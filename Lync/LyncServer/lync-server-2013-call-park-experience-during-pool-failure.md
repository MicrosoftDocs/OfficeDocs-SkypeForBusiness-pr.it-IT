---
title: 'Lync Server 2013: esperienza del parcheggio di chiamata durante un errore del pool'
description: 'Lync Server 2013: esperienza del parcheggio di chiamata durante un errore del pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565272"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="35666-103">Esperienza del parcheggio di chiamata in Lync Server 2013 durante un errore del pool</span><span class="sxs-lookup"><span data-stu-id="35666-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35666-104">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="35666-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="35666-105">Quando un pool Front end non è disponibile a causa di un incidente non pianificato, le chiamate che sono state parcheggiate ma non ancora recuperate sono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="35666-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="35666-106">Durante l'esecuzione di un failover in un pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="35666-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="35666-107">In modalità di resilienza gli utenti non possono parcheggiare le chiamate, ma possono mettere le chiamate in attesa e trasferirle.</span><span class="sxs-lookup"><span data-stu-id="35666-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="35666-108">Completato il failover, è possibile parcheggiare nuovamente le chiamate e recuperarle normalmente.</span><span class="sxs-lookup"><span data-stu-id="35666-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="35666-109">Durante il failback, gli utenti non possono parcheggiare le chiamate finché non sono usciti dalla modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="35666-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="35666-110">Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover utilizzano l'applicazione Parcheggio di chiamata distribuita nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="35666-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="35666-111">Di conseguenza, gli utenti che vengono reindirizzati al pool di backup utilizzano le impostazioni del parcheggio di chiamata configurate per l'applicazione Parcheggio di chiamata nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="35666-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="35666-112">Nella tabella seguente viene riepilogata l'esperienza del parcheggio di chiamata tramite le fasi del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="35666-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="35666-113">Esperienza utente durante il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="35666-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35666-114">Stato chiamata</span><span class="sxs-lookup"><span data-stu-id="35666-114">Call state</span></span></th>
<th><span data-ttu-id="35666-115">In caso di guasto</span><span class="sxs-lookup"><span data-stu-id="35666-115">When outage occurs</span></span></th>
<th><span data-ttu-id="35666-116">Durante il failover</span><span class="sxs-lookup"><span data-stu-id="35666-116">During failover</span></span></th>
<th><span data-ttu-id="35666-117">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="35666-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35666-118">Chiamata non ancora parcheggiata</span><span class="sxs-lookup"><span data-stu-id="35666-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="35666-119">La chiamata rimane connessa, ma non può essere parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="35666-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="35666-120">Durante il failover non è possibile parcheggiare la chiamata mentre gli utenti sono in modalità di resilienza, ma è possibile metterla in attesa e trasferirla.</span><span class="sxs-lookup"><span data-stu-id="35666-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="35666-121">Completato il failover, è possibile parcheggiare e recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35666-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="35666-122">Durante il failback non è possibile parcheggiare la chiamata mentre gli utenti sono in modalità di resilienza, ma è possibile metterla in attesa e trasferirla.</span><span class="sxs-lookup"><span data-stu-id="35666-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="35666-123">Completato il failback, è possibile parcheggiare e recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35666-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35666-124">Chiamata parcheggiata, ma non ancora recuperata</span><span class="sxs-lookup"><span data-stu-id="35666-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="35666-125">La chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="35666-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="35666-126">Nessuna chiamata in questo stato.</span><span class="sxs-lookup"><span data-stu-id="35666-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="35666-127">La chiamata resta parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="35666-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35666-128">Chiamata parcheggiata già recuperata</span><span class="sxs-lookup"><span data-stu-id="35666-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="35666-129">Le chiamate restano connesse.</span><span class="sxs-lookup"><span data-stu-id="35666-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="35666-130">Le chiamate restano connesse.</span><span class="sxs-lookup"><span data-stu-id="35666-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="35666-131">Le chiamate restano connesse.</span><span class="sxs-lookup"><span data-stu-id="35666-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

