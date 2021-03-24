---
title: Creare o modificare un gruppo di agenti in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Creare o modificare un gruppo di agenti in Response Group, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 0c0e7d54008ba6affa2bae5bd3228c93e430a114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105812"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="8ca29-103">Creare o modificare un gruppo di agenti in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ca29-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="8ca29-104">Creare o modificare un gruppo di agenti in Response Group, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8ca29-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8ca29-105">Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare impostazioni aggiuntive per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettervisi.</span><span class="sxs-lookup"><span data-stu-id="8ca29-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="8ca29-106">Un agente che deve accedere e disconnettersi dal gruppo, diverso dall'accesso o dalla disconnessione da Skype for Business, è definito agente formale.</span><span class="sxs-lookup"><span data-stu-id="8ca29-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="8ca29-107">Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="8ca29-108">Questo requisito può rivelarsi utile per gli agenti che rispondono alle chiamate provenienti dal gruppo a tempo parziale.</span><span class="sxs-lookup"><span data-stu-id="8ca29-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="8ca29-109">Gli agenti formali eseguono l'accesso e la disconnessione dai propri gruppi facendo clic su una voce di menu in Skype for Business per aprire il browser Internet di Windows Internet Explorer e visualizzare una console della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="8ca29-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="8ca29-110">Un agente che non esegue l'accesso o la disconnessione dal gruppo viene definito agente informale.</span><span class="sxs-lookup"><span data-stu-id="8ca29-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="8ca29-111">Gli agenti informali vengono automaticamente connessi al gruppo quando a loro volta a Skype for Business e non possono disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="8ca29-p103">Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="8ca29-114">Utilizzare una delle procedure seguenti per creare o modificare un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="8ca29-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8ca29-p104">Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="8ca29-118">Per usare il Pannello di controllo di Skype for Business Server per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="8ca29-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="8ca29-119">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="8ca29-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8ca29-120">Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi da utilizzare nei flussi di lavoro da gestire.</span><span class="sxs-lookup"><span data-stu-id="8ca29-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="8ca29-121">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ca29-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8ca29-122">Sulla barra di navigazione sinistra fare clic su **Response Group** e quindi su **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="8ca29-123">Nella pagina **Gruppo** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ca29-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="8ca29-p105">Per creare un nuovo gruppo di agenti, fare clic su **Nuovo**. Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** in cui si desidera aggiungere il gruppo. Nell'elenco di servizi visualizzato fare clic su quello desiderato e quindi premere **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="8ca29-p106">Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca. Nell'elenco dei risultati di ricerca fare clic sul gruppo desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8ca29-129">Nel campo **Nome** digitare il nome da assegnare al gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="8ca29-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="8ca29-130">Nel campo **Descrizione** digitare una descrizione per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="8ca29-131">Nel campo **Criteri di partecipazione** selezionare una delle opzioni indicate di seguito per impostare il comportamento di accesso per il gruppo:</span><span class="sxs-lookup"><span data-stu-id="8ca29-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="8ca29-132">Selezionare **Informale** per specificare che gli agenti del gruppo non devono connettersi e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="8ca29-133">Gli agenti vengono automaticamente connessi al gruppo quando a loro volta a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8ca29-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="8ca29-134">Selezionare **Formale** per specificare che gli agenti inclusi nel gruppo devono eseguire l'accesso e la disconnessione dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="8ca29-135">Quando si seleziona questa opzione, gli agenti selezionano una voce di menu in Skype for Business per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ca29-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="8ca29-136">In **Tempo per avviso (secondi)** specificare il numero di secondi per l'invio di uno squillo a un agente prima che la chiamata venga inoltrata al successivo agente disponibile (il valore predefinito è 20 secondi).</span><span class="sxs-lookup"><span data-stu-id="8ca29-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ca29-p109">L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il massimo tempo di attesa consentito.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="8ca29-139">In **Metodo di routing** selezionare il metodo per il routing delle chiamate agli agenti del gruppo, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8ca29-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="8ca29-140">Per offrire una nuova chiamata prima all'agente che è rimasto inattivo più a lungo (ha avuto una presenza di **Disponibile** o **Inattivo** in Skype for Business il più lungo), fare clic su **Inattività più lunga**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="8ca29-p110">Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, fare clic su **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="8ca29-143">Per inoltrare una nuova chiamata a ogni agente a turno, fare clic su **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="8ca29-144">Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, fare clic su **Seriale**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="8ca29-145">Per offrire una nuova chiamata a tutti gli agenti connessi contemporaneamente a Skype for Business e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **Operatore.**</span><span class="sxs-lookup"><span data-stu-id="8ca29-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="8ca29-146">Gli utenti configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="8ca29-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="8ca29-147">La chiamata viene inviata al primo agente che la accetta, dopo di che gli altri agenti non vedono più la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ca29-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="8ca29-148">In **Agenti** specificare in che modo si desidera creare l'elenco degli agenti:</span><span class="sxs-lookup"><span data-stu-id="8ca29-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="8ca29-149">Per utilizzare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ca29-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="8ca29-p112">Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**, nel campo di ricerca **Seleziona agenti** digitare tutto o parte del nome dell'utente desiderato e quindi fare clic su **Trova**. Nell'elenco di agenti risultante fare clic sull'utente e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="8ca29-152">Per rimuovere un utente dal gruppo di agenti, nell'elenco di agenti fare clic sull'utente desiderato e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="8ca29-153">Per modificare l'ordine in cui vengono inoltrate le chiamate agli agenti nei gruppi con il routing round robin o seriale, nell'elenco degli agenti fare clic su un utente e quindi sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="8ca29-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="8ca29-154">Per utilizzare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente** e quindi in **Indirizzo lista di distribuzione** digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8ca29-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="8ca29-155">Se si utilizza una lista di distribuzione di posta elettronica, verranno applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ca29-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="8ca29-p113">Non è possibile selezionare più liste di distribuzione per il gruppo di agenti. Ogni gruppo supporta una sola lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="8ca29-158">Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non verranno aggiunti all'elenco di agenti.</span><span class="sxs-lookup"><span data-stu-id="8ca29-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="8ca29-159">Se è selezionato il routing seriale o round robin, il server inoltra una chiamata in arrivo all'agente appropriato in base al metodo di routing e all'ordine con cui sono elencati gli agenti nella lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8ca29-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="8ca29-160">Se la lista di distribuzione contiene utenti per i quali Lync Server 2010 è abilitato ma VoIP aziendale non è abilitato, questi verranno aggiunti al gruppo di agenti come agenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="8ca29-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="8ca29-161">Assicurarsi che tutti i membri della lista di distribuzione VoIP aziendale abilitati per i propri account utente.</span><span class="sxs-lookup"><span data-stu-id="8ca29-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ca29-162">Se si utilizza una lista di distribuzione di posta elettronica, le appartenenze nascoste o le liste nascoste potrebbero diventare visibili all'amministratore o agli utenti di Response Group.</span><span class="sxs-lookup"><span data-stu-id="8ca29-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="8ca29-163">Per rendere visibili le appartenenze nascoste o gli elenchi nascosti, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8ca29-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="8ca29-164">Se una lista di distribuzione è stata configurata in modo che l'appartenenza sia nascosta e l'amministratore di Response Group assegna la lista di distribuzione alla lista di distribuzione, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.</span><span class="sxs-lookup"><span data-stu-id="8ca29-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="8ca29-165">Se una lista di distribuzione è stata configurata in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore di Response Group potrebbe essere in grado di visualizzare la lista di distribuzione e assegnarla all'elenco degli agenti se il processo di Response Group dispone delle autorizzazioni e dei diritti utente appropriati, anche se l'amministratore non dispone delle autorizzazioni e dei diritti utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="8ca29-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="8ca29-166">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8ca29-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="8ca29-167">Per utilizzare Skype for Business Server Management Shell per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="8ca29-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="8ca29-168">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="8ca29-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="8ca29-169">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="8ca29-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8ca29-170">Utilizzare **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="8ca29-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="8ca29-171">Utilizzare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente.</span><span class="sxs-lookup"><span data-stu-id="8ca29-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="8ca29-172">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8ca29-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="8ca29-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8ca29-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="8ca29-p116">L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il tempo massimo di attesa consentito.</span><span class="sxs-lookup"><span data-stu-id="8ca29-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="8ca29-p117">Verificare che il gruppo di agenti sia stato creato. Eseguire:</span><span class="sxs-lookup"><span data-stu-id="8ca29-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="8ca29-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ca29-178">See also</span></span>

[<span data-ttu-id="8ca29-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8ca29-179">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="8ca29-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="8ca29-180">New-CsRgsAgentGroup</span></span>](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="8ca29-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="8ca29-181">Set-CsRgsAgentGroup</span></span>](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="8ca29-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="8ca29-182">Get-CsRgsAgentGroup</span></span>](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)