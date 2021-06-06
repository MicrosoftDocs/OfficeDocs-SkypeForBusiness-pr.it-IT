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
description: Informazioni su come configurare le code di chiamata per le organizzazioni di grandi dimensioni in Microsoft Teams, che fornisce un messaggio di saluto, la musica in attesa, il reindirizzamento delle chiamate e altre funzionalità.
ms.openlocfilehash: fe0c2863c627f728f5418cfeb9b7b17c91d246fa
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777927"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="78022-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="78022-103">Create a call queue</span></span>

<span data-ttu-id="78022-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="78022-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="78022-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="78022-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="78022-106">Questo articolo è per le organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="78022-106">This article is for large organizations.</span></span> <span data-ttu-id="78022-107">Se l'organizzazione è una piccola azienda, vedere Creare una coda [di chiamata - esercitazione sulle piccole](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) imprese.</span><span class="sxs-lookup"><span data-stu-id="78022-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="78022-108">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="78022-108">Call queues provide:</span></span>

- <span data-ttu-id="78022-109">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="78022-109">A greeting message.</span></span>

- <span data-ttu-id="78022-110">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="78022-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="78022-111">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="78022-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="78022-112">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="78022-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="78022-113">Assicurarsi di aver letto Pianificare [gli](plan-auto-attendant-call-queue.md) operatori Teams e le [](plan-auto-attendant-call-queue.md#getting-started) code di chiamata e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="78022-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="78022-114">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="78022-114">Video demonstration</span></span>

<span data-ttu-id="78022-115">Questo video mostra un esempio di base di come creare una coda di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="78022-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="78022-116">Creare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="78022-116">Create the call queue</span></span>

<span data-ttu-id="78022-117">Per configurare una coda di chiamata, nell'interfaccia Teams di amministrazione espandere **Voce,** fare clic su Code di chiamata **e** quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="78022-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="78022-118">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="78022-119">Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="78022-119">Resource accounts</span></span>

