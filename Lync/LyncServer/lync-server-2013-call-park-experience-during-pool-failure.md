---
title: 'Lync Server 2013: Esperienza del parcheggio di chiamata durante un errore del pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="f5f13-102">Esperienza del parcheggio di chiamata in Lync Server 2013 durante un errore del pool</span><span class="sxs-lookup"><span data-stu-id="f5f13-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f13-103">_**Argomento Ultima modifica:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f5f13-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f5f13-104">Quando un pool Front-end diventa non disponibile a causa di un evento non pianificato, le chiamate parcheggiate ma non ancora recuperate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f5f13-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="f5f13-105">Durante il failover in un pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità resilienza.</span><span class="sxs-lookup"><span data-stu-id="f5f13-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="f5f13-106">In modalità resilienza, gli utenti non possono parcheggiare le chiamate, ma possono effettuare chiamate in attesa e trasferirle.</span><span class="sxs-lookup"><span data-stu-id="f5f13-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="f5f13-107">Al termine del failover, le chiamate possono essere di nuovo parcheggiate e recuperate come di consueto.</span><span class="sxs-lookup"><span data-stu-id="f5f13-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="f5f13-108">Durante il failback, gli utenti non possono parcheggiare le chiamate finché non si trovano in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="f5f13-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="f5f13-109">Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover usano l'applicazione Parcheggio di chiamata distribuita nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="f5f13-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="f5f13-110">Di conseguenza, gli utenti che vengono reindirizzati al pool di backup usano le impostazioni del parcheggio di chiamata configurate per l'applicazione Call Park nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="f5f13-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="f5f13-111">La tabella seguente riepiloga l'esperienza di parcheggio delle chiamate attraverso le fasi del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f5f13-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="f5f13-112">Esperienza utente durante il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="f5f13-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f13-113">Stato chiamata</span><span class="sxs-lookup"><span data-stu-id="f5f13-113">Call state</span></span></th>
<th><span data-ttu-id="f5f13-114">Quando si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="f5f13-114">When outage occurs</span></span></th>
<th><span data-ttu-id="f5f13-115">Durante il failover</span><span class="sxs-lookup"><span data-stu-id="f5f13-115">During failover</span></span></th>
<th><span data-ttu-id="f5f13-116">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="f5f13-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f13-117">Chiamata non ancora parcheggiata</span><span class="sxs-lookup"><span data-stu-id="f5f13-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="f5f13-118">La chiamata rimane connessa, ma non può essere parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="f5f13-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5f13-119">Durante il failover, la chiamata non può essere parcheggiata mentre gli utenti sono in modalità di resilienza, ma possono essere messi in attesa e trasferiti.</span><span class="sxs-lookup"><span data-stu-id="f5f13-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="f5f13-120">Quando il failover viene completato, la chiamata può essere parcheggiata e recuperata.</span><span class="sxs-lookup"><span data-stu-id="f5f13-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f5f13-121">Durante il failback, la chiamata non può essere parcheggiata mentre gli utenti sono in modalità di resilienza, ma possono essere messi in attesa e trasferiti.</span><span class="sxs-lookup"><span data-stu-id="f5f13-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="f5f13-122">Quando il failback viene completato, la chiamata può essere parcheggiata e recuperata.</span><span class="sxs-lookup"><span data-stu-id="f5f13-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f13-123">Chiamata parcheggiata, ma non ancora recuperata</span><span class="sxs-lookup"><span data-stu-id="f5f13-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="f5f13-124">La chiamata è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="f5f13-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="f5f13-125">Nessuna chiamata in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f5f13-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="f5f13-126">La chiamata rimane parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="f5f13-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f13-127">Chiamata parcheggiata già recuperata</span><span class="sxs-lookup"><span data-stu-id="f5f13-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="f5f13-128">La chiamata rimane connessa.</span><span class="sxs-lookup"><span data-stu-id="f5f13-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="f5f13-129">La chiamata rimane connessa.</span><span class="sxs-lookup"><span data-stu-id="f5f13-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="f5f13-130">La chiamata rimane connessa.</span><span class="sxs-lookup"><span data-stu-id="f5f13-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

