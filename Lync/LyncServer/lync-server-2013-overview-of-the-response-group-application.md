---
title: "Lync Server 2013: Panoramica dell'applicazione Response Group"
description: "Lync Server 2013: Panoramica dell'applicazione Response Group."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763a64adcf0eaf43e8f98a49cd850882ca9c91c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552382"
---
# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="dad24-103">Panoramica dell'applicazione Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad24-103">Overview of the Response Group application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dad24-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="dad24-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="dad24-105">Quando un chiamante chiama un Response Group, viene eseguito il routing della chiamata a un agente in base a un gruppo di risposta o alle risposte del chiamante alle domande di un sistema IVR (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="dad24-105">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="dad24-106">L'applicazione Response Group utilizza metodi di routing di Response Group standard per instradare la chiamata al successivo agente disponibile.</span><span class="sxs-lookup"><span data-stu-id="dad24-106">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="dad24-107">I metodi di routing delle chiamate includono routing seriale, verso l'agente inattivo più a lungo, round robin e il nuovo routing operatore, in cui vengono chiamati tutti gli agenti contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla loro effettiva presenza.</span><span class="sxs-lookup"><span data-stu-id="dad24-107">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="dad24-108">Se non è disponibile alcun agente, la chiamata viene mantenuta in una coda fino a quando non è disponibile un agente.</span><span class="sxs-lookup"><span data-stu-id="dad24-108">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="dad24-109">Mentre la chiamata è nella coda, il chiamante ascolta un brano musicale fino a quando un agente disponibile non accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dad24-109">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="dad24-110">Se la coda è piena o si verifica il timeout della chiamata mentre questa è in coda, il chiamante potrebbe ascoltare un messaggio e quindi venire disconnesso o trasferito a una destinazione diversa.</span><span class="sxs-lookup"><span data-stu-id="dad24-110">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="dad24-111">Quando un agente accetta la chiamata, il chiamante può o meno visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore ha configurato Response Group.</span><span class="sxs-lookup"><span data-stu-id="dad24-111">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="dad24-112">Gli agenti possono essere agenti formali, ovvero devono accedere al gruppo prima di poter accettare le chiamate di cui viene eseguito il routing al gruppo, oppure agenti informali, ovvero non accedono al gruppo né si disconnettono per accettare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="dad24-112">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dad24-p102">Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.</span><span class="sxs-lookup"><span data-stu-id="dad24-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dad24-115">L'applicazione Response Group utilizza un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="dad24-115">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="dad24-116">Ogni computer che esegue l'applicazione Response Group esegue il servizio di corrispondenza, ma è attivo un solo servizio di corrispondenza per ogni pool di Lync Server alla volta: le altre sono passive.</span><span class="sxs-lookup"><span data-stu-id="dad24-116">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="dad24-117">Se il servizio di ricerca corrispondenze diventa non disponibile durante un guasto non pianificato, viene attivato uno dei servizi di ricerca corrispondenze passivi.</span><span class="sxs-lookup"><span data-stu-id="dad24-117">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="dad24-118">L'applicazione Response Group consente di fare in modo che il routing delle chiamate e l'accodamento continuino senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="dad24-118">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="dad24-119">Quando si verifica una transizione a un servizio di ricerca corrispondenze, tutte le chiamate in trasferimento durante la transizione vengono perdute.</span><span class="sxs-lookup"><span data-stu-id="dad24-119">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="dad24-120">Ad esempio, se la transizione è dovuta alla fine del server front-end, vengono perse anche tutte le chiamate attualmente gestite dal servizio di corrispondenza attivo in quel front end server.</span><span class="sxs-lookup"><span data-stu-id="dad24-120">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="dad24-121">In Lync Server 2013, sono disponibili due ruoli di gestione per la gestione dei Response Group, ovvero il responsabile del gruppo di risposta e l'amministratore di Response Group.</span><span class="sxs-lookup"><span data-stu-id="dad24-121">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="dad24-122">Gli amministratori di Response Group possono gestire qualsiasi aspetto di qualsiasi Response Group.</span><span class="sxs-lookup"><span data-stu-id="dad24-122">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="dad24-123">I responsabili dei Response Group possono gestire solo alcuni aspetti e solo per i Response Group di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="dad24-123">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="dad24-124">Il nuovo ruolo di gestione può contribuire a ridurre i costi amministrativi, in quanto è possibile delegare responsabilità limitate per gruppi di risposta specifici a qualsiasi utente abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dad24-124">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="dad24-125">Per ospitare il nuovo ruolo di gestione, Lync Server 2013 Response Group Application introduce un **tipo di flusso di lavoro** gestito o non gestito.</span><span class="sxs-lookup"><span data-stu-id="dad24-125">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="dad24-126">Nella tabella riportata di seguito vengono descritti i Response Group gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="dad24-126">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="dad24-127">Response Group gestiti e non gestiti</span><span class="sxs-lookup"><span data-stu-id="dad24-127">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dad24-128">Tipo di Response Group</span><span class="sxs-lookup"><span data-stu-id="dad24-128">Response group type</span></span></th>
<th><span data-ttu-id="dad24-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dad24-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dad24-130">Gestito</span><span class="sxs-lookup"><span data-stu-id="dad24-130">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dad24-131">Ai Response Group non gestiti non è assegnato alcun Gestore.</span><span class="sxs-lookup"><span data-stu-id="dad24-131">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="dad24-132">Solo l'amministratore del gruppo di risposta può configurare questi Response Group.</span><span class="sxs-lookup"><span data-stu-id="dad24-132">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="dad24-133">Response group multipli non gestiti possono condividere una coda o gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="dad24-133">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="dad24-134">Quando si esegue la migrazione dei Response Group da una versione precedente a Lync Server 2013, il tipo è impostato su non gestito.</span><span class="sxs-lookup"><span data-stu-id="dad24-134">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dad24-135">Gestione</span><span class="sxs-lookup"><span data-stu-id="dad24-135">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dad24-136">Gli amministratori di Response Group possono configurare qualsiasi aspetto dei gruppi di risposta gestiti.</span><span class="sxs-lookup"><span data-stu-id="dad24-136">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="dad24-137">I responsabili dei Response Group non sono in grado di visualizzare o modificare gruppi di risposta non assegnati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dad24-137">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="dad24-138">I responsabili dei Response Group possono configurare solo alcune impostazioni per i Response Group a loro assegnati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dad24-138">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="dad24-139">I Response group gestiti non possono condividere code o gruppi di agenti con altri Response group gestiti o non gestiti.</span><span class="sxs-lookup"><span data-stu-id="dad24-139">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dad24-140">Nella tabella seguente vengono descritte le azioni che possono essere eseguite dai responsabili dei Response Group e che non è possibile eseguire per i Response Group a loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="dad24-140">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="dad24-141">Capacità del manager del Response group</span><span class="sxs-lookup"><span data-stu-id="dad24-141">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dad24-142">Possono configurare:</span><span class="sxs-lookup"><span data-stu-id="dad24-142">Can configure:</span></span></th>
<th><span data-ttu-id="dad24-143">Possono creare, eliminare o configurare:</span><span class="sxs-lookup"><span data-stu-id="dad24-143">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="dad24-144">Possibile</span><span class="sxs-lookup"><span data-stu-id="dad24-144">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="dad24-145">Agents</span><span class="sxs-lookup"><span data-stu-id="dad24-145">Agents</span></span></p></li>
<li><p><span data-ttu-id="dad24-146">Messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="dad24-146">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="dad24-147">Nome del gruppo di risposta</span><span class="sxs-lookup"><span data-stu-id="dad24-147">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="dad24-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dad24-148">Description</span></span></p></li>
<li><p><span data-ttu-id="dad24-149">Numero visualizzato</span><span class="sxs-lookup"><span data-stu-id="dad24-149">Display number</span></span></p></li>
<li><p><span data-ttu-id="dad24-150">Ore lavorative</span><span class="sxs-lookup"><span data-stu-id="dad24-150">Business hours</span></span></p></li>
<li><p><span data-ttu-id="dad24-151">Musica di attesa</span><span class="sxs-lookup"><span data-stu-id="dad24-151">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="dad24-152">Stato (attivo/inattivo)</span><span class="sxs-lookup"><span data-stu-id="dad24-152">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="dad24-153">Workflow del gruppo di risposta o Interactive voice response (IVR)</span><span class="sxs-lookup"><span data-stu-id="dad24-153">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dad24-154">Gestione di gruppi di agenti</span><span class="sxs-lookup"><span data-stu-id="dad24-154">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="dad24-155">Code</span><span class="sxs-lookup"><span data-stu-id="dad24-155">Queues</span></span></p></li>
<li><p><span data-ttu-id="dad24-156">Insiemi di festività</span><span class="sxs-lookup"><span data-stu-id="dad24-156">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dad24-157">Creare o eliminare qualsiasi tipo di workflow</span><span class="sxs-lookup"><span data-stu-id="dad24-157">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="dad24-158">Modificare le impostazioni fondamentali dei Response Group, quali: <strong>URI SIP</strong>, <strong>Numero di telefono</strong> o <strong>Tipo di workflow</strong>.</span><span class="sxs-lookup"><span data-stu-id="dad24-158">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dad24-159">I responsabili dei Response Group possono utilizzare gli strumenti seguenti per gestire i Response Group designati.</span><span class="sxs-lookup"><span data-stu-id="dad24-159">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="dad24-160">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="dad24-160">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dad24-161">I responsabili dei Response Group possono gestire solo le impostazioni di Response Group con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="dad24-161">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="dad24-162">Altre impostazioni di Lync Server non sono disponibili per i responsabili.</span><span class="sxs-lookup"><span data-stu-id="dad24-162">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="dad24-163">Strumento di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="dad24-163">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="dad24-164">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="dad24-164">Lync Server Management Shell</span></span>

<span data-ttu-id="dad24-165">La scala dei Response Group è adatta agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, vedere [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e può essere distribuita in installazioni di telefonia completamente nuove.</span><span class="sxs-lookup"><span data-stu-id="dad24-165">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="dad24-166">Supporta le chiamate in arrivo dalla distribuzione di VoIP aziendale e dalla rete di vettori locali.</span><span class="sxs-lookup"><span data-stu-id="dad24-166">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="dad24-167">Gli agenti possono utilizzare Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate a tali operatori.</span><span class="sxs-lookup"><span data-stu-id="dad24-167">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="dad24-168">L'applicazione Response Group è un componente di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dad24-168">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="dad24-169">Quando si distribuisce VoIP aziendale, l'applicazione Response Group viene installata e attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dad24-169">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