![Screenshot delle impostazioni dell'account delle risorse](media/call-queue-name-language.png)

<span data-ttu-id="78022-121">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="78022-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="78022-122">Gli agenti visualizzano il nome dell'account della risorsa quando ricevono una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="78022-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="78022-123">Assegnare l'ID chiamata</span><span class="sxs-lookup"><span data-stu-id="78022-123">Assign calling ID</span></span>

![Screenshot delle impostazioni dell'ID chiamata](media/call-queue-assign-calling-id.png)

<span data-ttu-id="78022-125">Se si prevede di usare un canale Teams per gli agenti di chiamata, è possibile assegnare un numero di ID chiamante in uscita per gli agenti specificando uno o più account delle risorse con un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="78022-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="78022-126">Fare **clic su** Aggiungi , cercare gli account delle risorse a cui consentire agli agenti di effettuare chiamate con ID durante le chiamate in uscita, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="78022-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="78022-127">Se non si usa un canale di Teams per controllare l'appartenenza all'agente, è consigliabile impostare direttamente l'ID chiamante per i membri della coda di chiamata sul numero di servizio della coda di chiamata o sull'operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="78022-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="78022-128">Per altre informazioni, vedere Gestire i [criteri id chiamante in Microsoft Teams](caller-id-policies.md) chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="78022-129">Lingua</span><span class="sxs-lookup"><span data-stu-id="78022-129">Language</span></span>

![Screenshot delle impostazioni della lingua](media/call-queue-language.png)

<span data-ttu-id="78022-131">Scegliere una [lingua supportata.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="78022-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="78022-132">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="78022-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="78022-133">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="78022-133">Greetings and music on hold in queue</span></span>

![Screenshot di messaggi di saluto e musica in attesa nelle impostazioni della coda](media/call-queue-greetings-music.png)

<span data-ttu-id="78022-135">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="78022-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="78022-136">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="78022-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="78022-137">Teams musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="78022-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="78022-138">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="78022-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="78022-139">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="78022-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="78022-140">La musica predefinita fornita nelle code Teams chiamate è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78022-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="78022-141">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="78022-141">Call agents</span></span>

<span data-ttu-id="78022-142">Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="78022-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="78022-144">Teams canale</span><span class="sxs-lookup"><span data-stu-id="78022-144">Teams channel</span></span>

<span data-ttu-id="78022-145">È possibile aggiungere fino a 200 agenti tramite un Teams canale.</span><span class="sxs-lookup"><span data-stu-id="78022-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="78022-146">Se si vuole usare un canale Teams per gestire la [coda,](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)selezionare l'opzione **Scegli un team** e fare clic su Aggiungi **canale.**</span><span class="sxs-lookup"><span data-stu-id="78022-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="78022-147">Cercare il team da usare, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="78022-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="78022-148">Selezionare il canale da usare e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="78022-148">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="78022-149">I client seguenti sono supportati quando si usa un canale Teams per le code di chiamata:</span><span class="sxs-lookup"><span data-stu-id="78022-149">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="78022-150">Microsoft Teams Windows client</span><span class="sxs-lookup"><span data-stu-id="78022-150">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="78022-151">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="78022-151">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="78022-152">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="78022-152">Users and groups</span></span>

<span data-ttu-id="78022-153">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="78022-153">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="78022-154">Per aggiungere singoli utenti o gruppi alla coda, selezionare **l'opzione Scegli utenti e** gruppi.</span><span class="sxs-lookup"><span data-stu-id="78022-154">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="78022-155">Per aggiungere un utente alla coda, fare clic **su Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="78022-155">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="78022-156">Per aggiungere un gruppo alla coda, fare clic **su Aggiungi gruppi,** cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="78022-156">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="78022-157">È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o Microsoft Teams team.</span><span class="sxs-lookup"><span data-stu-id="78022-157">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="78022-158">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore prima dell'arrivo della prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-158">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="78022-159">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="78022-159">Call routing</span></span>

![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="78022-161">**La modalità conferenza** riduce significativamente il tempo necessario per la connessione di un chiamante a un agente, dopo che l'agente ha accettato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-161">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="78022-162">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="78022-162">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="78022-163">La versione più recente del client desktop Microsoft Teams, dell'app Android o dell'app iOS</span><span class="sxs-lookup"><span data-stu-id="78022-163">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="78022-164">Microsoft Teams telefono 1449/1.0.94.2020051601 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="78022-164">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="78022-165">Gli account Teams agenti devono essere impostati sulla modalità Teams solo utenti.</span><span class="sxs-lookup"><span data-stu-id="78022-165">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="78022-166">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-166">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="78022-167">È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.</span><span class="sxs-lookup"><span data-stu-id="78022-167">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="78022-168">La modalità conferenza non è supportata se le chiamate telefoniche vengono instradati alla coda da un gateway di routing diretto abilitato per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="78022-168">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="78022-169">**Il metodo di** routing determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="78022-169">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="78022-170">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="78022-170">Choose from these options:</span></span>

- <span data-ttu-id="78022-171">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="78022-171">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="78022-172">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-172">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="78022-173">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **Agenti di** chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-173">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="78022-174">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="78022-174">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="78022-175">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="78022-175">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="78022-176">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-176">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="78022-177">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="78022-177">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="78022-178">Un agente è considerato inattivo se lo stato di presenza è Disponibile o se lo stato presenza è Stato Non al computer per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="78022-178">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="78022-179">Gli agenti il cui stato presenza è Stato Non al computer per più di 10 minuti non vengono considerati inattivi e non saranno idonei a ricevere chiamate finché non cambiano la propria presenza in Disponibile.</span><span class="sxs-lookup"><span data-stu-id="78022-179">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](media/call-queue-presence-agents-time.png)

<span data-ttu-id="78022-181">**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="78022-181">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="78022-182">Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-182">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="78022-183">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="78022-183">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="78022-184">È possibile abilitare il routing delle chiamate basate sulla presenza con uno qualsiasi dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="78022-184">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="78022-185">Quando **l'opzione** Inattività più lunga è selezionata come metodo di routing, il routing  basato sulla presenza è obbligatorio e abilitato automaticamente anche se l'interruttore routing basato sulla presenza sarà disattivato e disattivato.</span><span class="sxs-lookup"><span data-stu-id="78022-185">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="78022-186">Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate indipendentemente dal relativo stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="78022-186">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="78022-187">Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="78022-187">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="78022-188">Se si hanno agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="78022-188">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="78022-189">**Tempo di avviso agente** specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="78022-189">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="78022-190">Sono consigliate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="78022-190">The following settings are recommended:</span></span>

- <span data-ttu-id="78022-191">**Modalità conferenza su** **Automatico**</span><span class="sxs-lookup"><span data-stu-id="78022-191">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="78022-192">**Metodo di instradamento** **a Round robin** o Più lungo **inattivo**</span><span class="sxs-lookup"><span data-stu-id="78022-192">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="78022-193">**Routing basato sulla presenza su** **On**</span><span class="sxs-lookup"><span data-stu-id="78022-193">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="78022-194">**Tempo di avviso dell'agente:** **a 20 secondi**</span><span class="sxs-lookup"><span data-stu-id="78022-194">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="78022-195">Se il routing basato sulla presenza non è abilitato e la coda contiene più chiamate, il sistema presenterà queste chiamate contemporaneamente agli agenti indipendentemente dal loro stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="78022-195">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="78022-196">In questo modo si riceveranno più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.</span><span class="sxs-lookup"><span data-stu-id="78022-196">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="78022-197">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="78022-197">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="78022-199">**Numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono essere in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="78022-199">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="78022-200">Il valore predefinito è 50, ma può essere compreso tra 0 e 200.</span><span class="sxs-lookup"><span data-stu-id="78022-200">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="78022-201">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione Quando viene raggiunto il numero massimo **di** chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-201">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="78022-202">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-202">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="78022-203">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="78022-203">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="78022-204">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="78022-204">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="78022-205">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="78022-205">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="78022-206">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="78022-206">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="78022-208">**Timeout chiamata: il tempo di attesa** massimo specifica il tempo massimo di attesa di una chiamata in coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="78022-208">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="78022-209">È possibile specificare un valore compreso tra 0 secondi e 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="78022-209">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="78022-210">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78022-210">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="78022-211">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="78022-211">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="78022-212">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="78022-212">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="78022-213">Dopo aver selezionato le opzioni di timeout della chiamata, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="78022-213">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="78022-214">Client supportati</span><span class="sxs-lookup"><span data-stu-id="78022-214">Supported clients</span></span>

<span data-ttu-id="78022-215">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="78022-215">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="78022-216">Skype for Business client desktop 2016 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="78022-216">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="78022-217">Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="78022-217">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="78022-218">Tutti i modelli di telefono IP supportati per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78022-218">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="78022-219">Vedere [Ottenere telefoni per Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="78022-219">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="78022-220">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="78022-220">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="78022-221">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="78022-221">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="78022-222">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="78022-222">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="78022-223">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="78022-223">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="78022-224">Microsoft Teams Windows client (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="78022-224">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="78022-225">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="78022-225">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="78022-226">Microsoft Teams in [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="78022-226">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="78022-227">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="78022-227">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="78022-228">Microsoft Teams App Android</span><span class="sxs-lookup"><span data-stu-id="78022-228">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="78022-229">Le code di chiamata a cui è assegnato un numero di instradamento diretto non supportano Skype for Business client, client Lync o telefoni IP Skype for Business telefoni IP come agenti.</span><span class="sxs-lookup"><span data-stu-id="78022-229">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="78022-230">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="78022-230">Call queue cmdlets</span></span>

<span data-ttu-id="78022-231">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-231">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="78022-232">Ecco i cmdlet che si usano per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="78022-232">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="78022-233">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="78022-233">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="78022-234">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="78022-234">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="78022-235">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="78022-235">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="78022-236">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="78022-236">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="78022-237">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="78022-237">Related topics</span></span>

[<span data-ttu-id="78022-238">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="78022-238">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="78022-239">[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="78022-239">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="78022-240">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="78022-240">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="78022-241">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="78022-241">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="78022-242">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="78022-242">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
