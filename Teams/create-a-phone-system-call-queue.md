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
description: Informazioni su come configurare Sistema telefonico per le code di chiamata con Microsoft Teams, che forniscono un messaggio di saluto, la musica in attesa, il reindirizzamento delle chiamate e altre funzionalità.
ms.openlocfilehash: 9bb33e5590df1af6b70dffecba64eb313838b228
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092714"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="79ab0-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="79ab0-103">Create a call queue</span></span>

<span data-ttu-id="79ab0-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="79ab0-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="79ab0-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="79ab0-106">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="79ab0-106">Call queues provide:</span></span>

- <span data-ttu-id="79ab0-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="79ab0-107">A greeting message.</span></span>

- <span data-ttu-id="79ab0-108">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="79ab0-109">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="79ab0-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="79ab0-110">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="79ab0-111">Assicurarsi di aver letto Pianificare gli operatori automatici e [](plan-auto-attendant-call-queue.md#getting-started) le code di chiamata di [Teams](plan-auto-attendant-call-queue.md) e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="79ab0-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="79ab0-112">Per configurare una coda di chiamata, nell'interfaccia di amministrazione di Teams espandere **Voce,** fare clic su **Code di chiamata** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="79ab0-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="79ab0-113">Account e lingua delle risorse</span><span class="sxs-lookup"><span data-stu-id="79ab0-113">Resource account and language</span></span>

