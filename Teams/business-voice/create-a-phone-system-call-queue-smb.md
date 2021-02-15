---
title: Creare una coda di chiamata in Microsoft Teams - esercitazione aziendale
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
description: Scopri come impostare code di chiamata con Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909635"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="31cfa-103">Creare una coda di chiamata - esercitazione per piccole aziende</span><span class="sxs-lookup"><span data-stu-id="31cfa-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="31cfa-104">Le code di chiamata sono un metodo per instradare i chiamanti all'interno dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="31cfa-105">Le chiamate vengono distribuite una alla volta alle persone in coda (che sono noti come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="31cfa-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="31cfa-106">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="31cfa-106">Call queues provide:</span></span>

- <span data-ttu-id="31cfa-107">Un messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="31cfa-107">A greeting message.</span></span>

- <span data-ttu-id="31cfa-108">Musica persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="31cfa-109">Instradamento delle chiamate ( in *ordine FIFO ,First In, First Out)* - agli agenti.</span><span class="sxs-lookup"><span data-stu-id="31cfa-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="31cfa-110">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="31cfa-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="31cfa-111">Before you begin</span></span>

<span data-ttu-id="31cfa-112">Ottieni alcune [licenze Sistema telefonico - Utente virtuale,](../teams-add-on-licensing/virtual-user.md) se non le hai già.</span><span class="sxs-lookup"><span data-stu-id="31cfa-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="31cfa-113">Ottieni un'opzione per ogni coda di chiamata e operatore automatico che hai intenzione di impostare.</span><span class="sxs-lookup"><span data-stu-id="31cfa-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="31cfa-114">Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore prodotto se decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="31cfa-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="31cfa-115">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="31cfa-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="31cfa-116">Per [altre informazioni, vedere Gestire i criteri ID chiamante in Microsoft Teams.](../caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="31cfa-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="31cfa-117">Seguire questa procedura per impostare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="31cfa-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="31cfa-118">Passaggio <br> 1: Creare un team</span><span class="sxs-lookup"><span data-stu-id="31cfa-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="31cfa-119">Quando crei una coda di chiamata, puoi aggiungere singoli utenti alla coda oppure puoi utilizzare un gruppo di sicurezza esistente, un gruppo di Microsoft 365 o un team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31cfa-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="31cfa-120">È consigliabile usare un team.</span><span class="sxs-lookup"><span data-stu-id="31cfa-120">We recommend using a team.</span></span> <span data-ttu-id="31cfa-121">In questo modo i membri della coda possono chattare tra loro, condividere idee e creare documenti o altre risorse per aiutarli a aiutare i clienti.</span><span class="sxs-lookup"><span data-stu-id="31cfa-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="31cfa-122">Un team fornisce anche una cassetta postale vocale in cui i chiamanti possono lasciare un messaggio fuori orario o se la coda raggiunge la sua capacità massima.</span><span class="sxs-lookup"><span data-stu-id="31cfa-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="31cfa-123">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="31cfa-123">To create a team</span></span>

1. <span data-ttu-id="31cfa-124">Prima di tutto, fai clic su **Teams** sul lato sinistro dell'app, quindi fai clic su **Partecipa o crea** un team in fondo all'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="31cfa-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="31cfa-125">Quindi fai **clic su Crea team** (prima scheda, angolo in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="31cfa-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="31cfa-126">Scegliere **Crea un team da zero.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="31cfa-127">Successivamente, scegliere se si vuole un team pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="31cfa-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="31cfa-128">Si consiglia **di usare** il servizio privato per la coda di chiamata per evitare che le persone diventino involontariamente parte della coda partecipando al team.</span><span class="sxs-lookup"><span data-stu-id="31cfa-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="31cfa-129">Assegnare un nome al team e aggiungere una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="31cfa-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="31cfa-130">Al termine, fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="31cfa-131">Digita i nomi delle persone che desideri inserire nella coda di chiamata, quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="31cfa-132">Fare clic **su Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-132">Click **Close**.</span></span> <span data-ttu-id="31cfa-133">Le persone che si aggiungono a un team riceveranno un messaggio di posta elettronica che le informa che sono ora membri del team e il team verrà visualizzato nell'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="31cfa-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="31cfa-134">Passaggio 2 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="31cfa-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="31cfa-135">Account delle risorse del passaggio 2 <br></span><span class="sxs-lookup"><span data-stu-id="31cfa-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="31cfa-136">Per ogni coda di chiamata creata è necessario un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="31cfa-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="31cfa-137">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="31cfa-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="31cfa-138">In questo passaggio creeremo l'account, gli assegniamo una licenza Sistema telefonico *Microsoft 365 -* Utente virtuale e quindi lo useremo per iniziare a creare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="31cfa-139">Creare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="31cfa-139">Create a resource account</span></span>

<span data-ttu-id="31cfa-140">È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="31cfa-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="31cfa-141">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="31cfa-142">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="31cfa-142">Click **Add**.</span></span>

3. <span data-ttu-id="31cfa-143">Nel riquadro **Aggiungi account risorsa,** compilare **Nome** visualizzato **,** Nome utente e scegliere Coda di chiamata **per** il tipo di account **risorsa.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Screenshot dell'interfaccia utente aggiungi account risorsa](../media/resource-account-add-cq.png)

4. <span data-ttu-id="31cfa-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31cfa-145">Click **Save**.</span></span>

<span data-ttu-id="31cfa-146">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="31cfa-146">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="31cfa-148">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="31cfa-148">Assign a license</span></span>

<span data-ttu-id="31cfa-149">È necessario assegnare una *licenza Sistema telefonico Microsoft 365 -* Utente virtuale all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="31cfa-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="31cfa-150">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="31cfa-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="31cfa-151">Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="31cfa-152">Fare clic **su Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-152">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="31cfa-154">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="31cfa-154">Create a call queue</span></span>

<span data-ttu-id="31cfa-155">A questo punto, inizieremo a creare una nuova coda di chiamata e ad assegnare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="31cfa-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="31cfa-156">Nell'interfaccia di amministrazione di Teams espandi **Voce,** fai clic su **Code di** chiamata, quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="31cfa-157">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-157">Type a name for the call queue.</span></span> <span data-ttu-id="31cfa-158">Gli agenti riceveranno questo nome quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="31cfa-159">Fare **clic su Aggiungi** account, cercare l'account delle risorse da usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="31cfa-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="31cfa-160">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="31cfa-160">Choose a language.</span></span> <span data-ttu-id="31cfa-161">Questa lingua verrà utilizzata per i comandi vocali generati dal sistema e per la trascrizione della segreteria telefonica (se li abiliti).</span><span class="sxs-lookup"><span data-stu-id="31cfa-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Screenshot delle impostazioni dell'account della risorsa e della lingua](../media/call-queue-name-language.png)

