---
title: 'Lync Server 2013: Esperienza dei Response Group durante un errore del pool'
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
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="d0754-102">Esperienza dei Response Group in Lync Server 2013 durante un errore del pool</span><span class="sxs-lookup"><span data-stu-id="d0754-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0754-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d0754-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d0754-104">Questa sezione descrive in dettaglio l'influenza delle attività di gruppo di risposta nelle fasi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0754-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="d0754-105">Si verifica un'interruzione nel pool principale, ma il failover non è ancora stato avviato.</span><span class="sxs-lookup"><span data-stu-id="d0754-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="d0754-106">Il servizio non viene superato nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d0754-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="d0754-107">Il servizio non viene restituito al pool principale.</span><span class="sxs-lookup"><span data-stu-id="d0754-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="d0754-108">Esperienza utente quando si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="d0754-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="d0754-109">Quando si verifica un'interruzione del pool o del sito, ma l'amministratore non ha ancora avviato il failover, l'attività di Response Group viene gestita come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0754-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0754-110">Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="d0754-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d0754-111">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d0754-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="d0754-112">Si verifica un'interruzione</span><span class="sxs-lookup"><span data-stu-id="d0754-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0754-113">Tipo di azione chiamata o utente</span><span class="sxs-lookup"><span data-stu-id="d0754-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="d0754-114">Durante l'interruzione</span><span class="sxs-lookup"><span data-stu-id="d0754-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0754-115">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-116">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-117">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-118">In corso le chiamate non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="d0754-119">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-120">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="d0754-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-121">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-122">Se i gruppi di risposta sono stati importati, chiama Connetti al pool di backup, ma gli agenti ospitati nel pool primario non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="d0754-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-123">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d0754-124">La caratteristica è disabilitata durante questa fase.</span><span class="sxs-lookup"><span data-stu-id="d0754-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-125">Informazioni sull'accesso e sull'agente dell'agente</span><span class="sxs-lookup"><span data-stu-id="d0754-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-126">I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-127">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0754-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-128">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="d0754-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-129">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-130">I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-131">I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-132">I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0754-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="d0754-133">Esperienza utente durante il failover</span><span class="sxs-lookup"><span data-stu-id="d0754-133">User Experience During Failover</span></span>

<span data-ttu-id="d0754-134">Quando un amministratore richiama il failover in un pool di backup, le attività di Response Group vengono gestite durante e dopo il failover, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0754-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="d0754-135">La prima colonna descrive il tipo di attività che potrebbe essere in atto.</span><span class="sxs-lookup"><span data-stu-id="d0754-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="d0754-136">La colonna centrale descrive il modo in cui ogni attività viene gestita durante il breve periodo di tempo necessario per il failover del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d0754-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="d0754-137">L'ultima colonna descrive il modo in cui viene gestita l'attività per la durata, dopo il completamento del processo di failover e il pool di backup per il pool principale.</span><span class="sxs-lookup"><span data-stu-id="d0754-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0754-138">Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="d0754-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d0754-139">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d0754-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="d0754-140">Il failover viene avviato</span><span class="sxs-lookup"><span data-stu-id="d0754-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0754-141">Tipo di azione chiamata o utente</span><span class="sxs-lookup"><span data-stu-id="d0754-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="d0754-142">Durante il failover</span><span class="sxs-lookup"><span data-stu-id="d0754-142">During Failover</span></span></th>
<th><span data-ttu-id="d0754-143">Dopo il completamento del failover</span><span class="sxs-lookup"><span data-stu-id="d0754-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0754-144">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-145">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-146">Le chiamate anonime vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-147">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-148">Per i gruppi di risposta importati, le chiamate anonime che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-149">In corso le chiamate non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="d0754-150">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-151">Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="d0754-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d0754-152">Per i gruppi di risposta importati, le chiamate che hanno raggiunto il pool di backup restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-153">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="d0754-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-154">Le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-155">Per i gruppi di risposta importati, le chiamate si connettono al pool di backup, ma gli agenti ospitati nel pool principale sono irraggiungibili.</span><span class="sxs-lookup"><span data-stu-id="d0754-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-156">Se i gruppi di risposta non sono stati importati, le chiamate vengono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-157">Per i gruppi di risposta importati, chiama Connetti al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d0754-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-158">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d0754-159">La caratteristica è disabilitata durante questa fase</span><span class="sxs-lookup"><span data-stu-id="d0754-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-160">Se i gruppi di risposta non vengono importati, le chiamate non riescono.</span><span class="sxs-lookup"><span data-stu-id="d0754-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="d0754-161">Per i gruppi di risposta importati, le chiamate hanno successo.</span><span class="sxs-lookup"><span data-stu-id="d0754-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-162">Informazioni sull'accesso e sull'agente dell'agente</span><span class="sxs-lookup"><span data-stu-id="d0754-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-163">I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-164">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0754-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-165">I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-166">I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-167">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0754-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-168">I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-169">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-170">I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-171">I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-172">I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0754-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-173">I gruppi di risposte di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-174">I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-175">I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0754-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="d0754-176">Esperienza utente durante il failback</span><span class="sxs-lookup"><span data-stu-id="d0754-176">User Experience During Failback</span></span>

