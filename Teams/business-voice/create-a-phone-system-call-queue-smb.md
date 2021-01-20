---
title: Creare una coda di chiamata in Microsoft teams-esercitazione sulle piccole imprese
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Informazioni su come configurare le code di chiamata con Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909635"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="5918d-103">Creare una coda di chiamata-esercitazione sulle piccole imprese</span><span class="sxs-lookup"><span data-stu-id="5918d-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="5918d-104">Le code di chiamata offrono un metodo per indirizzare i chiamanti alle persone dell'organizzazione che possono aiutarti con un problema o una domanda particolare.</span><span class="sxs-lookup"><span data-stu-id="5918d-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="5918d-105">Le chiamate vengono distribuite una alla volta per gli utenti della coda (noti come *agenti*).</span><span class="sxs-lookup"><span data-stu-id="5918d-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="5918d-106">Le code di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="5918d-106">Call queues provide:</span></span>

- <span data-ttu-id="5918d-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="5918d-107">A greeting message.</span></span>

- <span data-ttu-id="5918d-108">Musica mentre gli utenti attendono il blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="5918d-109">Chiamata routing-in *First in, First out* (FIFO) Order-to Agents.</span><span class="sxs-lookup"><span data-stu-id="5918d-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="5918d-110">Opzioni di gestione per l'overflow e il timeout delle code.</span><span class="sxs-lookup"><span data-stu-id="5918d-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="5918d-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5918d-111">Before you begin</span></span>

