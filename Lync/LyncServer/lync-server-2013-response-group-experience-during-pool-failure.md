---
title: Esperienza di Response Group di Lync Server 2013 durante un errore del pool
description: Esperienza di Response Group di Lync Server 2013 durante un errore del pool.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564572"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="f2d7a-103">Esperienza di Response Group in Lync Server 2013 durante un errore del pool</span><span class="sxs-lookup"><span data-stu-id="f2d7a-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d7a-104">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="f2d7a-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="f2d7a-105">In questa sezione viene descritto in dettaglio in che modo l'attività Response Group è intaccata nelle fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="f2d7a-106">Si verifica un'interruzione nel pool primario, ma il failover non è stato ancora avviato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="f2d7a-107">Il servizio non viene eseguito nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="f2d7a-108">Il servizio non viene ripristinato nel pool primario.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="f2d7a-109">Esperienza utente quando si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="f2d7a-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="f2d7a-110">Quando si verifica un'interruzione del pool o del sito, ma l'amministratore non ha ancora avviato il failover, l'attività dei Response Group viene gestita come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2d7a-111">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="f2d7a-111">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="f2d7a-112">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-112">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="f2d7a-113">Si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="f2d7a-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d7a-114">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="f2d7a-115">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="f2d7a-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-116">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-117">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-118">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-119">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-120">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-121">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="f2d7a-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-122">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-123">Se i Response Group sono stati importati, le chiamate si connettono al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-124">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-125">La funzionalità è disabilitata in questa fase.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-126">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-127">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-128">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-129">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-130">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-131">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-132">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-133">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="f2d7a-134">Esperienza utente durante il failover</span><span class="sxs-lookup"><span data-stu-id="f2d7a-134">User Experience During Failover</span></span>

<span data-ttu-id="f2d7a-135">Quando un amministratore richiama il failover su un pool di backup, l'attività dei Response Group viene gestita durante e dopo il failover come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-135">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="f2d7a-136">Nella prima colonna viene descritto il tipo di attività che potrebbe essere in corso.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-136">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="f2d7a-137">Nella colonna centrale viene descritto il modo in cui ogni attività viene gestita durante il breve periodo di tempo necessario per eseguire il failover del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-137">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="f2d7a-138">Nell'ultima colonna viene descritto il modo in cui l'attività viene gestita per la durata, dopo il completamento del processo di failover e il pool di backup per il pool primario.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-138">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2d7a-139">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="f2d7a-139">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="f2d7a-140">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-140">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="f2d7a-141">Il failover è stato avviato</span><span class="sxs-lookup"><span data-stu-id="f2d7a-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d7a-142">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="f2d7a-143">Durante il failover</span><span class="sxs-lookup"><span data-stu-id="f2d7a-143">During Failover</span></span></th>
<th><span data-ttu-id="f2d7a-144">Dopo il completamento del failover</span><span class="sxs-lookup"><span data-stu-id="f2d7a-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-145">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-146">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-147">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-148">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-149">Per i Response Group importati, le chiamate anonime che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-150">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-151">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-152">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-153">Per i Response Group importati, le chiamate che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-154">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="f2d7a-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-155">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-156">Per i Response Group importati, le chiamate vengono connesse al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-157">Se i Response Group non sono stati importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-158">Per i Response Group importati, le chiamate vengono connesse al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-159">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-160">La funzionalità è disabilitata durante questa fase</span><span class="sxs-lookup"><span data-stu-id="f2d7a-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-161">Se i Response Group non sono stati importati, le chiamate vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-162">Per i Response Group importati, le chiamate vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-163">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-164">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-165">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-166">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-167">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-168">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-169">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-170">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-171">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-172">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-173">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-174">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-175">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-176">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="f2d7a-177">Esperienza utente durante il failback</span><span class="sxs-lookup"><span data-stu-id="f2d7a-177">User Experience During Failback</span></span>

<span data-ttu-id="f2d7a-178">Quando un amministratore richiama il failback al pool primario, l'attività del gruppo di risposta viene gestita durante e dopo il failback come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2d7a-179">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="f2d7a-179">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="f2d7a-180">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-180">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="f2d7a-181">Gestione delle chiamate nel failback</span><span class="sxs-lookup"><span data-stu-id="f2d7a-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2d7a-182">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="f2d7a-183">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="f2d7a-183">During Failback</span></span></th>
<th><span data-ttu-id="f2d7a-184">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="f2d7a-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-185">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-186">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-187">Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-188">Per i Response Group importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-189">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-190">Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-191">Per i Response Group importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-192">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-193">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-194">Per i Response Group importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-195">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-196">Per i Response Group importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-197">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="f2d7a-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-198">Le chiamate si connettono al pool primario, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-199">Le chiamate si connettono al pool primario.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-200">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-201">La funzionalità è disabilitata in questa fase.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="f2d7a-202">Le chiamate hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d7a-203">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="f2d7a-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-204">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-205">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-206">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-207">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-208">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-209">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d7a-210">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="f2d7a-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-211">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-212">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-213">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f2d7a-214">I Response Group di proprietà del pool primario possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-215">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="f2d7a-216">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

