---
title: Creare una coda di chiamata in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Scopri come configurare Sistema telefonico per le code di chiamata con Microsoft Teams, che fornisce un messaggio di saluto, la musica in attesa, il reindirizzamento delle chiamate e altre funzionalità.
ms.openlocfilehash: 8b4fe4283ac9734c1dc29bf33759039098578744
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064802"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="84d06-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="84d06-103">Create a call queue</span></span>

<span data-ttu-id="84d06-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="84d06-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="84d06-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="84d06-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="84d06-106">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="84d06-106">Call queues provide:</span></span>

- <span data-ttu-id="84d06-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="84d06-107">A greeting message.</span></span>

- <span data-ttu-id="84d06-108">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="84d06-109">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="84d06-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="84d06-110">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="84d06-111">Assicurarsi di aver letto Pianificare gli operatori automatici e [](plan-auto-attendant-call-queue.md#getting-started) le code di chiamata di [Teams](plan-auto-attendant-call-queue.md) e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="84d06-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="84d06-112">Per configurare una coda di chiamata, nell'interfaccia di amministrazione di Teams espandere **Voce,** fare clic su **Code di chiamata** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="84d06-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="84d06-113">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="84d06-113">Video demonstration</span></span>

<span data-ttu-id="84d06-114">Questo video mostra un esempio di base di come creare una coda di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="84d06-114">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="resource-account-and-language"></a><span data-ttu-id="84d06-115">Account e lingua delle risorse</span><span class="sxs-lookup"><span data-stu-id="84d06-115">Resource account and language</span></span>

