---
title: Creare una coda di chiamata in Microsoft Teams - Esercitazione sulle piccole imprese
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
ms.openlocfilehash: 3e75dbb75d9edffedbf25d42f197d8723e3ef9a4
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478366"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="dbbc5-103">Creare una coda di chiamata - Esercitazione sulle piccole imprese</span><span class="sxs-lookup"><span data-stu-id="dbbc5-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="dbbc5-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare con un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="dbbc5-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="dbbc5-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="dbbc5-106">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="dbbc5-106">Call queues provide:</span></span>

- <span data-ttu-id="dbbc5-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-107">A greeting message.</span></span>

- <span data-ttu-id="dbbc5-108">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="dbbc5-109">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="dbbc5-110">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="dbbc5-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dbbc5-111">Before you begin</span></span>

<span data-ttu-id="dbbc5-112">Ottenere un [sistema telefonico - Licenze utente virtuale](../teams-add-on-licensing/virtual-user.md) se non sono già disponibili.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="dbbc5-113">Ottenere una per ogni coda di chiamata e operatore automatico che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="dbbc5-114">Queste licenze sono gratuite, quindi ti consigliamo di ottenere un po' di più se decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="dbbc5-115">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="dbbc5-116">Per altre informazioni, vedere Gestire [i criteri id chiamante in Microsoft Teams.](../caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbbc5-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="dbbc5-117">Seguire questa procedura per configurare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="dbbc5-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="dbbc5-118">Passaggio 1 <br> Creare un team</span><span class="sxs-lookup"><span data-stu-id="dbbc5-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="dbbc5-119">Quando si crea una coda di chiamata, è possibile aggiungere singoli utenti alla coda oppure usare un gruppo di sicurezza esistente, un gruppo di Microsoft 365 o un team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="dbbc5-120">È [consigliabile usare un canale del team.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="dbbc5-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="dbbc5-121">In questo modo i membri della coda possono chattare tra loro, condividere idee e creare documenti o altre risorse per aiutare i clienti.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="dbbc5-122">Un team fornisce anche una cassetta postale vocale per consentire ai chiamanti di lasciare un messaggio dopo ore o se la coda raggiunge la capacità massima.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="dbbc5-123">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="dbbc5-123">To create a team</span></span>

1. <span data-ttu-id="dbbc5-124">Prima di tutto, fai clic su **Teams** sul lato sinistro dell'app, quindi fai clic su **Partecipa o** crea un team nella parte inferiore dell'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="dbbc5-125">Quindi fare clic **su Crea team** (prima scheda, angolo in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="dbbc5-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="dbbc5-126">Scegliere **Crea un team da zero.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="dbbc5-127">Scegliere quindi se si vuole un team pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="dbbc5-128">È **consigliabile usare Privato** per la coda di chiamata per evitare che le persone diventino involontariamente parte della coda partecipando al team.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="dbbc5-129">Assegnare un nome al team e aggiungere una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="dbbc5-130">Al termine, fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="dbbc5-131">Digitare i nomi delle persone che si desidera inserire nella coda di chiamata e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="dbbc5-132">Fare clic **su Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-132">Click **Close**.</span></span> <span data-ttu-id="dbbc5-133">Le persone che aggiungi a un team riceveranno un messaggio di posta elettronica che informa che sono ora membri del team e che il team verrà visualizzato nell'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="dbbc5-134">Verrà quindi aggiunto un canale da usare con la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="dbbc5-135">Per aggiungere un canale</span><span class="sxs-lookup"><span data-stu-id="dbbc5-135">To add a channel</span></span>

1. <span data-ttu-id="dbbc5-136">In Teams trovare il team appena creato, fare clic su **Altre opzioni** (...), quindi fare clic su **Aggiungi canale.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="dbbc5-137">Digitare un nome e una descrizione per il canale e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dbbc5-138">Passaggio 2 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="dbbc5-138">Step 2 - Resource accounts ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="dbbc5-139">Passaggio 2 <br> Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="dbbc5-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="dbbc5-140">Per ogni coda di chiamata creata è necessario un account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="dbbc5-141">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="dbbc5-142">In questo passaggio creeremo l'account, gli assegniamo una licenza *Microsoft 365 Phone System - Virtual User* e quindi lo useremo per iniziare a creare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="dbbc5-143">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="dbbc5-143">Create a resource account</span></span>

<span data-ttu-id="dbbc5-144">È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="dbbc5-145">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="dbbc5-146">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-146">Click **Add**.</span></span>

3. <span data-ttu-id="dbbc5-147">Nel riquadro **Aggiungi account risorsa** compilare **Nome** visualizzato , Nome **utente** e scegliere **Coda** di chiamata per il tipo di **account risorsa**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add-cq.png)

4. <span data-ttu-id="dbbc5-149">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-149">Click **Save**.</span></span>

<span data-ttu-id="dbbc5-150">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-150">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="dbbc5-152">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="dbbc5-152">Assign a license</span></span>

<span data-ttu-id="dbbc5-153">È necessario assegnare una licenza Sistema telefonico - Utente virtuale di *Microsoft 365* all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-153">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="dbbc5-154">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-154">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="dbbc5-155">Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-155">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="dbbc5-156">Fare clic **su Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-156">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente per l'assegnazione delle licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="dbbc5-158">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="dbbc5-158">Create a call queue</span></span>

