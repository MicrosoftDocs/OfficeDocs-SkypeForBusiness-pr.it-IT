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
ms.openlocfilehash: a8dbcddbbc7b0717678f56a2876b617d06f49187
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428202"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="fddff-103">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-103">Create a call queue</span></span>

<span data-ttu-id="fddff-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="fddff-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="fddff-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="fddff-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="fddff-106">Questo articolo è per le organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fddff-106">This article is for large organizations.</span></span> <span data-ttu-id="fddff-107">Se l'organizzazione è una piccola azienda, vedere Creare una coda [di chiamata - esercitazione sulle piccole](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) imprese.</span><span class="sxs-lookup"><span data-stu-id="fddff-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="fddff-108">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="fddff-108">Call queues provide:</span></span>

- <span data-ttu-id="fddff-109">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="fddff-109">A greeting message.</span></span>

- <span data-ttu-id="fddff-110">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="fddff-111">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="fddff-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="fddff-112">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="fddff-113">Assicurarsi di aver letto Pianificare [gli](plan-auto-attendant-call-queue.md) operatori Teams e le [](plan-auto-attendant-call-queue.md#getting-started) code di chiamata e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fddff-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fddff-114">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="fddff-114">Video demonstration</span></span>

<span data-ttu-id="fddff-115">Questo video mostra un esempio di base di come creare una coda di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="fddff-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="fddff-116">Creare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-116">Create the call queue</span></span>

<span data-ttu-id="fddff-117">Per configurare una coda di chiamata, nell'interfaccia Teams di amministrazione espandere **Voce,** fare clic su Code di chiamata **e** quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fddff-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="fddff-118">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-118">Type a name for the call queue.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="fddff-119">Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="fddff-119">Resource accounts</span></span>