![Screenshot delle impostazioni dell'account della risorsa e della lingua](media/call-queue-name-language.png)

1. <span data-ttu-id="84d06-117">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-117">Type a name for the call queue.</span></span>

2. <span data-ttu-id="84d06-118">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="84d06-118">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="84d06-119">Gli agenti visualizzano il nome dell'account della risorsa quando ricevono una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="84d06-119">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="84d06-120">Scegliere una [lingua supportata.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="84d06-120">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="84d06-121">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="84d06-121">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="84d06-122">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="84d06-122">Greetings and music on hold in queue</span></span>

<span data-ttu-id="84d06-123">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-123">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="84d06-124">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="84d06-124">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="84d06-125">Teams fornisce musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-125">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="84d06-126">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="84d06-126">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="84d06-127">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="84d06-127">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="84d06-128">La musica predefinita fornita nelle code di chiamata di Teams è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84d06-128">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="84d06-129">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="84d06-129">Call agents</span></span>

<span data-ttu-id="84d06-130">Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="84d06-130">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="84d06-132">Canale di Teams</span><span class="sxs-lookup"><span data-stu-id="84d06-132">Teams channel</span></span>

<span data-ttu-id="84d06-133">È possibile aggiungere fino a 200 agenti tramite un canale di Teams.</span><span class="sxs-lookup"><span data-stu-id="84d06-133">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="84d06-134">Se si vuole usare [un canale di Teams per gestire la coda,](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)selezionare l'opzione Scegli un **team** e fare clic su **Aggiungi canale.**</span><span class="sxs-lookup"><span data-stu-id="84d06-134">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="84d06-135">Cercare il team da usare, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="84d06-135">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="84d06-136">Selezionare il canale da usare e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="84d06-136">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="84d06-137">I client seguenti sono supportati quando si usa un canale di Teams per le code di chiamata:</span><span class="sxs-lookup"><span data-stu-id="84d06-137">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="84d06-138">Client Windows di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84d06-138">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="84d06-139">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="84d06-139">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="84d06-140">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="84d06-140">Users and groups</span></span>

<span data-ttu-id="84d06-141">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="84d06-141">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="84d06-142">Per aggiungere singoli utenti o gruppi alla coda, selezionare **l'opzione Scegli utenti e** gruppi.</span><span class="sxs-lookup"><span data-stu-id="84d06-142">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="84d06-143">Per aggiungere un utente alla coda, fare clic **su Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="84d06-143">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="84d06-144">Per aggiungere un gruppo alla coda, fare clic **su Aggiungi gruppi,** cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="84d06-144">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="84d06-145">È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="84d06-145">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="84d06-146">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore prima dell'arrivo della prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-146">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="84d06-147">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="84d06-147">Call routing</span></span>

![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="84d06-149">**La modalità conferenza** riduce significativamente il tempo necessario per la connessione di un chiamante a un agente, dopo che l'agente ha accettato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-149">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="84d06-150">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="84d06-150">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="84d06-151">La versione più recente del client desktop di Microsoft Teams, dell'app Android o dell'app iOS</span><span class="sxs-lookup"><span data-stu-id="84d06-151">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="84d06-152">Microsoft Teams phone version 1449/1.0.94.2020051601 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="84d06-152">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="84d06-153">Gli account di Teams degli agenti devono essere impostati sulla modalità Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="84d06-153">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="84d06-154">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="84d06-154">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="84d06-155">È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.</span><span class="sxs-lookup"><span data-stu-id="84d06-155">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="84d06-156">La modalità conferenza non è supportata se le chiamate telefoniche vengono instradati alla coda da un gateway di routing diretto abilitato per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="84d06-156">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="84d06-157">**Il metodo di** routing determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-157">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="84d06-158">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84d06-158">Choose from these options:</span></span>

- <span data-ttu-id="84d06-159">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="84d06-159">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="84d06-160">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-160">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="84d06-161">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **Agenti di** chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-161">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="84d06-162">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="84d06-162">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="84d06-163">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-163">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="84d06-164">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-164">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="84d06-165">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="84d06-165">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="84d06-166">Un agente è considerato inattivo se lo stato di presenza è Disponibile o se lo stato presenza è Stato Non al computer per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="84d06-166">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="84d06-167">Gli agenti il cui stato presenza è Stato Non al computer per più di 10 minuti non vengono considerati inattivi e non saranno idonei a ricevere chiamate finché non cambiano la propria presenza in Disponibile.</span><span class="sxs-lookup"><span data-stu-id="84d06-167">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](media/call-queue-presence-agents-time.png)


<span data-ttu-id="84d06-169">**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="84d06-169">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="84d06-170">Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="84d06-170">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="84d06-171">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="84d06-171">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="84d06-172">È possibile abilitare il routing delle chiamate basate sulla presenza con uno qualsiasi dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="84d06-172">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="84d06-173">Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate indipendentemente dal relativo stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="84d06-173">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="84d06-174">Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="84d06-174">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="84d06-175">Se hai agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="84d06-175">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="84d06-176">**Tempo di avviso agente** specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="84d06-176">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="84d06-177">Sono consigliate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84d06-177">The following settings are recommended:</span></span>

- <span data-ttu-id="84d06-178">**Modalità conferenza su** **Automatico**</span><span class="sxs-lookup"><span data-stu-id="84d06-178">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="84d06-179">**Metodo di instradamento** **a Round robin** o Più lungo **inattivo**</span><span class="sxs-lookup"><span data-stu-id="84d06-179">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="84d06-180">**Routing basato sulla presenza su** **On**</span><span class="sxs-lookup"><span data-stu-id="84d06-180">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="84d06-181">**Tempo di avviso dell'agente:** **a 20 secondi**</span><span class="sxs-lookup"><span data-stu-id="84d06-181">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="84d06-182">Se il routing basato sulla presenza non è abilitato e la coda contiene più chiamate, il sistema presenterà queste chiamate contemporaneamente agli agenti indipendentemente dal loro stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="84d06-182">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="84d06-183">In questo modo si riceveranno più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.</span><span class="sxs-lookup"><span data-stu-id="84d06-183">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="84d06-184">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="84d06-184">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="84d06-186">**Numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono essere in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="84d06-186">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="84d06-187">Il valore predefinito è 50, ma può essere compreso tra 0 e 200.</span><span class="sxs-lookup"><span data-stu-id="84d06-187">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="84d06-188">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione Quando viene raggiunto il numero massimo **di** chiamate.</span><span class="sxs-lookup"><span data-stu-id="84d06-188">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="84d06-189">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="84d06-189">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="84d06-190">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-190">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="84d06-191">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="84d06-191">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="84d06-192">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="84d06-192">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="84d06-193">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="84d06-193">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="84d06-195">**Timeout chiamata: il tempo di attesa** massimo specifica il tempo massimo di attesa di una chiamata in coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="84d06-195">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="84d06-196">È possibile specificare un valore compreso tra 0 secondi e 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="84d06-196">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="84d06-197">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="84d06-197">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="84d06-198">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="84d06-198">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="84d06-199">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="84d06-199">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="84d06-200">Dopo aver selezionato le opzioni di timeout della chiamata, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="84d06-200">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="84d06-201">ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="84d06-201">Caller ID for outbound calls</span></span>

<span data-ttu-id="84d06-202">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="84d06-202">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="84d06-203">Per altre informazioni, vedere Gestire [i criteri id chiamante in Microsoft Teams.](caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="84d06-203">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="84d06-204">Client supportati</span><span class="sxs-lookup"><span data-stu-id="84d06-204">Supported clients</span></span>

<span data-ttu-id="84d06-205">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="84d06-205">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="84d06-206">Client desktop Skype for Business 2016 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="84d06-206">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="84d06-207">Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="84d06-207">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="84d06-208">Tutti i modelli di telefono IP supportati per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="84d06-208">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="84d06-209">Vedere [Ottenere telefoni per Skype for Business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="84d06-209">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="84d06-210">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="84d06-210">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="84d06-211">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="84d06-211">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="84d06-212">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="84d06-212">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="84d06-213">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="84d06-213">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="84d06-214">Client Windows di Microsoft Teams (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="84d06-214">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="84d06-215">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="84d06-215">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="84d06-216">Microsoft Teams in [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="84d06-216">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="84d06-217">App Per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84d06-217">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="84d06-218">App Microsoft Teams per Android</span><span class="sxs-lookup"><span data-stu-id="84d06-218">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="84d06-219">Le code di chiamata a cui è assegnato un numero di instradamento diretto non supportano i client Skype for Business, i client Lync o i telefoni IP Skype for Business come agenti.</span><span class="sxs-lookup"><span data-stu-id="84d06-219">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="84d06-220">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="84d06-220">Call queue cmdlets</span></span>

<span data-ttu-id="84d06-221">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-221">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="84d06-222">Ecco i cmdlet che si usano per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="84d06-222">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="84d06-223">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="84d06-223">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="84d06-224">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="84d06-224">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="84d06-225">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="84d06-225">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="84d06-226">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="84d06-226">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="84d06-227">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="84d06-227">Related topics</span></span>

[<span data-ttu-id="84d06-228">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="84d06-228">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="84d06-229">[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="84d06-229">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="84d06-230">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="84d06-230">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="84d06-231">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="84d06-231">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="84d06-232">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="84d06-232">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
