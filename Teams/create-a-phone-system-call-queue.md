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
ms.openlocfilehash: 9825c6ed1780efa78bfdbc86911e9b403be589f6
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2020
ms.locfileid: "48820019"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="8df73-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="8df73-103">Create a call queue</span></span>

<span data-ttu-id="8df73-104">Le code di chiamata offrono un metodo per indirizzare i chiamanti alle persone dell'organizzazione che possono aiutarti con un problema o una domanda particolare.</span><span class="sxs-lookup"><span data-stu-id="8df73-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="8df73-105">Le chiamate vengono distribuite una alla volta per gli utenti della coda (noti come *agenti* ).</span><span class="sxs-lookup"><span data-stu-id="8df73-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="8df73-106">Le code di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="8df73-106">Call queues provide:</span></span>

- <span data-ttu-id="8df73-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="8df73-107">A greeting message.</span></span>

- <span data-ttu-id="8df73-108">Musica mentre gli utenti attendono il blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="8df73-109">Chiamata routing-in *First in, First out* (FIFO) Order-to Agents.</span><span class="sxs-lookup"><span data-stu-id="8df73-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="8df73-110">Opzioni di gestione per l'overflow e il timeout delle code.</span><span class="sxs-lookup"><span data-stu-id="8df73-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="8df73-111">Assicurarsi di aver letto [piano per gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md) e aver seguito i [passaggi introduttivi](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8df73-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="8df73-112">Per configurare una coda di chiamata, nell'interfaccia di amministrazione di Team espandere **voce** , fare clic su **code di chiamata** e quindi fare clic su **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="8df73-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add** .</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="8df73-113">Account e lingua delle risorse</span><span class="sxs-lookup"><span data-stu-id="8df73-113">Resource account and language</span></span>

![Screenshot delle impostazioni dell'account delle risorse e della lingua](media/call-queue-name-language.png)

1. <span data-ttu-id="8df73-115">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-115">Type a name for the call queue.</span></span> <span data-ttu-id="8df73-116">Gli agenti vedranno questo nome quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="8df73-117">Fare clic su **Aggiungi account** , cercare l'account risorse che si vuole usare con la coda di chiamata, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="8df73-117">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add** .</span></span>

3. <span data-ttu-id="8df73-118">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="8df73-118">Choose a language.</span></span> <span data-ttu-id="8df73-119">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="8df73-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="8df73-120">Messaggi di saluto e musica in attesa</span><span class="sxs-lookup"><span data-stu-id="8df73-120">Greetings and hold music</span></span>

<span data-ttu-id="8df73-121">Specificare se si vuole riprodurre un saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="8df73-122">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto che si vuole riprodurre.</span><span class="sxs-lookup"><span data-stu-id="8df73-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="8df73-123">Teams offre musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="8df73-124">Se si vuole riprodurre un file audio specifico, scegliere **Riproduci un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="8df73-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="8df73-125">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="8df73-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="8df73-126">La musica predefinita fornita nelle code delle chiamate di teams è priva di qualsiasi royalties pagabile dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8df73-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="8df73-127">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="8df73-127">Call agents</span></span>

<span data-ttu-id="8df73-128">Gli agenti di chiamata selezionati devono essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8df73-128">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="8df73-129">Utenti online con licenza di sistema telefonico e VoIP aziendale abilitato</span><span class="sxs-lookup"><span data-stu-id="8df73-129">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="8df73-130">Utenti online con un piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="8df73-130">Online users with a Calling Plan</span></span>
- <span data-ttu-id="8df73-131">Utenti di Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="8df73-131">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="8df73-132">Se gli agenti usano l'app Microsoft teams per le chiamate alla coda di chiamata, devono essere in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8df73-132">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

<span data-ttu-id="8df73-134">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="8df73-134">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="8df73-135">Per aggiungere un utente alla coda, fare clic su **Aggiungi utenti** , cercare l'utente, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="8df73-135">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add** .</span></span>

<span data-ttu-id="8df73-136">Per aggiungere un gruppo alla coda, fare clic su **Aggiungi gruppi** , cercare il gruppo, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="8df73-136">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add** .</span></span> <span data-ttu-id="8df73-137">È possibile usare le liste di distribuzione, i gruppi di sicurezza e i gruppi Microsoft 365 o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8df73-137">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="8df73-138">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore per la prima chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="8df73-138">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="8df73-139">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8df73-139">Call routing</span></span>

![Screenshot della modalità conferenza e delle impostazioni del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="8df73-141">La **modalità conferenza** riduce significativamente la quantità di tempo necessaria affinché un chiamante venga connesso a un agente, dopo che l'agente accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-141">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="8df73-142">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="8df73-142">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="8df73-143">La versione più recente di Microsoft teams desktop client, Android app o iOS app</span><span class="sxs-lookup"><span data-stu-id="8df73-143">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="8df73-144">Telefono Microsoft teams versione 1449/1.0.94.2020051601 o successiva</span><span class="sxs-lookup"><span data-stu-id="8df73-144">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="8df73-145">Gli account teams degli agenti devono essere impostati sulla modalità solo teams.</span><span class="sxs-lookup"><span data-stu-id="8df73-145">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="8df73-146">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="8df73-146">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="8df73-147">È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti i client compatibili.</span><span class="sxs-lookup"><span data-stu-id="8df73-147">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="8df73-148">Occupato in occupato non è supportato dalla modalità conferenza.</span><span class="sxs-lookup"><span data-stu-id="8df73-148">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="8df73-149">Gli agenti sulle chiamate di coda non di chiamata potrebbero essere ancora presentati con una chiamata alla coda di chiamata se il routing basato sulla presenza non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="8df73-149">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="8df73-150">Il **metodo di routing** determina l'ordine in cui gli agenti ricevono chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-150">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="8df73-151">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8df73-151">Choose from these options:</span></span>

- <span data-ttu-id="8df73-152">Il **routing di Attendant** squilla tutti gli agenti della coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8df73-152">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="8df73-153">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-153">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="8df73-154">Il **routing seriale** squilla tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **agenti di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="8df73-154">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="8df73-155">Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.</span><span class="sxs-lookup"><span data-stu-id="8df73-155">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="8df73-156">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-156">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="8df73-157">Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-157">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="8df73-158">Le rotte **inattive più lunghe** ogni chiamata all'agente che è stato inattivo il tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="8df73-158">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="8df73-159">Un agente viene considerato inattivo se lo stato presenza è disponibile o se lo stato presenza è stato assente per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="8df73-159">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="8df73-160">Gli agenti il cui stato di presenza è stato assente per più di 10 minuti non sono considerati inattivi e non sono idonei a ricevere chiamate finché non modificano la loro presenza in available.</span><span class="sxs-lookup"><span data-stu-id="8df73-160">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni di routing, disattivazione e ora di avviso](media/call-queue-presence-agents-time.png)


<span data-ttu-id="8df73-162">Il **routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="8df73-162">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="8df73-163">Gli agenti di chiamata il cui stato di disponibilità è impostato su **disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="8df73-163">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="8df73-164">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato sono esclusi dall'elenco di routing delle chiamate e non ricevono le chiamate finché il loro stato di disponibilità non torna a **disponibile** .</span><span class="sxs-lookup"><span data-stu-id="8df73-164">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available** .</span></span> 

<span data-ttu-id="8df73-165">Puoi abilitare il routing delle chiamate basate sulla presenza con uno dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="8df73-165">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="8df73-166">Se un agente sceglie di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate, indipendentemente dal tipo di stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="8df73-166">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="8df73-167">Gli agenti che usano il client Skype for business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="8df73-167">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="8df73-168">Se si hanno agenti che usano Skype for business, non abilitare il routing delle chiamate basate sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="8df73-168">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="8df73-169">L' **ora di avviso dell'agente** specifica il tempo di squillo del telefono di un agente prima che la chiamata venga reindirizzata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="8df73-169">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="8df73-170">Per le code a volume elevato, è consigliabile seguire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8df73-170">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="8df73-171">**Modalità conferenza** per l' **auto**</span><span class="sxs-lookup"><span data-stu-id="8df73-171">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="8df73-172">**Metodo di routing** per il **routing di Attendant**</span><span class="sxs-lookup"><span data-stu-id="8df73-172">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="8df73-173">**Routing basato sulla presenza** **su** attivato</span><span class="sxs-lookup"><span data-stu-id="8df73-173">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="8df73-174">**Tempo di avviso agente:** a **20 secondi**</span><span class="sxs-lookup"><span data-stu-id="8df73-174">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="8df73-175">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8df73-175">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="8df73-177">**Massimo chiamate nella coda** specifica il numero massimo di chiamate che possono essere attese nella coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8df73-177">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="8df73-178">Il valore predefinito è 50, ma può variare da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="8df73-178">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="8df73-179">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dalla **quando viene raggiunta l'impostazione del numero massimo di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="8df73-179">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="8df73-180">Puoi scegliere di disconnettere la chiamata o reindirizzarla a qualsiasi [destinazione di routing delle chiamate](create-a-phone-system-auto-attendant.md#call-routing-options) eccetto l'operatore.</span><span class="sxs-lookup"><span data-stu-id="8df73-180">You can choose to disconnect the call or redirect it to any of the [call routing destinations](create-a-phone-system-auto-attendant.md#call-routing-options) except the operator.</span></span> <span data-ttu-id="8df73-181">Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-181">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="8df73-182">(Nota [questi dettagli](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) se si sta trasferendo un numero esterno).</span><span class="sxs-lookup"><span data-stu-id="8df73-182">(Note [these details](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) if you're transferring to an external number.)</span></span>

> [!NOTE]
> <span data-ttu-id="8df73-183">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="8df73-183">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="8df73-184">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8df73-184">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="8df73-186">**Timeout chiamata: periodo di attesa massimo** specifica il tempo massimo che una chiamata può contenere nella coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="8df73-186">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="8df73-187">È possibile specificare un valore da 15 secondi a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="8df73-187">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="8df73-188">Puoi scegliere di disconnettere la chiamata o di reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="8df73-188">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="8df73-189">Ad esempio, è possibile che il chiamante lasci un messaggio vocale per gli agenti nella coda.</span><span class="sxs-lookup"><span data-stu-id="8df73-189">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="8df73-190">Dopo aver selezionato le opzioni di timeout delle chiamate, fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="8df73-190">When you have selected your call timeout options, click **Save** .</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="8df73-191">ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="8df73-191">Caller ID for outbound calls</span></span>

<span data-ttu-id="8df73-192">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="8df73-192">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="8df73-193">Per altre informazioni, vedere [gestire i criteri di ID chiamante in Microsoft teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="8df73-193">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="8df73-194">Client supportati</span><span class="sxs-lookup"><span data-stu-id="8df73-194">Supported clients</span></span>

- <span data-ttu-id="8df73-195">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="8df73-195">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="8df73-196">Client desktop Skype for business 2016 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="8df73-196">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8df73-197">Client desktop Lync 2013 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="8df73-197">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8df73-198">Tutti i modelli di telefono IP supportati per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8df73-198">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="8df73-199">Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="8df73-199">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="8df73-200">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="8df73-200">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="8df73-201">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="8df73-201">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="8df73-202">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="8df73-202">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8df73-203">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="8df73-203">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="8df73-204">Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="8df73-204">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="8df73-205">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="8df73-205">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="8df73-206">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8df73-206">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="8df73-207">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="8df73-207">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="8df73-208">Le code di chiamata assegnate a un numero di routing diretto non supportano i client Skype for business, i client Lync o i telefoni IP Skype for business come agenti.</span><span class="sxs-lookup"><span data-stu-id="8df73-208">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="8df73-209">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="8df73-209">Call queue cmdlets</span></span>

<span data-ttu-id="8df73-210">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-210">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="8df73-211">Ecco i cmdlet usati per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8df73-211">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="8df73-212">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8df73-212">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="8df73-213">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8df73-213">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="8df73-214">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8df73-214">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="8df73-215">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="8df73-215">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="8df73-216">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8df73-216">Related topics</span></span>

[<span data-ttu-id="8df73-217">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="8df73-217">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="8df73-218">[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="8df73-218">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="8df73-219">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="8df73-219">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="8df73-220">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8df73-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="8df73-221">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8df73-221">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
