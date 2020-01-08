---
title: "Lync Server 2013: Panoramica dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="6c2d9-102">Panoramica dell'applicazione Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2d9-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c2d9-103">_**Argomento Ultima modifica:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="6c2d9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="6c2d9-104">Quando un chiamante chiama un gruppo di risposte, la chiamata viene instradata a un agente in base a un gruppo di risposta o alle domande del chiamante per rispondere alla risposta vocale interattiva (IVR).</span><span class="sxs-lookup"><span data-stu-id="6c2d9-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="6c2d9-105">L'applicazione Response Group USA i metodi di routing dei gruppi di risposta standard per instradare la chiamata al successivo agente disponibile.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="6c2d9-106">I metodi di routing delle chiamate includono il routing seriale, più lungo-inattivo, parallelo, rotondo Robin e supervisore (ovvero tutti gli agenti vengono chiamati contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla presenza corrente).</span><span class="sxs-lookup"><span data-stu-id="6c2d9-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="6c2d9-107">Se non sono disponibili agenti, la chiamata viene mantenuta in una coda finché non è disponibile un agente.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="6c2d9-108">Mentre si è in coda, il chiamante sente la musica finché un agente disponibile non accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="6c2d9-109">Se la coda è piena o se la chiamata viene interrotta durante la coda, il chiamante potrebbe udire un messaggio e quindi essere disconnesso o trasferito in una destinazione diversa.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="6c2d9-110">Quando un agente accetta la chiamata, il chiamante potrebbe non essere in grado di visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore configura il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="6c2d9-111">Gli agenti possono essere formali, quindi devono accedere al gruppo prima di poter accettare le chiamate instradate al gruppo o informale, il che significa che non accedono al gruppo per accettare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c2d9-112">Solo gli utenti locali possono essere agenti.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="6c2d9-113">Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6c2d9-114">L'applicazione Response Group usa un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="6c2d9-115">Ogni computer che esegue l'applicazione Response Group esegue il servizio di creazione delle corrispondenze, ma solo un servizio per il pool di Lync Server è attivo alla volta, mentre gli altri sono passivi.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="6c2d9-116">Se il servizio di corrispondenza attiva diventa non disponibile durante un'interruzione non pianificata, uno dei servizi di corrispondenza passiva diventa attivo.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="6c2d9-117">L'applicazione Response Group fa del suo meglio per assicurarsi che il routing delle chiamate e l'accodamento continuino senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="6c2d9-118">Tuttavia, quando si verifica una transizione del servizio di corrispondenza, le chiamate in fase di trasferimento vengono perse.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="6c2d9-119">Ad esempio, se la transizione è dovuta al fatto che il server front-end si abbassa, vengono perse anche le chiamate attualmente gestite dal servizio Active match making del server front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="6c2d9-120">In Lync Server 2013 sono disponibili due ruoli di gestione per la gestione dei gruppi di risposta: Response Group Manager e Response Group Administrator.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="6c2d9-121">Gli amministratori del gruppo di risposte possono gestire qualsiasi aspetto di un gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="6c2d9-122">I responsabili dei gruppi di risposte possono gestire solo determinati aspetti e solo per i gruppi di risposta di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="6c2d9-123">Il nuovo ruolo di gestione può contribuire a ridurre i costi amministrativi, perché è possibile delegare responsabilità limitate per gruppi di risposta specifici a qualsiasi utente abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="6c2d9-124">Per supportare il nuovo ruolo di Manager, l'applicazione di Response Group di Lync Server 2013 introduce un **tipo di flusso di lavoro** gestito o non gestito.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="6c2d9-125">La tabella seguente descrive i gruppi di risposta gestiti e non Managed.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="6c2d9-126">Gruppi di risposte gestite e non gestiti</span><span class="sxs-lookup"><span data-stu-id="6c2d9-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c2d9-127">Tipo di gruppo di risposta</span><span class="sxs-lookup"><span data-stu-id="6c2d9-127">Response group type</span></span></th>
<th><span data-ttu-id="6c2d9-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c2d9-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c2d9-129">Non gestite</span><span class="sxs-lookup"><span data-stu-id="6c2d9-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6c2d9-130">I gruppi di risposte non gestiti non hanno gestori assegnati.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="6c2d9-131">Solo l'amministratore del gruppo di risposte può configurare questi gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-132">Più gruppi di risposte non gestiti possono condividere una coda o un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-133">Quando si esegue la migrazione dei gruppi di risposte da una versione precedente a Lync Server 2013, il tipo viene impostato su non gestito.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2d9-134">Gestito</span><span class="sxs-lookup"><span data-stu-id="6c2d9-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6c2d9-135">Gli amministratori del gruppo di risposte possono configurare qualsiasi aspetto dei gruppi di risposta gestiti.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-136">I responsabili del gruppo di risposte non possono visualizzare o modificare i gruppi di risposta che non sono assegnati esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-137">I responsabili del gruppo di risposte possono configurare solo alcune impostazioni per i gruppi di risposta assegnati esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-138">I gruppi di risposta gestiti non possono condividere le code o i gruppi di agenti con qualsiasi altro gruppo di risposte, gestito o non gestito.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c2d9-139">La tabella seguente descrive le azioni che i responsabili dei gruppi di risposta possono e non possono eseguire per i gruppi di risposte assegnati.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="6c2d9-140">Funzionalità di gestione gruppi di risposte</span><span class="sxs-lookup"><span data-stu-id="6c2d9-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c2d9-141">Può configurare:</span><span class="sxs-lookup"><span data-stu-id="6c2d9-141">Can configure:</span></span></th>
<th><span data-ttu-id="6c2d9-142">Può creare, eliminare o configurare:</span><span class="sxs-lookup"><span data-stu-id="6c2d9-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="6c2d9-143">Non</span><span class="sxs-lookup"><span data-stu-id="6c2d9-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="6c2d9-144">Agenti</span><span class="sxs-lookup"><span data-stu-id="6c2d9-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-145">Messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="6c2d9-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-146">Nome del gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="6c2d9-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c2d9-147">Description</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-148">Numero di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="6c2d9-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-149">Orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="6c2d9-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-150">Musica in attesa</span><span class="sxs-lookup"><span data-stu-id="6c2d9-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-151">Stato (attivo/inattivo)</span><span class="sxs-lookup"><span data-stu-id="6c2d9-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-152">Cercare flussi di lavoro di gruppo o flussi di lavoro IVR (Interactive Voice Response)</span><span class="sxs-lookup"><span data-stu-id="6c2d9-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6c2d9-153">Gruppi di agenti</span><span class="sxs-lookup"><span data-stu-id="6c2d9-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-154">Code</span><span class="sxs-lookup"><span data-stu-id="6c2d9-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-155">Set di festività</span><span class="sxs-lookup"><span data-stu-id="6c2d9-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6c2d9-156">Creare o eliminare qualsiasi tipo di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6c2d9-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="6c2d9-157">Modificare le impostazioni del gruppo di risposte di base, ad esempio: <strong>URI SIP</strong>, <strong>numero di telefono</strong>o <strong>tipo di flusso di lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c2d9-158">I responsabili del gruppo di risposte possono usare gli strumenti seguenti per gestire i gruppi di risposta designati.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="6c2d9-159">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6c2d9-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c2d9-160">I responsabili dei gruppi di risposte possono gestire solo le impostazioni di Response Group con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="6c2d9-161">Le altre impostazioni di Lync Server non sono disponibili per i responsabili.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="6c2d9-162">Strumento di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="6c2d9-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="6c2d9-163">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6c2d9-163">Lync Server Management Shell</span></span>

<span data-ttu-id="6c2d9-164">Il gruppo di risposte si adatta bene agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, vedere [pianificazione della capacità per il gruppo di risposte in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e può essere distribuito in installazioni di telefonia completamente nuove.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="6c2d9-165">Supporta le chiamate in arrivo dalla distribuzione VoIP aziendale e dalla rete di vettori locali.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="6c2d9-166">Gli agenti possono usare Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="6c2d9-167">L'applicazione Response Group è un componente di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="6c2d9-168">Quando si distribuisce VoIP aziendale, l'applicazione Response Group viene installata e attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c2d9-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

