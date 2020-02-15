---
title: 'Lync Server 2013: creare o modificare un gruppo di agenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cd385c5310a5b2df01127e870861fa83231d6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="b115d-102">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b115d-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b115d-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="b115d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="b115d-104">Utilizzare una delle procedure seguenti per creare o modificare un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="b115d-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b115d-105">Un amministratore, ad esempio CsVoiceAdministrator, deve abilitare gli utenti per VoIP aziendale e Lync Server prima che gli utenti possano essere assegnati ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="b115d-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="b115d-106">Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi di agenti da utilizzare nei flussi di lavoro da gestire.</span><span class="sxs-lookup"><span data-stu-id="b115d-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b115d-p102">Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy.</span><span class="sxs-lookup"><span data-stu-id="b115d-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="b115d-110">Per utilizzare il pannello di controllo di Lync Server per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="b115d-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="b115d-111">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="b115d-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b115d-112">Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi da utilizzare nei flussi di lavoro da gestire.</span><span class="sxs-lookup"><span data-stu-id="b115d-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="b115d-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b115d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b115d-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b115d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b115d-115">Sulla barra di navigazione sinistra fare clic su **Response Group** e quindi su **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b115d-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="b115d-116">Nella pagina **Gruppo** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b115d-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b115d-p104">Per creare un nuovo gruppo di agenti, fare clic su **Nuovo**. Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** in cui si desidera aggiungere il gruppo. Nell'elenco di servizi visualizzato fare clic su quello desiderato e quindi premere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b115d-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b115d-p105">Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca. Nell'elenco dei risultati di ricerca fare clic sul gruppo desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b115d-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b115d-122">Nel campo **Nome** digitare il nome da assegnare al gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="b115d-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="b115d-123">Nel campo **Descrizione** digitare una descrizione per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="b115d-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="b115d-124">Nel campo **Criteri di partecipazione** selezionare una delle opzioni indicate di seguito per impostare il comportamento di accesso per il gruppo:</span><span class="sxs-lookup"><span data-stu-id="b115d-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="b115d-125">Selezionare **Informale** per specificare che gli agenti del gruppo non devono connettersi e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="b115d-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="b115d-126">Gli agenti vengono automaticamente connessi al gruppo quando eseguono l'accesso a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b115d-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="b115d-127">Selezionare **Formale** per specificare che gli agenti inclusi nel gruppo devono eseguire l'accesso e la disconnessione dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="b115d-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="b115d-128">Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu in Lync per aprire Internet Explorer e visualizzare una console di pagina Web per l'accesso e la disconnessione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b115d-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="b115d-129">In **Tempo per avviso (secondi)** specificare il numero di secondi per l'invio di uno squillo a un agente prima che la chiamata venga inoltrata al successivo agente disponibile (il valore predefinito è 20 secondi).</span><span class="sxs-lookup"><span data-stu-id="b115d-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b115d-p108">L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il massimo tempo di attesa consentito.</span><span class="sxs-lookup"><span data-stu-id="b115d-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="b115d-132">In **Metodo di routing** selezionare il metodo per il routing delle chiamate agli agenti del gruppo, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b115d-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="b115d-133">Per offrire una nuova chiamata prima all'agente che è stato inattivo più a lungo (ha avuto una presenza **disponibile** o **inattivo** in Lync Server più a lungo), fare clic su **inattività più lunga**.</span><span class="sxs-lookup"><span data-stu-id="b115d-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="b115d-p109">Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, fare clic su **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.</span><span class="sxs-lookup"><span data-stu-id="b115d-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="b115d-136">Per inoltrare una nuova chiamata a ogni agente a turno, fare clic su **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="b115d-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="b115d-137">Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, fare clic su **Seriale**.</span><span class="sxs-lookup"><span data-stu-id="b115d-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="b115d-138">Per offrire una nuova chiamata a tutti gli agenti che hanno eseguito l'accesso contemporaneamente a Lync Server 2013 e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **operatore**.</span><span class="sxs-lookup"><span data-stu-id="b115d-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="b115d-139">Gli utenti di Lync 2010 Attendant che sono configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="b115d-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="b115d-140">La chiamata viene inviata al primo agente che lo accetta, dopo il quale gli altri utenti dell'operatore di Lync 2010 non vedranno più la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b115d-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="b115d-141">In **Agenti** specificare in che modo si desidera creare l'elenco degli agenti:</span><span class="sxs-lookup"><span data-stu-id="b115d-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="b115d-142">Per utilizzare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b115d-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="b115d-p111">Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**, nel campo di ricerca **Seleziona agenti** digitare tutto o parte del nome dell'utente desiderato e quindi fare clic su **Trova**. Nell'elenco di agenti risultante fare clic sull'utente e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b115d-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="b115d-145">Per rimuovere un utente dal gruppo di agenti, nell'elenco di agenti fare clic sull'utente desiderato e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="b115d-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="b115d-146">Per modificare l'ordine in cui vengono inoltrate le chiamate agli agenti nei gruppi con il routing round robin o seriale, nell'elenco degli agenti fare clic su un utente e quindi sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="b115d-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="b115d-147">Per utilizzare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente** e quindi in **Indirizzo lista di distribuzione** digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b115d-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="b115d-148">Se si utilizza una lista di distribuzione di posta elettronica, verranno applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b115d-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="b115d-p112">Non è possibile selezionare più liste di distribuzione per il gruppo di agenti. Ogni gruppo supporta una sola lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b115d-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="b115d-151">Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non verranno aggiunti all'elenco di agenti.</span><span class="sxs-lookup"><span data-stu-id="b115d-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="b115d-152">Se è selezionato il routing seriale o round robin, il server inoltra una chiamata in arrivo all'agente appropriato in base al metodo di routing e all'ordine con cui sono elencati gli agenti nella lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b115d-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="b115d-153">Se la lista di distribuzione contiene gli utenti per i quali è abilitato Lync Server 2010 ma VoIP aziendale non è abilitato, verrà aggiunto al gruppo di agenti come agente disfunzionale.</span><span class="sxs-lookup"><span data-stu-id="b115d-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="b115d-154">Assicurarsi che tutti i membri della lista di distribuzione abbiano abilitato VoIP aziendale per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="b115d-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b115d-155">Se si utilizza una lista di distribuzione di posta elettronica, le appartenenze nascoste o gli elenchi nascosti possono diventare visibili per l'amministratore o gli utenti di Response Group.</span><span class="sxs-lookup"><span data-stu-id="b115d-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="b115d-156">Per rendere visibili le appartenenze nascoste o gli elenchi nascosti, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b115d-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="b115d-157">Se una lista di distribuzione è stata configurata in modo che l'appartenenza sia nascosta e che l'amministratore di Response Group assegni la lista di distribuzione all'elenco degli agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.</span><span class="sxs-lookup"><span data-stu-id="b115d-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="b115d-158">Se una lista di distribuzione è stata configurata in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore del Response Group potrebbe essere in grado di visualizzare la lista di distribuzione e assegnarla all'elenco di agenti se il processo di Response Group ha i diritti utente e autorizzazioni, anche se l'amministratore non dispone dei diritti utente e delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="b115d-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="b115d-159">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b115d-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="b115d-160">Per utilizzare Windows PowerShell per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="b115d-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="b115d-161">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="b115d-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b115d-162">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b115d-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b115d-163">Utilizzare **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="b115d-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="b115d-164">Utilizzare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente.</span><span class="sxs-lookup"><span data-stu-id="b115d-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="b115d-165">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b115d-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="b115d-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b115d-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b115d-p115">L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il tempo massimo di attesa consentito.</span><span class="sxs-lookup"><span data-stu-id="b115d-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="b115d-p116">Verificare che il gruppo di agenti sia stato creato. Eseguire:</span><span class="sxs-lookup"><span data-stu-id="b115d-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b115d-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b115d-171">See Also</span></span>


[<span data-ttu-id="b115d-172">Eliminare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b115d-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="b115d-173">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b115d-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="b115d-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b115d-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b115d-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b115d-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="b115d-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b115d-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="b115d-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b115d-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

