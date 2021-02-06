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
description: Informazioni su come configurare il sistema telefonico per le code di chiamata con Microsoft teams, che offre un messaggio di saluto, detenere musica, reindirizzare le chiamate e altre funzionalità.
ms.openlocfilehash: 17e15e270492c4105f79ead6b2ce34ca37165ec3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125789"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="79a93-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="79a93-103">Create a call queue</span></span>

<span data-ttu-id="79a93-104">Le code di chiamata offrono un metodo per indirizzare i chiamanti alle persone dell'organizzazione che possono essere utili per un problema o una domanda particolare.</span><span class="sxs-lookup"><span data-stu-id="79a93-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="79a93-105">Le chiamate vengono distribuite una alla volta per gli utenti della coda (noti come *agenti*).</span><span class="sxs-lookup"><span data-stu-id="79a93-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="79a93-106">Le code di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="79a93-106">Call queues provide:</span></span>

- <span data-ttu-id="79a93-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="79a93-107">A greeting message.</span></span>

- <span data-ttu-id="79a93-108">Musica mentre gli utenti attendono il blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="79a93-109">Chiamata routing-in *First in, First out* (FIFO) Order-to Agents.</span><span class="sxs-lookup"><span data-stu-id="79a93-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="79a93-110">Opzioni di gestione per l'overflow e il timeout delle code.</span><span class="sxs-lookup"><span data-stu-id="79a93-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="79a93-111">Assicurarsi di aver letto [piano per gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md) e aver seguito i [passaggi introduttivi](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="79a93-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="79a93-112">Per configurare una coda di chiamata, nell'interfaccia di amministrazione di Team espandere **voce**, fare clic su **code di chiamata** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79a93-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="79a93-113">Account e lingua delle risorse</span><span class="sxs-lookup"><span data-stu-id="79a93-113">Resource account and language</span></span>

![Screenshot delle impostazioni dell'account delle risorse e della lingua](media/call-queue-name-language.png)

1. <span data-ttu-id="79a93-115">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-115">Type a name for the call queue.</span></span> <span data-ttu-id="79a93-116">Gli agenti vedranno questo nome quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="79a93-117">Fare clic su **Aggiungi account**, cercare l'account risorse che si vuole usare con la coda di chiamata, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79a93-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="79a93-118">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="79a93-118">Choose a language.</span></span> <span data-ttu-id="79a93-119">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="79a93-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="79a93-120">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="79a93-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="79a93-121">Specificare se si vuole riprodurre un saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="79a93-122">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto che si vuole riprodurre.</span><span class="sxs-lookup"><span data-stu-id="79a93-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="79a93-123">Teams offre musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="79a93-124">Se si vuole riprodurre un file audio specifico, scegliere **Riproduci un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="79a93-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="79a93-125">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="79a93-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="79a93-126">La musica predefinita fornita nelle code delle chiamate di teams è priva di qualsiasi royalties pagabile dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79a93-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="79a93-127">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="79a93-127">Call agents</span></span>

<span data-ttu-id="79a93-128">Per poter aggiungere agenti a una coda di chiamata, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) .</span><span class="sxs-lookup"><span data-stu-id="79a93-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

<span data-ttu-id="79a93-130">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="79a93-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="79a93-131">Per aggiungere un utente alla coda, fare clic su **Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79a93-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="79a93-132">Per aggiungere un gruppo alla coda, fare clic su **Aggiungi gruppi**, cercare il gruppo, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79a93-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="79a93-133">È possibile usare le liste di distribuzione, i gruppi di sicurezza e i gruppi Microsoft 365 o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="79a93-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="79a93-134">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore per la prima chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="79a93-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="79a93-135">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79a93-135">Call routing</span></span>

![Screenshot della modalità conferenza e delle impostazioni del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="79a93-137">La **modalità conferenza** riduce significativamente la quantità di tempo necessaria affinché un chiamante venga connesso a un agente, dopo che l'agente accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="79a93-138">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="79a93-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="79a93-139">La versione più recente di Microsoft teams desktop client, Android app o iOS app</span><span class="sxs-lookup"><span data-stu-id="79a93-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="79a93-140">Telefono Microsoft teams versione 1449/1.0.94.2020051601 o successiva</span><span class="sxs-lookup"><span data-stu-id="79a93-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="79a93-141">Gli account teams degli agenti devono essere impostati sulla modalità solo teams.</span><span class="sxs-lookup"><span data-stu-id="79a93-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="79a93-142">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79a93-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="79a93-143">È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti i client compatibili.</span><span class="sxs-lookup"><span data-stu-id="79a93-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="79a93-144">Il **metodo di routing** determina l'ordine in cui gli agenti ricevono chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="79a93-145">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79a93-145">Choose from these options:</span></span>

- <span data-ttu-id="79a93-146">Il **routing di Attendant** squilla tutti gli agenti della coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="79a93-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="79a93-147">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="79a93-148">Il **routing seriale** squilla tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **agenti di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="79a93-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="79a93-149">Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.</span><span class="sxs-lookup"><span data-stu-id="79a93-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="79a93-150">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="79a93-151">Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="79a93-152">Le rotte **inattive più lunghe** ogni chiamata all'agente che è stato inattivo il tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="79a93-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="79a93-153">Un agente viene considerato inattivo se lo stato presenza è disponibile o se lo stato presenza è stato assente per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="79a93-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="79a93-154">Gli agenti il cui stato di presenza è stato assente per più di 10 minuti non sono considerati inattivi e non sono idonei a ricevere chiamate finché non modificano la loro presenza in available.</span><span class="sxs-lookup"><span data-stu-id="79a93-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni di routing, disattivazione e ora di avviso](media/call-queue-presence-agents-time.png)


<span data-ttu-id="79a93-156">Il **routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="79a93-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="79a93-157">Gli agenti di chiamata il cui stato di disponibilità è impostato su **disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="79a93-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="79a93-158">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato sono esclusi dall'elenco di routing delle chiamate e non ricevono le chiamate finché il loro stato di disponibilità non torna a **disponibile**.</span><span class="sxs-lookup"><span data-stu-id="79a93-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="79a93-159">Puoi abilitare il routing delle chiamate basate sulla presenza con uno dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="79a93-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="79a93-160">Se un agente sceglie di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate, indipendentemente dal tipo di stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="79a93-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="79a93-161">Gli agenti che usano il client Skype for business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="79a93-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="79a93-162">Se si hanno agenti che usano Skype for business, non abilitare il routing delle chiamate basate sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="79a93-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="79a93-163">L' **ora di avviso dell'agente** specifica il tempo di squillo del telefono di un agente prima che la chiamata venga reindirizzata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="79a93-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="79a93-164">Per le code a volume elevato, è consigliabile seguire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79a93-164">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="79a93-165">**Modalità conferenza** per l' **auto**</span><span class="sxs-lookup"><span data-stu-id="79a93-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="79a93-166">**Metodo di routing** per il **routing di Attendant**</span><span class="sxs-lookup"><span data-stu-id="79a93-166">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="79a93-167">**Routing basato sulla presenza** **su** attivato</span><span class="sxs-lookup"><span data-stu-id="79a93-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="79a93-168">**Tempo di avviso agente:** a **20 secondi**</span><span class="sxs-lookup"><span data-stu-id="79a93-168">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="79a93-169">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79a93-169">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="79a93-171">**Massimo chiamate nella coda** specifica il numero massimo di chiamate che possono essere attese nella coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="79a93-171">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="79a93-172">Il valore predefinito è 50, ma può variare da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="79a93-172">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="79a93-173">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dalla **quando viene raggiunta l'impostazione del numero massimo di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="79a93-173">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="79a93-174">Puoi scegliere di disconnettere la chiamata o di reindirizzarla a qualsiasi destinazione di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79a93-174">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="79a93-175">Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-175">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="79a93-176">Per i trasferimenti esterni, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e i trasferimenti per i [numeri di telefono esterni-dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.</span><span class="sxs-lookup"><span data-stu-id="79a93-176">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="79a93-177">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="79a93-177">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="79a93-178">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79a93-178">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="79a93-180">**Timeout chiamata: periodo di attesa massimo** specifica il tempo massimo che una chiamata può contenere nella coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="79a93-180">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="79a93-181">È possibile specificare un valore da 0 secondi a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="79a93-181">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="79a93-182">Puoi scegliere di disconnettere la chiamata o di reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79a93-182">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="79a93-183">Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda.</span><span class="sxs-lookup"><span data-stu-id="79a93-183">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="79a93-184">Per i trasferimenti esterni, vedere i [prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e i trasferimenti per i [numeri di telefono esterni-dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.</span><span class="sxs-lookup"><span data-stu-id="79a93-184">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="79a93-185">Dopo aver selezionato le opzioni di timeout delle chiamate, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79a93-185">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="79a93-186">ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="79a93-186">Caller ID for outbound calls</span></span>

<span data-ttu-id="79a93-187">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="79a93-187">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="79a93-188">Per altre informazioni, vedere [gestire i criteri di ID chiamante in Microsoft teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="79a93-188">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="79a93-189">Client supportati</span><span class="sxs-lookup"><span data-stu-id="79a93-189">Supported clients</span></span>

<span data-ttu-id="79a93-190">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="79a93-190">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="79a93-191">Client desktop Skype for business 2016 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79a93-191">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79a93-192">Client desktop Lync 2013 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79a93-192">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79a93-193">Tutti i modelli di telefono IP supportati per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="79a93-193">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="79a93-194">Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="79a93-194">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="79a93-195">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79a93-195">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="79a93-196">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79a93-196">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="79a93-197">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79a93-197">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="79a93-198">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79a93-198">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="79a93-199">Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79a93-199">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79a93-200">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="79a93-200">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="79a93-201">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79a93-201">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="79a93-202">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="79a93-202">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="79a93-203">Le code di chiamata assegnate a un numero di routing diretto non supportano i client Skype for business, i client Lync o i telefoni IP Skype for business come agenti.</span><span class="sxs-lookup"><span data-stu-id="79a93-203">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="79a93-204">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="79a93-204">Call queue cmdlets</span></span>

<span data-ttu-id="79a93-205">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-205">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="79a93-206">Ecco i cmdlet usati per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79a93-206">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="79a93-207">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79a93-207">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="79a93-208">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79a93-208">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="79a93-209">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79a93-209">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="79a93-210">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79a93-210">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="79a93-211">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="79a93-211">Related topics</span></span>

[<span data-ttu-id="79a93-212">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="79a93-212">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="79a93-213">[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="79a93-213">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="79a93-214">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="79a93-214">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="79a93-215">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="79a93-215">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="79a93-216">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="79a93-216">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
