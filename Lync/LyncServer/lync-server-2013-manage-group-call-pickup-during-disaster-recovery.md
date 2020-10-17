---
title: 'Lync Server 2013: gestione del prelievo delle chiamate di gruppo durante il ripristino di emergenza'
description: 'Lync Server 2013: gestione del prelievo delle chiamate di gruppo durante il ripristino di emergenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04d85bc83cfe35571c2b0f47f707c9dcd8037d80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555282"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ab028-103">Gestire il ritiro delle chiamate di gruppo durante il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab028-103">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab028-104">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ab028-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ab028-105">Quando un pool Front end diventa non disponibile a causa di un incidente non pianificato, il servizio non viene eseguito nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ab028-105">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="ab028-106">Durante il failover per il pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="ab028-106">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="ab028-107">Durante la modalità di resilienza, gli utenti non possono prendere le chiamate di altri utenti o fare in modo che le chiamate vengano raccolte da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="ab028-107">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="ab028-108">Al termine del failover, gli utenti possono utilizzare di nuovo il pick-up di chiamata di gruppo come al solito.</span><span class="sxs-lookup"><span data-stu-id="ab028-108">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="ab028-109">Durante il failback al pool primario, gli utenti vengono reindirizzati al pool primario e sono di nuovo in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="ab028-109">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="ab028-110">La funzionalità di prelievo delle chiamate di gruppo non è disponibile finché gli utenti non sono in modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="ab028-110">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="ab028-111">In questa sezione vengono illustrate alcune considerazioni relative al ritiro delle chiamate di gruppo durante il ripristino di emergenza e viene descritta anche l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="ab028-111">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="ab028-112">Considerazioni per il ritiro delle chiamate di gruppo durante il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="ab028-112">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="ab028-113">Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover utilizzano l'applicazione Parcheggio di chiamata in esecuzione nel pool di backup per i numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ab028-113">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="ab028-114">Pertanto, il supporto per il ritiro delle chiamate di gruppo durante il ripristino di emergenza richiede che l'applicazione Parcheggio di chiamata venga distribuita e abilitata sia nel pool primario che nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ab028-114">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="ab028-115">Gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata devono essere reindirizzati al pool di backup dopo il completamento del processo di failover del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ab028-115">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="ab028-116">Gli intervalli di numeri devono essere reindirizzati al pool primario dopo il completamento del processo di failback del pool primario.</span><span class="sxs-lookup"><span data-stu-id="ab028-116">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="ab028-117">Per reindirizzare gli intervalli di prelievo delle chiamate di gruppo, utilizzare il cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="ab028-117">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="ab028-118">Se si distribuisce un nuovo pool con un nome di dominio completo (FQDN) diverso per sostituire il pool primario, è necessario riassegnare tutti gli intervalli di numeri di prelievo delle chiamate di gruppo che sono stati associati al pool primario all'FQDN del nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="ab028-118">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="ab028-119">Per riassegnare gli intervalli di numeri al nuovo pool, è possibile utilizzare il cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="ab028-119">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="ab028-120">Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="ab028-120">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="ab028-121">Esperienza di ritiro delle chiamate di gruppo durante l'errore del pool</span><span class="sxs-lookup"><span data-stu-id="ab028-121">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="ab028-122">Nella tabella seguente viene riepilogata l'esperienza di prelievo delle chiamate di gruppo tramite le fasi del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ab028-122">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="ab028-123">Esperienza utente durante il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="ab028-123">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab028-124">Stato chiamata</span><span class="sxs-lookup"><span data-stu-id="ab028-124">Call state</span></span></th>
<th><span data-ttu-id="ab028-125">Failover per il pool di backup</span><span class="sxs-lookup"><span data-stu-id="ab028-125">Failover to backup pool</span></span></th>
<th><span data-ttu-id="ab028-126">Failback al pool primario</span><span class="sxs-lookup"><span data-stu-id="ab028-126">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab028-127">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="ab028-127">New calls</span></span></p></td>
<td><p><span data-ttu-id="ab028-128"><strong>Durante il processo di failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-128"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-129">Raccolta di chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</span><span class="sxs-lookup"><span data-stu-id="ab028-129">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-130"><strong>Dopo il completamento del failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-130"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-131">Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e gli intervalli di numeri di prelievo delle chiamate di gruppo vengono reindirizzati al pool</span><span class="sxs-lookup"><span data-stu-id="ab028-131">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ab028-132"><strong>Durante il processo di failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-132"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-133">Raccolta di chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</span><span class="sxs-lookup"><span data-stu-id="ab028-133">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-134"><strong>Dopo il completamento del failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-134"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-135">Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e gli intervalli di numeri di prelievo delle chiamate di gruppo vengono reindirizzati al pool primario</span><span class="sxs-lookup"><span data-stu-id="ab028-135">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab028-136">Chiamate nella coda di prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="ab028-136">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="ab028-137"><strong>Durante il processo di failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-137"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-138">Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ab028-138">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-139"><strong>Dopo il completamento del failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-139"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-140">Nessuna chiamata in questo stato</span><span class="sxs-lookup"><span data-stu-id="ab028-140">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ab028-141"><strong>Durante il processo di failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-141"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-142">Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ab028-142">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-143"><strong>Dopo il completamento del failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-143"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-144">Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ab028-144">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab028-145">Chiamata stabilita</span><span class="sxs-lookup"><span data-stu-id="ab028-145">Established call</span></span></p></td>
<td><p><span data-ttu-id="ab028-146"><strong>Durante il processo di failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-146"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-147">Chiamate rimanere connesse</span><span class="sxs-lookup"><span data-stu-id="ab028-147">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-148"><strong>Dopo il completamento del failover:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-148"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-149">Chiamate rimanere connesse</span><span class="sxs-lookup"><span data-stu-id="ab028-149">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ab028-150"><strong>Durante il processo di failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-150"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-151">Chiamate rimanere connesse</span><span class="sxs-lookup"><span data-stu-id="ab028-151">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="ab028-152"><strong>Dopo il completamento del failback:</strong></span><span class="sxs-lookup"><span data-stu-id="ab028-152"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="ab028-153">Chiamate rimanere connesse</span><span class="sxs-lookup"><span data-stu-id="ab028-153">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

