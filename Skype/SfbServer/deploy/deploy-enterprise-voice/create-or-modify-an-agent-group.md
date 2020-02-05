---
title: Creare o modificare un gruppo di agenti in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 0b496160f00cde80364c0f81c150392405ef7768
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767759"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="cf9f3-103">Creare o modificare un gruppo di agenti in Skype for business</span><span class="sxs-lookup"><span data-stu-id="cf9f3-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="cf9f3-104">Creare o modificare un gruppo di agenti in Response Group, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cf9f3-105">Quando si crea un gruppo di agenti, si selezionano gli agenti assegnati al gruppo e si specificano altre impostazioni di gruppo, ad esempio il metodo di routing, e se un agente può accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="cf9f3-106">Un agente che deve accedere e disconnettersi dal gruppo, che è diverso dall'accesso o da Skype for business, si chiama agente formale.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="cf9f3-107">Gli agenti formali devono essere connessi al gruppo prima che possano ricevere le chiamate instradate al gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="cf9f3-108">Può essere utile per gli agenti che rispondono alle chiamate dal gruppo in base a tempo parziale.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="cf9f3-109">Gli agenti formali entrano e espongono i loro gruppi facendo clic su una voce di menu in Skype for business per aprire il browser Internet di Windows Internet Explorer e visualizzare una console della pagina Web.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="cf9f3-110">Un agente che non esegue l'accesso o fuori dal gruppo viene chiamato agente informale.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="cf9f3-111">Gli agenti informali vengono automaticamente connessi al gruppo quando accedono a Skype for business e non possono disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="cf9f3-112">Solo gli utenti locali possono essere agenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="cf9f3-113">Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="cf9f3-114">Per creare o modificare un gruppo di agenti, usare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cf9f3-115">Quando si assegnano gli utenti come agenti del gruppo di risposta, informarli che, se la modalità di privacy è abilitata, devono cercare i contatti "RGS Presence Watcher" e aggiungerli al proprio elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-115">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="cf9f3-116">Gli agenti che hanno abilitato la modalità privacy, ma che non hanno "Watcher presenza RGS" nell'elenco contatti, non possono ricevere chiamate al Response Group.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-116">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="cf9f3-117">Gli agenti che non hanno la modalità di privacy abilitata non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-117">Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="cf9f3-118">Per usare il pannello di controllo di Skype for Business Server per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="cf9f3-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="cf9f3-119">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf9f3-120">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare gruppi e usarli nei flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="cf9f3-121">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cf9f3-122">Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su **raggruppa**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="cf9f3-123">Nella pagina del **gruppo** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="cf9f3-124">Per creare un nuovo gruppo di agenti, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-124">To create a new agent group, click **New**.</span></span> <span data-ttu-id="cf9f3-125">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** in cui si vuole aggiungere il gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-125">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="cf9f3-126">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-126">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="cf9f3-127">Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-127">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="cf9f3-128">Nell'elenco risultante fare clic sul gruppo desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-128">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cf9f3-129">In **nome**Digitare un nome identificativo per il gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="cf9f3-130">In **Descrizione**Digitare una descrizione per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="cf9f3-131">Nei **criteri di partecipazione**selezionare una delle opzioni seguenti per configurare il comportamento di accesso per il gruppo:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="cf9f3-132">Selezionare **informale** per specificare che gli agenti del gruppo non devono eseguire l'accesso e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="cf9f3-133">Gli agenti vengono automaticamente registrati al gruppo quando accedono a Skype for business.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="cf9f3-134">Selezionare **formale** per specificare che gli agenti del gruppo devono accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="cf9f3-135">Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu in Skype for business per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="cf9f3-136">In **tempo di avviso (secondi)** specificare il numero di secondi per chiamare un agente prima di offrire la chiamata al successivo agente disponibile (il valore predefinito è 20 secondi).</span><span class="sxs-lookup"><span data-stu-id="cf9f3-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cf9f3-137">L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-137">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="cf9f3-138">Se il tempo di avviso dell'agente supera 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-138">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="cf9f3-139">In **metodo di routing**selezionare il metodo per il routing delle chiamate agli agenti nel gruppo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="cf9f3-140">Per offrire una nuova chiamata prima all'agente che è stato inattivo il più lungo (ha avuto una presenza di **disponibile** o **inattivo** in Skype for business il più lungo), fare clic su **inattivo più lungo**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="cf9f3-141">Per offrire una nuova chiamata a tutti gli agenti disponibili simultaneamente, fare clic su **parallelo**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-141">To offer a new call to all available agents at the same time, click **Parallel**.</span></span> <span data-ttu-id="cf9f3-142">La chiamata verrà inviata al primo agente che la accetta.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-142">The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="cf9f3-143">Per offrire una nuova chiamata a ogni agente, fare clic su **Round Robin**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="cf9f3-144">Per offrire sempre una nuova chiamata agli agenti nell'ordine in cui sono elencate nell'elenco **agente** , fare clic su **seriale**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="cf9f3-145">Per offrire una nuova chiamata a tutti gli agenti che hanno effettuato l'accesso contemporaneamente a Skype for business e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **Assistente**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="cf9f3-146">Gli utenti configurati come agenti possono vedere tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="cf9f3-147">La chiamata viene inviata al primo agente che lo accetta, dopodiché gli altri agenti non vedranno più la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="cf9f3-148">In **agenti**specificare come si vuole creare l'elenco agenti:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="cf9f3-149">Per usare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato**ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="cf9f3-150">Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**e quindi nel campo **Seleziona agenti** di ricerca digitare tutto o parte del nome dell'utente che si vuole aggiungere al gruppo e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-150">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="cf9f3-151">Nell'elenco di agenti risultante fare clic sull'utente e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-151">In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="cf9f3-152">Per rimuovere un utente dal gruppo agente, nell'elenco di agenti fare clic sull'utente da rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="cf9f3-153">Per modificare l'ordine in cui gli agenti vengono offerti chiamate in gruppi che usano il routing o l'instradamento seriale di Round Robin, nell'elenco di agenti fare clic su un utente e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="cf9f3-154">Per usare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente**e quindi, nell' **indirizzo della lista di distribuzione**, digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="cf9f3-155">Se si usa una lista di distribuzione di posta elettronica, si è soggetti ai vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="cf9f3-156">Non è possibile selezionare più liste di distribuzione per il gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-156">You cannot select multiple distribution lists for the agent group.</span></span> <span data-ttu-id="cf9f3-157">Ogni gruppo supporta solo una singola lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-157">Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="cf9f3-158">Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non vengono aggiunti all'elenco di agenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="cf9f3-159">Se è selezionata l'opzione routing seriale o Round Robin, il server offre una chiamata in arrivo all'agente appropriato in base al metodo di routing e in base all'ordine in cui gli agenti sono elencati nella lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="cf9f3-160">Se la lista di distribuzione contiene utenti per cui è abilitato Lync Server 2010 ma VoIP aziendale non è abilitato, verranno aggiunti al gruppo agente come agenti disfunzionali.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="cf9f3-161">Assicurarsi che tutti i membri della lista di distribuzione abbiano abilitato VoIP aziendale per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cf9f3-162">Se si usa una lista di distribuzione di posta elettronica, le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili per l'amministratore del gruppo di risposte o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="cf9f3-163">Le appartenenze nascoste o gli elenchi nascosti possono diventare visibili come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="cf9f3-164">Se è stata configurata una lista di distribuzione in modo che l'appartenenza sia nascosta e l'amministratore del gruppo di risposte assegna la lista di distribuzione all'elenco di agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="cf9f3-165">Se è stata configurata una lista di distribuzione in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore del gruppo di risposte potrebbe essere in grado di vedere la lista di distribuzione e assegnarla all'elenco di agenti se il processo del gruppo di risposta ha i diritti utente appropriati e autorizzazioni, anche se l'amministratore non dispone dei diritti utente e delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="cf9f3-166">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="cf9f3-167">Per usare Skype for Business Server Management Shell per creare o modificare un gruppo di agenti</span><span class="sxs-lookup"><span data-stu-id="cf9f3-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="cf9f3-168">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="cf9f3-169">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="cf9f3-170">USA **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="cf9f3-171">Usare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="cf9f3-172">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="cf9f3-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="cf9f3-174">L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-174">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="cf9f3-175">Se il tempo di avviso dell'agente è maggiore di 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-175">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="cf9f3-176">Verificare che il gruppo di agenti sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-176">Confirm that the agent group is created.</span></span> <span data-ttu-id="cf9f3-177">Eseguire</span><span class="sxs-lookup"><span data-stu-id="cf9f3-177">Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="cf9f3-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf9f3-178">See also</span></span>

[<span data-ttu-id="cf9f3-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="cf9f3-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="cf9f3-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cf9f3-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="cf9f3-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cf9f3-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="cf9f3-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cf9f3-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