![Screenshot delle impostazioni dell'account della risorsa e della lingua](media/call-queue-name-language.png)

1. <span data-ttu-id="79ab0-115">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="79ab0-116">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="79ab0-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="79ab0-117">Gli agenti visualizzano il nome dell'account della risorsa quando ricevono una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="79ab0-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="79ab0-118">Scegliere una [lingua supportata.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="79ab0-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="79ab0-119">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="79ab0-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="79ab0-120">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="79ab0-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="79ab0-121">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="79ab0-122">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="79ab0-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="79ab0-123">Teams fornisce musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="79ab0-124">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="79ab0-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="79ab0-125">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="79ab0-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="79ab0-126">La musica predefinita fornita nelle code di chiamata di Teams è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79ab0-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="79ab0-127">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="79ab0-127">Call agents</span></span>

<span data-ttu-id="79ab0-128">Fare riferimento ai [Prerequisiti per](plan-auto-attendant-call-queue.md#prerequisites) poter aggiungere agenti a una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

<span data-ttu-id="79ab0-130">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="79ab0-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="79ab0-131">Per aggiungere un utente alla coda, fare clic **su Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79ab0-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="79ab0-132">Per aggiungere un gruppo alla coda, fare clic **su Aggiungi gruppi,** cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="79ab0-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="79ab0-133">È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79ab0-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="79ab0-134">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore prima dell'arrivo della prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="79ab0-135">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79ab0-135">Call routing</span></span>

![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="79ab0-137">**La modalità conferenza** riduce significativamente il tempo necessario per la connessione di un chiamante a un agente, dopo che l'agente ha accettato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="79ab0-138">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="79ab0-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="79ab0-139">La versione più recente del client desktop di Microsoft Teams, dell'app Android o dell'app iOS</span><span class="sxs-lookup"><span data-stu-id="79ab0-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="79ab0-140">Microsoft Teams phone version 1449/1.0.94.2020051601 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="79ab0-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="79ab0-141">Gli account di Teams degli agenti devono essere impostati sulla modalità Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="79ab0-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="79ab0-142">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79ab0-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="79ab0-143">È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.</span><span class="sxs-lookup"><span data-stu-id="79ab0-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="79ab0-144">**Il metodo di** routing determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="79ab0-145">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79ab0-145">Choose from these options:</span></span>

- <span data-ttu-id="79ab0-146">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="79ab0-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="79ab0-147">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="79ab0-148">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **Agenti di** chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="79ab0-149">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="79ab0-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="79ab0-150">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="79ab0-151">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="79ab0-152">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="79ab0-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="79ab0-153">Un agente è considerato inattivo se lo stato di presenza è Disponibile o se lo stato presenza è Stato Non al computer per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="79ab0-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="79ab0-154">Gli agenti il cui stato presenza è Stato Non al computer per più di 10 minuti non vengono considerati inattivi e non saranno idonei a ricevere chiamate finché non cambiano la propria presenza in Disponibile.</span><span class="sxs-lookup"><span data-stu-id="79ab0-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](media/call-queue-presence-agents-time.png)


<span data-ttu-id="79ab0-156">**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="79ab0-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="79ab0-157">Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="79ab0-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="79ab0-158">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="79ab0-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="79ab0-159">È possibile abilitare il routing delle chiamate basate sulla presenza con uno qualsiasi dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="79ab0-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="79ab0-160">Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate indipendentemente dal relativo stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="79ab0-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="79ab0-161">Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="79ab0-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="79ab0-162">Se hai agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="79ab0-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="79ab0-163">**Tempo di avviso agente** specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="79ab0-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="79ab0-164">Sono consigliate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79ab0-164">The following settings are recommended:</span></span>

- <span data-ttu-id="79ab0-165">**Modalità conferenza su** **Automatico**</span><span class="sxs-lookup"><span data-stu-id="79ab0-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="79ab0-166">**Metodo di instradamento** **a Round robin** o Più lungo **inattivo**</span><span class="sxs-lookup"><span data-stu-id="79ab0-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="79ab0-167">**Routing basato sulla presenza su** **On**</span><span class="sxs-lookup"><span data-stu-id="79ab0-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="79ab0-168">**Tempo di avviso dell'agente:** **a 20 secondi**</span><span class="sxs-lookup"><span data-stu-id="79ab0-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="79ab0-169">Se il routing basato sulla presenza non è abilitato e la coda contiene più chiamate, il sistema presenterà queste chiamate contemporaneamente agli agenti indipendentemente dal loro stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="79ab0-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="79ab0-170">In questo modo si riceveranno più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="79ab0-171">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79ab0-171">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="79ab0-173">**Numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono essere in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="79ab0-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="79ab0-174">Il valore predefinito è 50, ma può essere compreso tra 0 e 200.</span><span class="sxs-lookup"><span data-stu-id="79ab0-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="79ab0-175">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione Quando viene raggiunto il numero massimo **di** chiamate.</span><span class="sxs-lookup"><span data-stu-id="79ab0-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="79ab0-176">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79ab0-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="79ab0-177">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="79ab0-178">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="79ab0-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="79ab0-179">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="79ab0-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="79ab0-180">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="79ab0-180">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="79ab0-182">**Timeout chiamata: il tempo di attesa** massimo specifica il tempo massimo di attesa di una chiamata in coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="79ab0-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="79ab0-183">È possibile specificare un valore compreso tra 0 secondi e 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="79ab0-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="79ab0-184">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="79ab0-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="79ab0-185">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="79ab0-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="79ab0-186">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="79ab0-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="79ab0-187">Dopo aver selezionato le opzioni di timeout della chiamata, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="79ab0-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="79ab0-188">ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="79ab0-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="79ab0-189">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="79ab0-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="79ab0-190">Per altre informazioni, vedere Gestire [i criteri id chiamante in Microsoft Teams.](caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="79ab0-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="79ab0-191">Client supportati</span><span class="sxs-lookup"><span data-stu-id="79ab0-191">Supported clients</span></span>

<span data-ttu-id="79ab0-192">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="79ab0-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="79ab0-193">Client desktop Skype for Business 2016 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79ab0-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79ab0-194">Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79ab0-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79ab0-195">Tutti i modelli di telefono IP supportati per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79ab0-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="79ab0-196">Vedere [Ottenere telefoni per Skype for Business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="79ab0-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="79ab0-197">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79ab0-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="79ab0-198">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79ab0-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="79ab0-199">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79ab0-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="79ab0-200">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="79ab0-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="79ab0-201">Client Windows di Microsoft Teams (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="79ab0-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="79ab0-202">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="79ab0-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="79ab0-203">App Per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79ab0-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="79ab0-204">App Microsoft Teams per Android</span><span class="sxs-lookup"><span data-stu-id="79ab0-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ab0-205">Le code di chiamata a cui è assegnato un numero di instradamento diretto non supportano i client Skype for Business, i client Lync o i telefoni IP Skype for Business come agenti.</span><span class="sxs-lookup"><span data-stu-id="79ab0-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="79ab0-206">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="79ab0-206">Call queue cmdlets</span></span>

<span data-ttu-id="79ab0-207">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="79ab0-208">Ecco i cmdlet che si usano per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ab0-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="79ab0-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79ab0-209">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="79ab0-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79ab0-210">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="79ab0-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79ab0-211">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="79ab0-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="79ab0-212">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="79ab0-213">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="79ab0-213">Related topics</span></span>

[<span data-ttu-id="79ab0-214">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="79ab0-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="79ab0-215">[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="79ab0-215">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="79ab0-216">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="79ab0-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="79ab0-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="79ab0-217">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="79ab0-218">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="79ab0-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)