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
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="94e7a-102">Creare o modificare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94e7a-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94e7a-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="94e7a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="94e7a-104">Per creare o modificare un gruppo di agenti, usare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94e7a-105">Un amministratore, ad esempio CsVoiceAdministrator, deve abilitare gli utenti per Enterprise Voice e Lync Server prima che gli utenti possano essere assegnati a gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="94e7a-106">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e usare i gruppi di agenti nei flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94e7a-107">Quando si assegnano gli utenti come agenti del gruppo di risposta, informarli che, se la modalità di privacy è abilitata, devono cercare i contatti "RGS Presence Watcher" e aggiungerli al proprio elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-107">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="94e7a-108">Gli agenti che hanno abilitato la modalità privacy, ma che non hanno "Watcher presenza RGS" nell'elenco contatti, non possono ricevere chiamate al Response Group.</span><span class="sxs-lookup"><span data-stu-id="94e7a-108">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="94e7a-109">Gli agenti che non hanno la modalità di privacy abilitata non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="94e7a-109">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="94e7a-110">Per usare il pannello di controllo di Lync Server per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="94e7a-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="94e7a-111">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="94e7a-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94e7a-112">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare gruppi e usarli nei flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="94e7a-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94e7a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94e7a-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94e7a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94e7a-115">Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su **raggruppa**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="94e7a-116">Nella pagina del **gruppo** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94e7a-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="94e7a-117">Per creare un nuovo gruppo di agenti, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="94e7a-118">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** in cui si vuole aggiungere il gruppo.</span><span class="sxs-lookup"><span data-stu-id="94e7a-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="94e7a-119">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="94e7a-120">Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="94e7a-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="94e7a-121">Nell'elenco risultante fare clic sul gruppo desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="94e7a-122">In **nome**Digitare un nome identificativo per il gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="94e7a-123">In **Descrizione**Digitare una descrizione per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="94e7a-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="94e7a-124">Nei **criteri di partecipazione**selezionare una delle opzioni seguenti per configurare il comportamento di accesso per il gruppo:</span><span class="sxs-lookup"><span data-stu-id="94e7a-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="94e7a-125">Selezionare **informale** per specificare che gli agenti del gruppo non devono eseguire l'accesso e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="94e7a-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="94e7a-126">Gli agenti hanno eseguito l'accesso automatico al gruppo quando accedono a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94e7a-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="94e7a-127">Selezionare **formale** per specificare che gli agenti del gruppo devono accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="94e7a-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="94e7a-128">Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu in Lync per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="94e7a-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="94e7a-129">In **tempo di avviso (secondi)** specificare il numero di secondi per chiamare un agente prima di offrire la chiamata al successivo agente disponibile (il valore predefinito è 20 secondi).</span><span class="sxs-lookup"><span data-stu-id="94e7a-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94e7a-130">L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="94e7a-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="94e7a-131">Se il tempo di avviso dell'agente supera 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.</span><span class="sxs-lookup"><span data-stu-id="94e7a-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="94e7a-132">In **metodo di routing**selezionare il metodo per il routing delle chiamate agli agenti nel gruppo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="94e7a-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="94e7a-133">Per offrire una nuova chiamata prima all'agente che è stato inattivo più a lungo (ha avuto una presenza di **disponibile** o **inattivo** in Lync Server il più lungo), fare clic su **inattivo più lungo**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="94e7a-134">Per offrire una nuova chiamata a tutti gli agenti disponibili simultaneamente, fare clic su **parallelo**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-134">To offer a new call to all available agents at the same time, click **Parallel**.</span></span> <span data-ttu-id="94e7a-135">La chiamata verrà inviata al primo agente che la accetta.</span><span class="sxs-lookup"><span data-stu-id="94e7a-135">The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="94e7a-136">Per offrire una nuova chiamata a ogni agente, fare clic su **Round Robin**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="94e7a-137">Per offrire sempre una nuova chiamata agli agenti nell'ordine in cui sono elencate nell'elenco **agente** , fare clic su **seriale**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="94e7a-138">Per offrire una nuova chiamata a tutti gli agenti che hanno effettuato l'accesso contemporaneamente a Lync Server 2013 e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **Assistente**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="94e7a-139">Gli utenti di Lync 2010 Attendant configurati come agenti possono vedere tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="94e7a-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="94e7a-140">La chiamata viene inviata al primo agente che lo accetta, dopodiché gli altri utenti del supervisore di Lync 2010 non vedranno più la chiamata.</span><span class="sxs-lookup"><span data-stu-id="94e7a-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="94e7a-141">In **agenti**specificare come si vuole creare l'elenco agenti:</span><span class="sxs-lookup"><span data-stu-id="94e7a-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="94e7a-142">Per usare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato**ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94e7a-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="94e7a-143">Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**e quindi nel campo **Seleziona agenti** di ricerca digitare tutto o parte del nome dell'utente che si vuole aggiungere al gruppo e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="94e7a-144">Nell'elenco di agenti risultante fare clic sull'utente e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="94e7a-145">Per rimuovere un utente dal gruppo agente, nell'elenco di agenti fare clic sull'utente da rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="94e7a-146">Per modificare l'ordine in cui gli agenti vengono offerti chiamate in gruppi che usano il routing o l'instradamento seriale di Round Robin, nell'elenco di agenti fare clic su un utente e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="94e7a-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="94e7a-147">Per usare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente**e quindi, nell' **indirizzo della lista di distribuzione**, digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94e7a-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="94e7a-148">Se si usa una lista di distribuzione di posta elettronica, si è soggetti ai vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94e7a-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="94e7a-149">Non è possibile selezionare più liste di distribuzione per il gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-149">You cannot select multiple distribution lists for the agent group.</span></span> <span data-ttu-id="94e7a-150">Ogni gruppo supporta solo una singola lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="94e7a-150">Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="94e7a-151">Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non vengono aggiunti all'elenco di agenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="94e7a-152">Se è selezionata l'opzione routing seriale o Round Robin, il server offre una chiamata in arrivo all'agente appropriato in base al metodo di routing e in base all'ordine in cui gli agenti sono elencati nella lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="94e7a-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="94e7a-153">Se la lista di distribuzione contiene utenti per cui è abilitato Lync Server 2010 ma VoIP aziendale non è abilitato, verranno aggiunti al gruppo agente come agenti disfunzionali.</span><span class="sxs-lookup"><span data-stu-id="94e7a-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="94e7a-154">Assicurarsi che tutti i membri della lista di distribuzione abbiano abilitato VoIP aziendale per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="94e7a-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="94e7a-155">Se si usa una lista di distribuzione di posta elettronica, le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili per l'amministratore del gruppo di risposte o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="94e7a-156">Le appartenenze nascoste o gli elenchi nascosti possono diventare visibili come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="94e7a-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="94e7a-157">Se è stata configurata una lista di distribuzione in modo che l'appartenenza sia nascosta e l'amministratore del gruppo di risposte assegna la lista di distribuzione all'elenco di agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.</span><span class="sxs-lookup"><span data-stu-id="94e7a-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="94e7a-158">Se è stata configurata una lista di distribuzione in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore del gruppo di risposte potrebbe essere in grado di vedere la lista di distribuzione e assegnarla all'elenco di agenti se il processo del gruppo di risposta ha i diritti utente appropriati e autorizzazioni, anche se l'amministratore non dispone dei diritti utente e delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="94e7a-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="94e7a-159">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="94e7a-160">Per usare Windows PowerShell per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="94e7a-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="94e7a-161">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="94e7a-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="94e7a-162">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="94e7a-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="94e7a-163">USA **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="94e7a-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="94e7a-164">Usare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente.</span><span class="sxs-lookup"><span data-stu-id="94e7a-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="94e7a-165">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="94e7a-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="94e7a-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="94e7a-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94e7a-167">L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="94e7a-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="94e7a-168">Se il tempo di avviso dell'agente è maggiore di 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.</span><span class="sxs-lookup"><span data-stu-id="94e7a-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="94e7a-169">Verificare che il gruppo di agenti sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="94e7a-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="94e7a-170">Eseguire</span><span class="sxs-lookup"><span data-stu-id="94e7a-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94e7a-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e7a-171">See Also</span></span>


[<span data-ttu-id="94e7a-172">Eliminare un gruppo di agenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94e7a-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="94e7a-173">Gestione dei gruppi di agenti di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94e7a-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="94e7a-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="94e7a-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="94e7a-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="94e7a-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="94e7a-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="94e7a-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="94e7a-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="94e7a-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