4. <span data-ttu-id="31cfa-163">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="31cfa-164">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="31cfa-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="31cfa-165">Teams offre musica predefinita ai chiamanti mentre sono in attesa in coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="31cfa-166">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="31cfa-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="31cfa-167">Le dimensioni della registrazione caricata non possono essere superiori a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="31cfa-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="31cfa-168">La musica predefinita fornita nelle code di chiamata di Teams è gratuita di tutte le royalties pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="31cfa-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="31cfa-169">Fase 3 - Chiamare gli agenti ></span><span class="sxs-lookup"><span data-stu-id="31cfa-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="31cfa-170">Passaggio <br> 3: Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="31cfa-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="31cfa-171">Per aggiungere agenti alla coda di chiamata, aggiungeremo il team che abbiamo creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="31cfa-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="31cfa-172">Fare **clic su Aggiungi gruppi.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="31cfa-173">Digitare il nome del team creato.</span><span class="sxs-lookup"><span data-stu-id="31cfa-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="31cfa-174">Fare **clic su** Aggiungi e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-174">Click **Add**, and then click **Add**.</span></span>

    ![Schermata delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="31cfa-176">È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 tramite gruppi o team.</span><span class="sxs-lookup"><span data-stu-id="31cfa-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="31cfa-177">Quando vengono aggiunti nuovi utenti al team, per l'arrivo della prima chiamata possono essere necessario fino a otto ore.</span><span class="sxs-lookup"><span data-stu-id="31cfa-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="31cfa-178">Passaggio 4 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="31cfa-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="31cfa-179">Passaggio 4 Routing <br> delle chiamate</span><span class="sxs-lookup"><span data-stu-id="31cfa-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="31cfa-180">Scegliere il metodo di instradamento chiamate da usare.</span><span class="sxs-lookup"><span data-stu-id="31cfa-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="31cfa-181">Impostare **la modalità conferenza** su **Auto.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="31cfa-182">Scegliere **il metodo** di instradamento da usare.</span><span class="sxs-lookup"><span data-stu-id="31cfa-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="31cfa-183">Determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="31cfa-184">È consigliabile **il routing seriale** **o il round robin.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="31cfa-185">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31cfa-185">Choose from these options:</span></span>

    - <span data-ttu-id="31cfa-186">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="31cfa-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="31cfa-187">Il primo agente di chiamata a ritirare la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="31cfa-188">**L'instradamento** seriale squilla tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="31cfa-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="31cfa-189">Se un agente ignora o non riceve una chiamata, la chiamata squillerà sul successivo agente e proverà tutti gli agenti fino al ritiro o al timeout.</span><span class="sxs-lookup"><span data-stu-id="31cfa-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="31cfa-190">**Round Robin** bilancia l'instradamento delle chiamate in arrivo in modo che ogni agente di chiamata riceve lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="31cfa-191">Può essere desiderabile in un ambiente di vendita in entrata per assicurare la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="31cfa-192">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="31cfa-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="31cfa-193">Gli agenti il cui stato presenza è Fuori rete da più di 10 minuti non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="31cfa-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Schermata delle impostazioni per la modalità conferenza e il metodo di instradamento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="31cfa-195">Attivare **il routing basato sulla** presenza.</span><span class="sxs-lookup"><span data-stu-id="31cfa-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="31cfa-196">In questo modo le chiamate vengono instrade agli agenti il cui stato presenza è **Disponibile.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="31cfa-197">Scegli se consentire agli agenti di rifiutare esplicitamente le chiamate.</span><span class="sxs-lookup"><span data-stu-id="31cfa-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="31cfa-198">Imposta un **orario di avviso per l'agente** per specificare per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="31cfa-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Screenshot delle impostazioni per l'instradamento, il rifiuto esplicito e l'ora degli avvisi](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="31cfa-200">Fase 5 - Overflow della chiamata ></span><span class="sxs-lookup"><span data-stu-id="31cfa-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="31cfa-201">Passaggio 5 <br> Overflow chiamata</span><span class="sxs-lookup"><span data-stu-id="31cfa-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="31cfa-202">Scegliere come gestire le chiamate che superano il valore massimo in coda.</span><span class="sxs-lookup"><span data-stu-id="31cfa-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="31cfa-203">Impostare il **numero massimo di chiamate in coda.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="31cfa-204">Scegli l'operazione da eseguire quando viene raggiunto il numero massimo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="31cfa-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="31cfa-205">Puoi disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="31cfa-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="31cfa-206">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31cfa-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="31cfa-207">**Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="31cfa-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="31cfa-208">**App voce:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="31cfa-209">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="31cfa-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="31cfa-210">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="31cfa-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="31cfa-211">Usa questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="31cfa-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="31cfa-212">**Casella vocale:** è possibile usare la casella vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="31cfa-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Schermata delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="31cfa-214">Fase 6 - Timeout della chiamata ></span><span class="sxs-lookup"><span data-stu-id="31cfa-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="31cfa-215">Passaggio 6 <br> Timeout chiamata</span><span class="sxs-lookup"><span data-stu-id="31cfa-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="31cfa-216">Scegli cosa vuoi fare quando le chiamate sono in coda da troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="31cfa-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="31cfa-217">Impostare il **timeout della chiamata: tempo massimo di attesa.**</span><span class="sxs-lookup"><span data-stu-id="31cfa-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="31cfa-218">Scegli l'operazione da eseguire al timeout di una chiamata. Puoi disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="31cfa-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="31cfa-219">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31cfa-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="31cfa-220">**Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="31cfa-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="31cfa-221">**App voce:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="31cfa-222">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="31cfa-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="31cfa-223">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="31cfa-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="31cfa-224">Usa questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="31cfa-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="31cfa-225">**Casella vocale:** è possibile usare la casella vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="31cfa-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Schermata delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="31cfa-227">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31cfa-227">Click **Save**.</span></span>

<span data-ttu-id="31cfa-228">L'impostazione della coda di chiamata viene completata.</span><span class="sxs-lookup"><span data-stu-id="31cfa-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="31cfa-229">Successivamente, puoi impostare [un operatore automatico.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="31cfa-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