![Screenshot delle impostazioni dell'account delle risorse](media/call-queue-name-language.png)

<span data-ttu-id="fddff-121">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="fddff-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="fddff-122">Gli agenti visualizzano il nome dell'account della risorsa quando ricevono una chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="fddff-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="fddff-123">Assegnare l'ID chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-123">Assign calling ID</span></span>

![Screenshot delle impostazioni dell'ID chiamata](media/call-queue-assign-calling-id.png)

<span data-ttu-id="fddff-125">Se si prevede di usare un canale Teams per gli agenti di chiamata, è possibile assegnare un numero di ID chiamante in uscita per gli agenti specificando uno o più account delle risorse con un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="fddff-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="fddff-126">Fare **clic su** Aggiungi , cercare gli account delle risorse a cui consentire agli agenti di effettuare chiamate con ID durante le chiamate in uscita, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fddff-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="fddff-127">Se non si usa un canale di Teams per controllare l'appartenenza all'agente, è consigliabile impostare direttamente l'ID chiamante per i membri della coda di chiamata sul numero di servizio della coda di chiamata o sull'operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="fddff-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="fddff-128">Per altre informazioni, vedere Gestire i [criteri id chiamante in Microsoft Teams](caller-id-policies.md) chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="language"></a><span data-ttu-id="fddff-129">Lingua</span><span class="sxs-lookup"><span data-stu-id="fddff-129">Language</span></span>

![Screenshot delle impostazioni della lingua](media/call-queue-language.png)

<span data-ttu-id="fddff-131">Scegliere una [lingua supportata.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="fddff-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="fddff-132">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="fddff-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="fddff-133">Messaggi di saluto e musica in attesa in coda</span><span class="sxs-lookup"><span data-stu-id="fddff-133">Greetings and music on hold in queue</span></span>

![Screenshot di messaggi di saluto e musica in attesa nelle impostazioni della coda](media/call-queue-greetings-music.png)

<span data-ttu-id="fddff-135">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="fddff-136">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="fddff-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span> <span data-ttu-id="fddff-137">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="fddff-137">The uploaded recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="fddff-138">Teams musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-138">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="fddff-139">La musica predefinita fornita nelle code Teams chiamate è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fddff-139">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> <span data-ttu-id="fddff-140">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="fddff-140">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="fddff-141">L'utente è responsabile della cancellazione e della protezione indipendente di tutti i diritti e le autorizzazioni necessari per l'uso di qualsiasi file musicale o audio con il servizio di Microsoft Teams, che possono includere proprietà intellettuale e altri diritti in qualsiasi musica, effetti sonori, audio, marchi, nomi e altri contenuti nel file audio di tutti i titolari dei diritti pertinenti, che possono includere artisti, attori, interpreti, musicisti, cantautori, compositori, etichette di registrazione, editori musicali, unioni, corporazioni, società di diritti, organizzazioni di gestione collettiva e qualsiasi altra parte proprietaria, controllo o licenza del copyright musicale, degli effetti sonori, dell'audio e di altri diritti di proprietà intellettuale.</span><span class="sxs-lookup"><span data-stu-id="fddff-141">You are responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service, which may include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders, which may include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations and any other parties who own, control or license the music copyrights, sound effects, audio and other intellectual property rights.</span></span>

## <a name="call-agents"></a><span data-ttu-id="fddff-142">Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-142">Call agents</span></span>

<span data-ttu-id="fddff-143">Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="fddff-143">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="fddff-145">Teams canale</span><span class="sxs-lookup"><span data-stu-id="fddff-145">Teams channel</span></span>

<span data-ttu-id="fddff-146">È possibile aggiungere fino a 200 agenti tramite un Teams canale.</span><span class="sxs-lookup"><span data-stu-id="fddff-146">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="fddff-147">Se si vuole usare un canale Teams per gestire la [coda,](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)selezionare l'opzione **Scegli un team** e fare clic su Aggiungi **canale.**</span><span class="sxs-lookup"><span data-stu-id="fddff-147">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="fddff-148">Cercare il team da usare, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fddff-148">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="fddff-149">Selezionare il canale da usare e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="fddff-149">Select the channel that you want to use and click **Apply**.</span></span> <span data-ttu-id="fddff-150">È necessario essere un membro del team o il creatore di o un proprietario del canale.</span><span class="sxs-lookup"><span data-stu-id="fddff-150">You must be a member of the team or the creator of or an owner of the channel.</span></span>

<span data-ttu-id="fddff-151">I client seguenti sono supportati quando si usa un canale Teams per le code di chiamata:</span><span class="sxs-lookup"><span data-stu-id="fddff-151">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="fddff-152">Microsoft Teams Windows client</span><span class="sxs-lookup"><span data-stu-id="fddff-152">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="fddff-153">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="fddff-153">Microsoft Teams Mac client</span></span>

> [!NOTE]
> <span data-ttu-id="fddff-154">Se si usa questa opzione, la piena operatività della coda di chiamata può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="fddff-154">If you use this option, it can take up to 24 hours for the call queue to be fully operational.</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="fddff-155">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="fddff-155">Users and groups</span></span>

<span data-ttu-id="fddff-156">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.</span><span class="sxs-lookup"><span data-stu-id="fddff-156">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="fddff-157">Per aggiungere singoli utenti o gruppi alla coda, selezionare **l'opzione Scegli utenti e** gruppi.</span><span class="sxs-lookup"><span data-stu-id="fddff-157">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="fddff-158">Per aggiungere un utente alla coda, fare clic **su Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fddff-158">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="fddff-159">Per aggiungere un gruppo alla coda, fare clic **su Aggiungi gruppi,** cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fddff-159">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="fddff-160">È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o Microsoft Teams team.</span><span class="sxs-lookup"><span data-stu-id="fddff-160">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="fddff-161">I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore prima dell'arrivo della prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-161">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="fddff-162">Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="fddff-162">Call routing</span></span>

![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="fddff-164">**La modalità conferenza** riduce significativamente il tempo necessario per la connessione di un chiamante a un agente, dopo che l'agente ha accettato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-164">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="fddff-165">Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="fddff-165">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="fddff-166">La versione più recente del client desktop Microsoft Teams, dell'app Android o dell'app iOS</span><span class="sxs-lookup"><span data-stu-id="fddff-166">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="fddff-167">Microsoft Teams telefono 1449/1.0.94.2020051601 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="fddff-167">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="fddff-168">Gli account Teams agenti devono essere impostati sulla modalità Teams solo utenti.</span><span class="sxs-lookup"><span data-stu-id="fddff-168">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="fddff-169">Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-169">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="fddff-170">È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.</span><span class="sxs-lookup"><span data-stu-id="fddff-170">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="fddff-171">La modalità conferenza non è supportata se le chiamate telefoniche vengono instradati alla coda da un gateway di routing diretto abilitato per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="fddff-171">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

> [!TIP]
> <span data-ttu-id="fddff-172">**L'impostazione consigliata è** **La** modalità conferenza è Automatica.</span><span class="sxs-lookup"><span data-stu-id="fddff-172">Setting **Conference mode** to **Auto** is the recommended setting.</span></span>

<span data-ttu-id="fddff-173">**Il metodo di** routing determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-173">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="fddff-174">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fddff-174">Choose from these options:</span></span>

- <span data-ttu-id="fddff-175">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="fddff-175">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="fddff-176">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-176">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="fddff-177">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta nell'ordine specificato nell'elenco **Agenti di** chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-177">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="fddff-178">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="fddff-178">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="fddff-179">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-179">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="fddff-180">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-180">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="fddff-181">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="fddff-181">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="fddff-182">Un agente è considerato inattivo se lo stato di presenza è Disponibile o se lo stato presenza è Stato Non al computer per meno di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="fddff-182">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="fddff-183">Gli agenti il cui stato presenza è Stato Non al computer per più di 10 minuti non vengono considerati inattivi e non saranno idonei a ricevere chiamate finché non cambiano la propria presenza in Disponibile.</span><span class="sxs-lookup"><span data-stu-id="fddff-183">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

> [!TIP]
> <span data-ttu-id="fddff-184">**L'impostazione consigliata è** Round **robin** o **Inattività** più lunga.</span><span class="sxs-lookup"><span data-stu-id="fddff-184">Setting **Routing Method** to **Round robin** or **Longest idle** is the recommended setting.</span></span>

![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](media/call-queue-presence-agents-time.png)

<span data-ttu-id="fddff-186">**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato.</span><span class="sxs-lookup"><span data-stu-id="fddff-186">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="fddff-187">Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di routing delle chiamate e possono ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-187">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="fddff-188">Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="fddff-188">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="fddff-189">È possibile abilitare il routing delle chiamate basate sulla presenza con uno qualsiasi dei metodi di routing.</span><span class="sxs-lookup"><span data-stu-id="fddff-189">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="fddff-190">Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate indipendentemente dal relativo stato di disponibilità impostato.</span><span class="sxs-lookup"><span data-stu-id="fddff-190">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="fddff-191">Quando **l'opzione** Inattività più lunga è selezionata come metodo di routing, il routing  basato sulla presenza è obbligatorio e abilitato automaticamente anche se l'interruttore routing basato sulla presenza sarà disattivato e disattivato.</span><span class="sxs-lookup"><span data-stu-id="fddff-191">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>
>
> <span data-ttu-id="fddff-192">Se il routing basato sulla presenza non è abilitato e la coda contiene più chiamate, il sistema presenterà queste chiamate contemporaneamente agli agenti indipendentemente dal loro stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="fddff-192">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="fddff-193">In questo modo si riceveranno più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.</span><span class="sxs-lookup"><span data-stu-id="fddff-193">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>
> 
> <span data-ttu-id="fddff-194">Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="fddff-194">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="fddff-195">Se si hanno agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="fddff-195">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

> [!TIP]
> <span data-ttu-id="fddff-196">**L'impostazione consigliata è il routing basato** sulla presenza **su** Attivata.</span><span class="sxs-lookup"><span data-stu-id="fddff-196">Setting **Presence-based routing** to **On** is the recommended setting.</span></span>

<span data-ttu-id="fddff-197">**Tempo di avviso agente** specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="fddff-197">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

> [!TIP]
> <span data-ttu-id="fddff-198">**L'impostazione del tempo di avviso** dell'agente su **20 secondi** è l'impostazione consigliata.</span><span class="sxs-lookup"><span data-stu-id="fddff-198">Setting **Agent alert time** to **20 seconds** is the recommended setting.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="fddff-199">Gestione dell'overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="fddff-199">Call overflow handling</span></span>

![Screenshot delle impostazioni di overflow delle chiamate](media/call-queue-overflow-handling.png)

<span data-ttu-id="fddff-201">**Numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono essere in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="fddff-201">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="fddff-202">Il valore predefinito è 50, ma può essere compreso tra 0 e 200.</span><span class="sxs-lookup"><span data-stu-id="fddff-202">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="fddff-203">Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione Quando viene raggiunto il numero massimo **di** chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-203">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="fddff-204">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-204">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="fddff-205">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-205">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="fddff-206">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="fddff-206">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="fddff-207">Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.</span><span class="sxs-lookup"><span data-stu-id="fddff-207">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="fddff-208">Gestione del timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="fddff-208">Call timeout handling</span></span>

![Screenshot delle impostazioni di timeout delle chiamate](media/call-queue-timeout-handling.png)

<span data-ttu-id="fddff-210">**Timeout chiamata: il tempo di attesa** massimo specifica il tempo massimo di attesa di una chiamata in coda prima che venga reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="fddff-210">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="fddff-211">È possibile specificare un valore compreso tra 0 secondi e 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="fddff-211">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="fddff-212">È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fddff-212">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="fddff-213">Ad esempio, è possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.</span><span class="sxs-lookup"><span data-stu-id="fddff-213">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="fddff-214">Per i trasferimenti esterni, vedere Prerequisiti e trasferimenti di numeri di telefono esterni [- dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri. [](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="fddff-214">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="fddff-215">Dopo aver selezionato le opzioni di timeout della chiamata, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="fddff-215">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="summary-of-recommended-call-queue-settings"></a><span data-ttu-id="fddff-216">Riepilogo delle impostazioni consigliate per la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-216">Summary of recommended call queue settings</span></span>

<span data-ttu-id="fddff-217">Sono consigliate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fddff-217">The following settings are recommended:</span></span>

- <span data-ttu-id="fddff-218">**Modalità conferenza su** **Automatico**</span><span class="sxs-lookup"><span data-stu-id="fddff-218">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="fddff-219">**Metodo di instradamento** **a Round robin** o Più lungo **inattivo**</span><span class="sxs-lookup"><span data-stu-id="fddff-219">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="fddff-220">**Routing basato sulla presenza su** **On**</span><span class="sxs-lookup"><span data-stu-id="fddff-220">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="fddff-221">**Tempo di avviso dell'agente:** **a 20 secondi**</span><span class="sxs-lookup"><span data-stu-id="fddff-221">**Agent alert time:** to **20 seconds**</span></span>

## <a name="supported-clients"></a><span data-ttu-id="fddff-222">Client supportati</span><span class="sxs-lookup"><span data-stu-id="fddff-222">Supported clients</span></span>

<span data-ttu-id="fddff-223">I client seguenti sono supportati per gli agenti di chiamata in una coda di chiamata:</span><span class="sxs-lookup"><span data-stu-id="fddff-223">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="fddff-224">Skype for Business client desktop 2016 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="fddff-224">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="fddff-225">Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="fddff-225">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="fddff-226">Tutti i modelli di telefono IP supportati per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fddff-226">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="fddff-227">Vedere [Ottenere telefoni per Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="fddff-227">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="fddff-228">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="fddff-228">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="fddff-229">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="fddff-229">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="fddff-230">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="fddff-230">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="fddff-231">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="fddff-231">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="fddff-232">Microsoft Teams Windows client (versioni a 32 bit e a 64 bit)</span><span class="sxs-lookup"><span data-stu-id="fddff-232">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="fddff-233">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="fddff-233">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="fddff-234">Microsoft Teams in [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="fddff-234">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="fddff-235">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="fddff-235">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="fddff-236">Microsoft Teams App Android</span><span class="sxs-lookup"><span data-stu-id="fddff-236">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="fddff-237">Le code di chiamata a cui è assegnato un numero di instradamento diretto non supportano Skype for Business client, client Lync o telefoni IP Skype for Business telefoni IP come agenti.</span><span class="sxs-lookup"><span data-stu-id="fddff-237">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="fddff-238">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="fddff-238">Call queue cmdlets</span></span>

<span data-ttu-id="fddff-239">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-239">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="fddff-240">Ecco i cmdlet che si usano per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fddff-240">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="fddff-241">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="fddff-241">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="fddff-242">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="fddff-242">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="fddff-243">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="fddff-243">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="fddff-244">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="fddff-244">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="fddff-245">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fddff-245">Related topics</span></span>

[<span data-ttu-id="fddff-246">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="fddff-246">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="fddff-247">[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="fddff-247">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="fddff-248">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="fddff-248">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="fddff-249">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="fddff-249">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="fddff-250">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="fddff-250">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