<span data-ttu-id="dbbc5-159">A questo punto, inizieremo a creare una nuova coda di chiamata e assegnare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-159">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="dbbc5-160">Nell'interfaccia di amministrazione di Teams espandere **Voce,** fare clic su **Code di chiamata** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-160">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="dbbc5-161">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-161">Type a name for the call queue.</span></span> <span data-ttu-id="dbbc5-162">Gli agenti visualizzano questo nome quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-162">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="dbbc5-163">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="dbbc5-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="dbbc5-164">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-164">Choose a language.</span></span> <span data-ttu-id="dbbc5-165">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="dbbc5-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Screenshot delle impostazioni dell'account della risorsa e della lingua](../media/call-queue-name-language.png)

4. <span data-ttu-id="dbbc5-167">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="dbbc5-168">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="dbbc5-169">Teams fornisce musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="dbbc5-170">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc5-171">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-171">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="dbbc5-172">La musica predefinita fornita nelle code di chiamata di Teams è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="dbbc5-173">Passaggio 3 - Chiamare gli agenti ></span><span class="sxs-lookup"><span data-stu-id="dbbc5-173">Step 3 - Call agents ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="dbbc5-174">Passaggio 3 <br> Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="dbbc5-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="dbbc5-175">Per aggiungere agenti alla coda di chiamata, li aggiungeremo al team e al canale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="dbbc5-176">Selezionare **l'opzione Scegli un team** e fare clic **su Aggiungi canale.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="dbbc5-177">Digitare il nome del team creato, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="dbbc5-178">Selezionare il canale creato per la coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="dbbc5-179">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-179">Click **Apply**.</span></span>

    ![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="dbbc5-181">Quando vengono aggiunti nuovi utenti al team, l'arrivo della prima chiamata può richiedere fino a otto ore.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dbbc5-182">Passaggio 4 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="dbbc5-182">Step 4 - Resource accounts ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="dbbc5-183">Passaggio 4 <br> Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="dbbc5-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="dbbc5-184">Scegliere il metodo di routing delle chiamate da usare.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="dbbc5-185">Impostare **la modalità conferenza** su **Automatico**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="dbbc5-186">Scegliere il **metodo di** instradamento da usare.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="dbbc5-187">Questo determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="dbbc5-188">È consigliabile **instradamento seriale** **o Round robin.**</span><span class="sxs-lookup"><span data-stu-id="dbbc5-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="dbbc5-189">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbbc5-189">Choose from these options:</span></span>

    - <span data-ttu-id="dbbc5-190">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="dbbc5-191">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="dbbc5-192">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="dbbc5-193">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="dbbc5-194">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="dbbc5-195">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="dbbc5-196">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="dbbc5-197">Gli agenti il cui stato di presenza è Fuori rete per più di 10 minuti non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="dbbc5-199">Attivare **il routing basato sulla** presenza.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="dbbc5-200">In questo modo le chiamate vengono instradato agli agenti il cui stato di presenza è **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="dbbc5-201">Scegliere se consentire agli agenti di rifiutare esplicitamente le chiamate.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="dbbc5-202">Impostare un **tempo di avviso per** l'agente per specificare per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="dbbc5-204">Passaggio 5 - Overflow delle chiamate ></span><span class="sxs-lookup"><span data-stu-id="dbbc5-204">Step 5 - Call overflow ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="dbbc5-205">Passaggio 5 <br> Overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="dbbc5-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="dbbc5-206">Scegliere come gestire le chiamate che superano il massimo in coda.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="dbbc5-207">Impostare il **numero massimo di chiamate in coda**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="dbbc5-208">Scegliere l'operazione da eseguire quando viene raggiunto il numero massimo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="dbbc5-209">È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="dbbc5-210">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbbc5-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="dbbc5-211">**Persona dell'organizzazione,** una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="dbbc5-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="dbbc5-212">**App vocale:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="dbbc5-213">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="dbbc5-214">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="dbbc5-215">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="dbbc5-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="dbbc5-216">**Segreteria telefonica:** è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="dbbc5-218">Passaggio 6 - Timeout chiamata ></span><span class="sxs-lookup"><span data-stu-id="dbbc5-218">Step 6 - Call timeout ></span></span>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="dbbc5-219">Passaggio 6 <br> Timeout chiamata</span><span class="sxs-lookup"><span data-stu-id="dbbc5-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="dbbc5-220">Scegli cosa vuoi fare quando le chiamate sono in coda da troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="dbbc5-221">Impostare il **Timeout chiamata: tempo di attesa massimo**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-221">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="dbbc5-222">Scegliere l'operazione da eseguire quando si verifica il timeout di una chiamata. È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="dbbc5-223">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbbc5-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="dbbc5-224">**Persona dell'organizzazione,** una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="dbbc5-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="dbbc5-225">**App vocale:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="dbbc5-226">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="dbbc5-227">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="dbbc5-228">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="dbbc5-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="dbbc5-229">**Segreteria telefonica:** è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="dbbc5-231">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-231">Click **Save**.</span></span>

<span data-ttu-id="dbbc5-232">In questo modo viene completata la configurazione della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbbc5-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="dbbc5-233">È quindi possibile configurare [un operatore automatico.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="dbbc5-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

