---
title: Esperienza di Response Group di Lync Server 2013 durante un errore del pool
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
ms.openlocfilehash: d3977d05c0916cc23f628c0af26be1cbc8a79990
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="7fe14-102">Esperienza di Response Group in Lync Server 2013 durante un errore del pool</span><span class="sxs-lookup"><span data-stu-id="7fe14-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe14-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7fe14-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7fe14-104">In questa sezione viene descritto in dettaglio in che modo l'attività Response Group è intaccata nelle fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fe14-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="7fe14-105">Si verifica un'interruzione nel pool primario, ma il failover non è stato ancora avviato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="7fe14-106">Il servizio non viene eseguito nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7fe14-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="7fe14-107">Il servizio non viene ripristinato nel pool primario.</span><span class="sxs-lookup"><span data-stu-id="7fe14-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="7fe14-108">Esperienza utente quando si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="7fe14-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="7fe14-109">Quando si verifica un'interruzione del pool o del sito, ma l'amministratore non ha ancora avviato il failover, l'attività dei Response Group viene gestita come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe14-110">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="7fe14-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="7fe14-111">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7fe14-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="7fe14-112">Si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="7fe14-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe14-113">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7fe14-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="7fe14-114">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="7fe14-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-115">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-116">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-117">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-118">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="7fe14-119">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-120">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="7fe14-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-121">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-122">Se i Response Group sono stati importati, le chiamate si connettono al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="7fe14-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-123">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7fe14-124">La funzionalità è disabilitata in questa fase.</span><span class="sxs-lookup"><span data-stu-id="7fe14-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-125">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-126">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-127">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-128">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-129">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-130">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-131">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-132">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe14-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="7fe14-133">Esperienza utente durante il failover</span><span class="sxs-lookup"><span data-stu-id="7fe14-133">User Experience During Failover</span></span>

<span data-ttu-id="7fe14-134">Quando un amministratore richiama il failover su un pool di backup, l'attività dei Response Group viene gestita durante e dopo il failover come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="7fe14-135">Nella prima colonna viene descritto il tipo di attività che potrebbe essere in corso.</span><span class="sxs-lookup"><span data-stu-id="7fe14-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="7fe14-136">Nella colonna centrale viene descritto il modo in cui ogni attività viene gestita durante il breve periodo di tempo necessario per eseguire il failover del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7fe14-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="7fe14-137">Nell'ultima colonna viene descritto il modo in cui l'attività viene gestita per la durata, dopo il completamento del processo di failover e il pool di backup per il pool primario.</span><span class="sxs-lookup"><span data-stu-id="7fe14-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe14-138">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="7fe14-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="7fe14-139">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7fe14-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="7fe14-140">Il failover è stato avviato</span><span class="sxs-lookup"><span data-stu-id="7fe14-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe14-141">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7fe14-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="7fe14-142">Durante il failover</span><span class="sxs-lookup"><span data-stu-id="7fe14-142">During Failover</span></span></th>
<th><span data-ttu-id="7fe14-143">Dopo il completamento del failover</span><span class="sxs-lookup"><span data-stu-id="7fe14-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-144">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-145">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-146">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-147">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-148">Per i Response Group importati, le chiamate anonime che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-149">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="7fe14-150">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-151">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-152">Per i Response Group importati, le chiamate che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-153">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="7fe14-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-154">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-155">Per i Response Group importati, le chiamate vengono connesse al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="7fe14-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-156">Se i Response Group non sono stati importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-157">Per i Response Group importati, le chiamate vengono connesse al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7fe14-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-158">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7fe14-159">La funzionalità è disabilitata durante questa fase</span><span class="sxs-lookup"><span data-stu-id="7fe14-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-160">Se i Response Group non sono stati importati, le chiamate vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-161">Per i Response Group importati, le chiamate vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-162">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-163">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-164">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-165">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-166">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-167">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-168">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-169">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-170">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-171">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-172">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe14-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-173">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-174">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-175">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe14-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="7fe14-176">Esperienza utente durante il failback</span><span class="sxs-lookup"><span data-stu-id="7fe14-176">User Experience During Failback</span></span>

<span data-ttu-id="7fe14-177">Quando un amministratore richiama il failback al pool primario, l'attività del gruppo di risposta viene gestita durante e dopo il failback come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe14-178">Durante il ripristino di emergenza le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario siano stati importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="7fe14-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="7fe14-179">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7fe14-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="7fe14-180">Gestione delle chiamate nel failback</span><span class="sxs-lookup"><span data-stu-id="7fe14-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe14-181">Tipo di chiamata o azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7fe14-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="7fe14-182">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="7fe14-182">During Failback</span></span></th>
<th><span data-ttu-id="7fe14-183">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="7fe14-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-184">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-185">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-186">Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-187">Per i Response Group importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-188">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-189">Se i Response Group non sono stati importati, non ci sono chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-190">Per i Response Group importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-191">Chiamate in corso non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-192">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-193">Per i Response Group importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-194">Se i Response Group non sono stati importati, non ci sono chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="7fe14-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-195">Per i Response Group importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="7fe14-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-196">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="7fe14-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="7fe14-197">Le chiamate si connettono al pool primario, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="7fe14-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="7fe14-198">Le chiamate si connettono al pool primario.</span><span class="sxs-lookup"><span data-stu-id="7fe14-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-199">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7fe14-200">La funzionalità è disabilitata in questa fase.</span><span class="sxs-lookup"><span data-stu-id="7fe14-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="7fe14-201">Le chiamate hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7fe14-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe14-202">Accesso dell'agente e informazioni sull'agente</span><span class="sxs-lookup"><span data-stu-id="7fe14-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-203">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console dell'agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-204">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-205">I gruppi di agenti importati vengono visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-206">I gruppi di agenti di proprietà del pool primario possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-207">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati sulla console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="7fe14-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-208">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="7fe14-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe14-209">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="7fe14-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-210">I Response Group di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool primario, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-211">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-212">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe14-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7fe14-213">I Response Group di proprietà del pool primario possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-214">I Response Group di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="7fe14-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7fe14-215">Non è possibile visualizzare i Response Group importati con il pannello di controllo di Lync Server o lo strumento di configurazione di Response Group, ma possono essere configurati utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe14-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