<span data-ttu-id="d0754-177">Quando un amministratore richiama il failback nel pool principale, le attività di Response Group vengono gestite durante e dopo il failback, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0754-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0754-178">Durante il ripristino di emergenza, le chiamate si comportano in modo diverso a seconda che i gruppi di risposta del pool primario vengano importati nel pool di backup durante il ripristino</span><span class="sxs-lookup"><span data-stu-id="d0754-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d0754-179">Nella tabella seguente i riferimenti ai gruppi di risposta importati indicano che i gruppi di risposta del pool primario sono stati importati nel pool di backup durante la modalità di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d0754-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="d0754-180">Gestione delle chiamate in failback</span><span class="sxs-lookup"><span data-stu-id="d0754-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0754-181">Tipo di azione chiamata o utente</span><span class="sxs-lookup"><span data-stu-id="d0754-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="d0754-182">Durante il failback</span><span class="sxs-lookup"><span data-stu-id="d0754-182">During Failback</span></span></th>
<th><span data-ttu-id="d0754-183">Dopo il completamento del failback</span><span class="sxs-lookup"><span data-stu-id="d0754-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0754-184">Chiamate connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-185">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-186">Se i gruppi di risposta non sono stati importati, non sono presenti chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="d0754-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d0754-187">Per i gruppi di risposta importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-188">Le chiamate regolari restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d0754-189">Se i gruppi di risposta non sono stati importati, non sono presenti chiamate anonime in questo stato.</span><span class="sxs-lookup"><span data-stu-id="d0754-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d0754-190">Per i gruppi di risposta importati, le chiamate anonime restano connesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-191">In corso le chiamate non ancora connesse a un agente</span><span class="sxs-lookup"><span data-stu-id="d0754-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-192">Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="d0754-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d0754-193">Per i gruppi di risposta importati, le chiamate verranno disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-194">Se i gruppi di risposta non sono stati importati, non sono presenti chiamate in questo stato.</span><span class="sxs-lookup"><span data-stu-id="d0754-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d0754-195">Per i gruppi di risposta importati, le chiamate verranno disconnesse.</span><span class="sxs-lookup"><span data-stu-id="d0754-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-196">Nuove chiamate</span><span class="sxs-lookup"><span data-stu-id="d0754-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="d0754-197">Chiamate connettersi al pool principale, ma gli agenti ospitati nel pool principale sono irraggiungibili.</span><span class="sxs-lookup"><span data-stu-id="d0754-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="d0754-198">Chiama Connetti al pool principale.</span><span class="sxs-lookup"><span data-stu-id="d0754-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-199">Chiamate agente per conto di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d0754-200">La caratteristica è disabilitata durante questa fase.</span><span class="sxs-lookup"><span data-stu-id="d0754-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="d0754-201">Le chiamate hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d0754-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0754-202">Informazioni sull'accesso e sull'agente dell'agente</span><span class="sxs-lookup"><span data-stu-id="d0754-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-203">I gruppi di agenti di proprietà del pool primario possono essere visualizzati nella console agente, ma gli agenti non possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-204">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0754-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-205">I gruppi di agenti importati vengono visualizzati nella console agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-206">I gruppi di agenti di proprietà del pool principale possono essere visualizzati nella console dell'agente e gli agenti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d0754-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-207">I gruppi di agenti di proprietà del pool di backup possono essere visualizzati nella console agente e gli agenti possono eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0754-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d0754-208">I gruppi di agenti importati non vengono visualizzati nella console dell'agente.</span><span class="sxs-lookup"><span data-stu-id="d0754-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0754-209">Configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="d0754-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d0754-210">I gruppi di risposta di proprietà del pool primario possono essere visualizzati, a seconda della disponibilità del database back-end del pool principale, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-211">I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-212">I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0754-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d0754-213">I gruppi di risposte di proprietà del pool primario possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-214">I gruppi di risposte di proprietà del pool di backup possono essere visualizzati e modificati.</span><span class="sxs-lookup"><span data-stu-id="d0754-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d0754-215">I gruppi di risposta importati non possono essere visualizzati con il pannello di controllo di Lync Server o con lo strumento di configurazione di Response Group, ma possono essere configurati usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0754-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

