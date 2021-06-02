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
ms.openlocfilehash: 73b0e0c6c73b86e544ade5a43756e2e80c60c25a
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717877"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="2cc3a-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="2cc3a-103">Create a call queue</span></span>

<span data-ttu-id="2cc3a-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="2cc3a-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="2cc3a-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="2cc3a-106">Questo articolo è per le organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-106">This article is for large organizations.</span></span> <span data-ttu-id="2cc3a-107">Se l'organizzazione è una piccola azienda, vedere Creare una coda [di chiamata - esercitazione sulle piccole](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) imprese.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="2cc3a-108">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-108">Call queues provide:</span></span>

- <span data-ttu-id="2cc3a-109">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-109">A greeting message.</span></span>

- <span data-ttu-id="2cc3a-110">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="2cc3a-111">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="2cc3a-112">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="2cc3a-113">Assicurarsi di aver letto Pianificare [gli](plan-auto-attendant-call-queue.md) operatori Teams e le [](plan-auto-attendant-call-queue.md#getting-started) code di chiamata e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="2cc3a-114">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="2cc3a-114">Video demonstration</span></span>

<span data-ttu-id="2cc3a-115">Questo video mostra un esempio di base di come creare una coda di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="2cc3a-116">Creare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="2cc3a-116">Create the call queue</span></span>

<span data-ttu-id="2cc3a-117">Per configurare una coda di chiamata, nell'interfaccia Teams di amministrazione espandere **Voce,** fare clic su Code di chiamata **e** quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

### <a name="resource-account-and-language"></a><span data-ttu-id="2cc3a-118">Account e lingua delle risorse</span><span class="sxs-lookup"><span data-stu-id="2cc3a-118">Resource account and language</span></span>

![Screenshot delle impostazioni dell'account della risorsa e della lingua](media/call-queue-name-language.png)

1. <span data-ttu-id="2cc3a-120">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-120">Type a name for the call queue.</span></span>

2. <span data-ttu-id="2cc3a-121">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="2cc3a-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="2cc3a-122">Gli agenti visualizzano il nome dell'account della risorsa quando ricevono una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="2cc3a-123">Scegliere una [lingua supportata.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-123">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="2cc3a-124">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="2cc3a-124">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="2cc3a-125">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="2cc3a-125">Greetings and music on hold in queue</span></span>

<span data-ttu-id="2cc3a-126">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-126">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="2cc3a-127">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-127">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="2cc3a-128">Teams musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-128">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="2cc3a-129">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-129">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc3a-130">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-130">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="2cc3a-131">La musica predefinita fornita nelle code Teams chiamate è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-131">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="2cc3a-132">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="2cc3a-132">Call agents</span></span>

<span data-ttu-id="2cc3a-133">Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-133">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="2cc3a-135">Teams canale</span><span class="sxs-lookup"><span data-stu-id="2cc3a-135">Teams channel</span></span>

<span data-ttu-id="2cc3a-136">È possibile aggiungere fino a 200 agenti tramite un Teams canale.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-136">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="2cc3a-137">Se si vuole usare un canale Teams per gestire la [coda,](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)selezionare l'opzione **Scegli un team** e fare clic su Aggiungi **canale.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-137">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="2cc3a-138">Cercare il team da usare, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-138">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="2cc3a-139">Selezionare il canale da usare e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-139">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="2cc3a-140">I client seguenti sono supportati quando si usa un canale Teams per le code di chiamata:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-140">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="2cc3a-141">Microsoft Teams Windows client</span><span class="sxs-lookup"><span data-stu-id="2cc3a-141">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="2cc3a-142">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="2cc3a-142">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="2cc3a-143">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="2cc3a-143">Users and groups</span></span>

<span data-ttu-id="2cc3a-144">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-144">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="2cc3a-145">Per aggiungere singoli utenti o gruppi alla coda, selezionare **l'opzione Scegli utenti e** gruppi.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-145">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="2cc3a-146">Per aggiungere un utente alla coda, fare clic **su Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-146">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="2cc3a-147">Per aggiungere un gruppo alla coda, fare clic **su Aggiungi gruppi,** cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-147">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="2cc3a-148">È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o Microsoft Teams team.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-148">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc3a-149">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore prima dell'arrivo della prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-149">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="2cc3a-150">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="2cc3a-150">Call routing</span></span>

![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="2cc3a-152">**La modalità conferenza** riduce significativamente il tempo necessario per la connessione di un chiamante a un agente, dopo che l'agente ha accettato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-152">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="2cc3a-153">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-153">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="2cc3a-154">La versione più recente del client desktop Microsoft Teams, dell'app Android o dell'app iOS</span><span class="sxs-lookup"><span data-stu-id="2cc3a-154">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="2cc3a-155">Microsoft Teams telefono 1449/1.0.94.2020051601 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="2cc3a-155">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="2cc3a-156">Gli account Teams agenti devono essere impostati sulla modalità Teams solo utenti.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-156">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="2cc3a-157">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-157">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="2cc3a-158">È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-158">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc3a-159">La modalità conferenza non è supportata se le chiamate telefoniche vengono instradati alla coda da un gateway di routing diretto abilitato per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-159">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="2cc3a-160">**Il metodo di** routing determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-160">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="2cc3a-161">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-161">Choose from these options:</span></span>

- <span data-ttu-id="2cc3a-162">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-162">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="2cc3a-163">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-163">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="2cc3a-164">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **Agenti di** chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-164">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="2cc3a-165">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-165">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="2cc3a-166">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-166">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="2cc3a-167">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-167">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="2cc3a-168">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-168">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="2cc3a-169">Un agente è considerato inattivo se lo stato di presenza è Disponibile o se lo stato presenza è Stato Non al computer per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-169">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="2cc3a-170">Gli agenti il cui stato presenza è Stato Non al computer per più di 10 minuti non vengono considerati inattivi e non saranno idonei a ricevere chiamate finché non cambiano la propria presenza in Disponibile.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-170">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](media/call-queue-presence-agents-time.png)


<span data-ttu-id="2cc3a-172">**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-172">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="2cc3a-173">Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-173">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="2cc3a-174">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-174">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="2cc3a-175">È possibile abilitare il routing delle chiamate basate sulla presenza con uno qualsiasi dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-175">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="2cc3a-176">Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate indipendentemente dal relativo stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-176">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="2cc3a-177">Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-177">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="2cc3a-178">Se si hanno agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-178">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="2cc3a-179">**Tempo di avviso agente** specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-179">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="2cc3a-180">Sono consigliate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-180">The following settings are recommended:</span></span>

- <span data-ttu-id="2cc3a-181">**Modalità conferenza su** **Automatico**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-181">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="2cc3a-182">**Metodo di instradamento** **a Round robin** o Più lungo **inattivo**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-182">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="2cc3a-183">**Routing basato sulla presenza su** **On**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-183">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="2cc3a-184">**Tempo di avviso dell'agente:** **a 20 secondi**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-184">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="2cc3a-185">Se il routing basato sulla presenza non è abilitato e la coda contiene più chiamate, il sistema presenterà queste chiamate contemporaneamente agli agenti indipendentemente dal loro stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-185">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="2cc3a-186">In questo modo si riceveranno più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-186">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="2cc3a-187">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="2cc3a-187">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="2cc3a-189">**Numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono essere in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-189">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="2cc3a-190">Il valore predefinito è 50, ma può essere compreso tra 0 e 200.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-190">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="2cc3a-191">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione Quando viene raggiunto il numero massimo **di** chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-191">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="2cc3a-192">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-192">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="2cc3a-193">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-193">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="2cc3a-194">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-194">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc3a-195">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-195">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="2cc3a-196">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="2cc3a-196">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="2cc3a-198">**Timeout chiamata: il tempo di attesa** massimo specifica il tempo massimo di attesa di una chiamata in coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-198">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="2cc3a-199">È possibile specificare un valore compreso tra 0 secondi e 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-199">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="2cc3a-200">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-200">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="2cc3a-201">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-201">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="2cc3a-202">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-202">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="2cc3a-203">Dopo aver selezionato le opzioni di timeout della chiamata, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="2cc3a-203">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="2cc3a-204">ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="2cc3a-204">Caller ID for outbound calls</span></span>

<span data-ttu-id="2cc3a-205">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per i membri di una coda di chiamata sul numero di servizio di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-205">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="2cc3a-206">Per altre informazioni, vedere Gestire i [criteri id chiamante in Microsoft Teams](caller-id-policies.md) chiamate.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-206">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="2cc3a-207">Client supportati</span><span class="sxs-lookup"><span data-stu-id="2cc3a-207">Supported clients</span></span>

<span data-ttu-id="2cc3a-208">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="2cc3a-208">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="2cc3a-209">Skype for Business client desktop 2016 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-209">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2cc3a-210">Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-210">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2cc3a-211">Tutti i modelli di telefono IP supportati per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-211">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="2cc3a-212">Vedere [Ottenere telefoni per Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="2cc3a-212">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="2cc3a-213">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-213">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="2cc3a-214">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-214">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="2cc3a-215">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-215">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="2cc3a-216">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-216">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="2cc3a-217">Microsoft Teams Windows client (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-217">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2cc3a-218">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="2cc3a-218">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="2cc3a-219">Microsoft Teams in [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="2cc3a-219">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="2cc3a-220">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="2cc3a-220">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="2cc3a-221">Microsoft Teams App Android</span><span class="sxs-lookup"><span data-stu-id="2cc3a-221">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="2cc3a-222">Le code di chiamata a cui è assegnato un numero di instradamento diretto non supportano Skype for Business client, client Lync o telefoni IP Skype for Business telefoni IP come agenti.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-222">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="2cc3a-223">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="2cc3a-223">Call queue cmdlets</span></span>

<span data-ttu-id="2cc3a-224">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-224">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="2cc3a-225">Ecco i cmdlet che si usano per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2cc3a-225">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="2cc3a-226">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2cc3a-226">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="2cc3a-227">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2cc3a-227">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="2cc3a-228">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2cc3a-228">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="2cc3a-229">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2cc3a-229">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="2cc3a-230">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2cc3a-230">Related topics</span></span>

[<span data-ttu-id="2cc3a-231">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="2cc3a-231">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="2cc3a-232">[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="2cc3a-232">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="2cc3a-233">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="2cc3a-233">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="2cc3a-234">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="2cc3a-234">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="2cc3a-235">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2cc3a-235">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