<span data-ttu-id="5918d-112">Ottenere alcune [licenze per gli utenti virtuali nel sistema telefonico,](../teams-add-on-licensing/virtual-user.md) se non sono già disponibili.</span><span class="sxs-lookup"><span data-stu-id="5918d-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="5918d-113">Ottenere uno per ogni coda di chiamata e operatore automatico che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="5918d-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="5918d-114">Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche extra nel caso in cui decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="5918d-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="5918d-115">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="5918d-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="5918d-116">Per altre informazioni, vedere [gestire i criteri di ID chiamante in Microsoft teams](../caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="5918d-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="5918d-117">Seguire questa procedura per configurare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="5918d-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="5918d-118">Passaggio 1 <br> creare un team</span><span class="sxs-lookup"><span data-stu-id="5918d-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="5918d-119">Quando si crea una coda di chiamata, è possibile aggiungere singoli utenti alla coda oppure usare un gruppo di sicurezza esistente, un gruppo Microsoft 365 o un team di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5918d-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="5918d-120">È consigliabile usare un team.</span><span class="sxs-lookup"><span data-stu-id="5918d-120">We recommend using a team.</span></span> <span data-ttu-id="5918d-121">Ciò consente ai membri della coda di chattare tra loro, condividere idee e creare documenti o altre risorse per aiutarli a aiutare i clienti.</span><span class="sxs-lookup"><span data-stu-id="5918d-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="5918d-122">Un team offre anche una cassetta postale vocale per i chiamanti che lasciano un messaggio dopo le ore o se la coda raggiunge la sua capacità massima.</span><span class="sxs-lookup"><span data-stu-id="5918d-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="5918d-123">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="5918d-123">To create a team</span></span>

1. <span data-ttu-id="5918d-124">Prima di tutto, fai clic su **Teams** sul lato sinistro dell'app, quindi fai clic su **partecipa o crea un team** nella parte inferiore dell'elenco teams.</span><span class="sxs-lookup"><span data-stu-id="5918d-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="5918d-125">Quindi fare clic su **Crea team** (prima carta, angolo in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="5918d-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="5918d-126">Scegliere **Crea un team da zero**.</span><span class="sxs-lookup"><span data-stu-id="5918d-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="5918d-127">Scegliere quindi se si vuole un team pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="5918d-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="5918d-128">È consigliabile **private** per la coda di chiamata per evitare che gli utenti involontariamente partecipino alla coda unendo il team.</span><span class="sxs-lookup"><span data-stu-id="5918d-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="5918d-129">Assegnare un nome al team e aggiungere una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="5918d-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="5918d-130">Al termine, fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5918d-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="5918d-131">Digitare i nomi delle persone che si desidera includere nella coda di chiamata e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="5918d-132">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-132">Click **Close**.</span></span> <span data-ttu-id="5918d-133">Gli utenti aggiunti a un team riceveranno un messaggio di posta elettronica che informa che ora sono membri del team e che il team verrà visualizzato nell'elenco teams.</span><span class="sxs-lookup"><span data-stu-id="5918d-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5918d-134">Passaggio 2->degli account risorse </span><span class="sxs-lookup"><span data-stu-id="5918d-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="5918d-135"><br>Account delle risorse del passaggio 2</span><span class="sxs-lookup"><span data-stu-id="5918d-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="5918d-136">Ogni coda di chiamata creata richiede un account di risorse.</span><span class="sxs-lookup"><span data-stu-id="5918d-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="5918d-137">Questo è simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="5918d-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="5918d-138">In questo passaggio creeremo l'account, gli assegnaremo un *sistema telefonico Microsoft 365-* licenza per gli utenti virtuali e lo useremo per iniziare a creare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="5918d-139">Creare un account di risorse</span><span class="sxs-lookup"><span data-stu-id="5918d-139">Create a resource account</span></span>

<span data-ttu-id="5918d-140">È possibile creare un account risorse nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="5918d-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="5918d-141">Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.</span><span class="sxs-lookup"><span data-stu-id="5918d-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="5918d-142">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-142">Click **Add**.</span></span>

3. <span data-ttu-id="5918d-143">Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato**, **nomeutente** e scegliere **coda di chiamata** per il **tipo di account risorse**.</span><span class="sxs-lookup"><span data-stu-id="5918d-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Screenshot dell'interfaccia utente Aggiungi account risorse](../media/resource-account-add-cq.png)

4. <span data-ttu-id="5918d-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5918d-145">Click **Save**.</span></span>

<span data-ttu-id="5918d-146">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="5918d-146">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="5918d-148">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="5918d-148">Assign a license</span></span>

<span data-ttu-id="5918d-149">È necessario assegnare un *sistema telefonico Microsoft 365-licenza utente virtuale* per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5918d-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="5918d-150">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="5918d-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="5918d-151">Nella scheda **licenze e app** , in **licenze**, selezionare **Microsoft 365 Phone System-Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="5918d-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="5918d-152">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="5918d-152">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="5918d-154">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="5918d-154">Create a call queue</span></span>

<span data-ttu-id="5918d-155">Inizieremo quindi a creare una nuova coda di chiamata e ad assegnare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5918d-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="5918d-156">Nell'interfaccia di amministrazione di teams espandere **Voice**, fare clic su **code di chiamata** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="5918d-157">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-157">Type a name for the call queue.</span></span> <span data-ttu-id="5918d-158">Gli agenti vedranno questo nome quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="5918d-159">Fare clic su **Aggiungi account**, cercare l'account risorse che si vuole usare con la coda di chiamata, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="5918d-160">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="5918d-160">Choose a language.</span></span> <span data-ttu-id="5918d-161">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="5918d-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Screenshot delle impostazioni dell'account delle risorse e della lingua](../media/call-queue-name-language.png)

4. <span data-ttu-id="5918d-163">Specificare se si vuole riprodurre un saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="5918d-164">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto che si vuole riprodurre.</span><span class="sxs-lookup"><span data-stu-id="5918d-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="5918d-165">Teams offre musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="5918d-166">Se si vuole riprodurre un file audio specifico, scegliere **Riproduci un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="5918d-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="5918d-167">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="5918d-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="5918d-168">La musica predefinita fornita nelle code delle chiamate di teams è priva di qualsiasi royalties pagabile dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5918d-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="5918d-169">Passaggio 3-chiamare gli agenti ></span><span class="sxs-lookup"><span data-stu-id="5918d-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="5918d-170">Passaggio 3 <br> chiama agenti</span><span class="sxs-lookup"><span data-stu-id="5918d-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="5918d-171">Per aggiungere agenti alla coda di chiamata, aggiungiamo il team creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5918d-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="5918d-172">Fare clic su **Aggiungi gruppi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="5918d-173">Digitare il nome del team creato.</span><span class="sxs-lookup"><span data-stu-id="5918d-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="5918d-174">Fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5918d-174">Click **Add**, and then click **Add**.</span></span>

    ![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="5918d-176">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi o team.</span><span class="sxs-lookup"><span data-stu-id="5918d-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="5918d-177">Quando si aggiungono nuovi utenti al team, possono essere necessarie fino a otto ore per la prima chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="5918d-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5918d-178">Passaggio 4->degli account risorse </span><span class="sxs-lookup"><span data-stu-id="5918d-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="5918d-179">Passaggio 4 <br> chiamata di routing</span><span class="sxs-lookup"><span data-stu-id="5918d-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="5918d-180">Scegliere il metodo di routing delle chiamate che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="5918d-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="5918d-181">Impostare la **modalità conferenza** su **auto**.</span><span class="sxs-lookup"><span data-stu-id="5918d-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="5918d-182">Scegliere il **metodo di routing** che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="5918d-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="5918d-183">In questo modo viene determinato l'ordine in cui gli agenti ricevono chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="5918d-184">È consigliabile un **routing seriale** o  **Round Robin**.</span><span class="sxs-lookup"><span data-stu-id="5918d-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="5918d-185">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5918d-185">Choose from these options:</span></span>

    - <span data-ttu-id="5918d-186">Il **routing di Attendant** squilla tutti gli agenti della coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5918d-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="5918d-187">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="5918d-188">Il **routing seriale** squilla tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="5918d-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="5918d-189">Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.</span><span class="sxs-lookup"><span data-stu-id="5918d-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="5918d-190">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="5918d-191">Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="5918d-192">Le rotte **inattive più lunghe** ogni chiamata all'agente che è stato inattivo il tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="5918d-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="5918d-193">Gli agenti il cui stato presenza è stato assente per più di 10 minuti non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="5918d-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Screenshot della modalità conferenza e delle impostazioni del metodo di routing](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="5918d-195">Attivare il **routing basato sulla presenza** .</span><span class="sxs-lookup"><span data-stu-id="5918d-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="5918d-196">Questo instrada le chiamate agli agenti di cui è **disponibile** lo stato presenza.</span><span class="sxs-lookup"><span data-stu-id="5918d-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="5918d-197">Scegliere se si vuole consentire agli agenti di rifiutare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="5918d-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="5918d-198">Impostare il **tempo di avviso** di un agente per specificare la durata dell'interlinea telefonica di un agente prima che la chiamata venga reindirizzata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="5918d-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Screenshot delle impostazioni di routing, disattivazione e ora di avviso](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="5918d-200">Passaggio 5->di overflow delle chiamate </span><span class="sxs-lookup"><span data-stu-id="5918d-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="5918d-201">Passaggio 5- <br> overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="5918d-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="5918d-202">Scegliere la modalità di gestione delle chiamate che superano il massimo nella coda.</span><span class="sxs-lookup"><span data-stu-id="5918d-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="5918d-203">Impostare le **chiamate massime nella coda**.</span><span class="sxs-lookup"><span data-stu-id="5918d-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="5918d-204">Scegliere cosa si vuole fare quando viene raggiunto il numero massimo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="5918d-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="5918d-205">È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="5918d-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="5918d-206">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5918d-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="5918d-207">**Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="5918d-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="5918d-208">**App vocale** : un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="5918d-209">Scegliere l'account delle risorse associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="5918d-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="5918d-210">**Numero di telefono esterno** -qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5918d-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="5918d-211">Usare questo formato: + [codice paese] [prefisso] [numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="5918d-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="5918d-212">**Segreteria telefonica** : è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="5918d-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="5918d-214">Passaggio 6-Timeout chiamata ></span><span class="sxs-lookup"><span data-stu-id="5918d-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="5918d-215">Passaggio 6 <br> timeout chiamata</span><span class="sxs-lookup"><span data-stu-id="5918d-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="5918d-216">Scegliere cosa si vuole fare quando le chiamate sono state attese in coda troppo a lungo.</span><span class="sxs-lookup"><span data-stu-id="5918d-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="5918d-217">Impostare il **timeout della chiamata: tempo massimo di attesa**.</span><span class="sxs-lookup"><span data-stu-id="5918d-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="5918d-218">Scegliere cosa si vuole fare quando si esce da una chiamata. È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="5918d-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="5918d-219">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5918d-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="5918d-220">**Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="5918d-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="5918d-221">**App vocale** : un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="5918d-222">Scegliere l'account delle risorse associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="5918d-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="5918d-223">**Numero di telefono esterno** -qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5918d-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="5918d-224">Usare questo formato: + [codice paese] [prefisso] [numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="5918d-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="5918d-225">**Segreteria telefonica** : è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="5918d-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="5918d-227">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5918d-227">Click **Save**.</span></span>

<span data-ttu-id="5918d-228">In questo articolo viene completata la configurazione della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5918d-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="5918d-229">È quindi consigliabile [configurare un operatore automatico](create-a-phone-system-auto-attendant-smb.md).</span><span class="sxs-lookup"><span data-stu-id="5918d-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

