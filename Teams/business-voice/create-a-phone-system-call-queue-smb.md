---
title: Creare una coda di chiamata in Microsoft Teams - Esercitazione su Small Business
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
description: Informazioni su come configurare le code di chiamata per le piccole imprese in Microsoft 365 Business Voice.
ms.openlocfilehash: e7141d32015207469346e018bc12bc362254ba2f
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126922"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="bf5ab-103">Creare una coda di chiamata - Esercitazione sulle piccole imprese</span><span class="sxs-lookup"><span data-stu-id="bf5ab-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="bf5ab-104">Le code di chiamata forniscono un metodo per instradare i chiamanti alle persone dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="bf5ab-105">Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti).*</span><span class="sxs-lookup"><span data-stu-id="bf5ab-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="bf5ab-106">Le code di chiamata forniscono:</span><span class="sxs-lookup"><span data-stu-id="bf5ab-106">Call queues provide:</span></span>

- <span data-ttu-id="bf5ab-107">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-107">A greeting message.</span></span>

- <span data-ttu-id="bf5ab-108">Musica mentre le persone sono in attesa di blocco in una coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="bf5ab-109">Instradamento delle chiamate, in ordine FIFO *(First In, First Out)* agli agenti.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="bf5ab-110">Opzioni di gestione per l'overflow e il timeout della coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="bf5ab-111">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="bf5ab-111">Video demonstration</span></span>

<span data-ttu-id="bf5ab-112">Questo video illustra come creare una coda di chiamata in Teams.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="bf5ab-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bf5ab-113">Before you begin</span></span>

<span data-ttu-id="bf5ab-114">Ottenere alcune [Sistema telefonico - Licenze utente virtuale](../teams-add-on-licensing/virtual-user.md) se non sono già disponibili.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="bf5ab-115">Ottenere una per ogni coda di chiamata e operatore automatico che si prevede di configurare.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="bf5ab-116">Queste licenze sono gratuite, quindi ti consigliamo di ottenere un po' di più se decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="bf5ab-117">Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="bf5ab-118">Per altre informazioni, vedere Gestire i [criteri id chiamante in Microsoft Teams](../caller-id-policies.md) chiamate.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="bf5ab-119">Seguire questa procedura per configurare la coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="bf5ab-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="bf5ab-120">Passaggio 1 <br> Creare un team</span><span class="sxs-lookup"><span data-stu-id="bf5ab-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="bf5ab-121">Quando si crea una coda di chiamata, è possibile aggiungere singoli utenti alla coda oppure usare un gruppo di sicurezza, un gruppo di Microsoft 365 o un team Microsoft Teams esistente.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="bf5ab-122">È [consigliabile usare un canale del team.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="bf5ab-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="bf5ab-123">In questo modo i membri della coda possono chattare tra loro, condividere idee e creare documenti o altre risorse per aiutare i clienti.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="bf5ab-124">Un team fornisce anche una cassetta postale vocale per consentire ai chiamanti di lasciare un messaggio dopo ore o se la coda raggiunge la capacità massima.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="bf5ab-125">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="bf5ab-125">To create a team</span></span>

1. <span data-ttu-id="bf5ab-126">Prima di tutto, **Teams** sul lato sinistro dell'app, quindi fare clic su Partecipa o crea un **team** nella parte inferiore dell'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="bf5ab-127">Quindi fare clic **su Crea team** (prima scheda, angolo in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="bf5ab-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="bf5ab-128">Scegliere **Crea un team da zero.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="bf5ab-129">Scegliere quindi se si vuole un team pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="bf5ab-130">È **consigliabile usare Privato** per la coda di chiamata per evitare che le persone diventino involontariamente parte della coda partecipando al team.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="bf5ab-131">Assegnare un nome al team e aggiungere una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="bf5ab-132">Al termine, fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="bf5ab-133">Digitare i nomi delle persone che si desidera inserire nella coda di chiamata e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="bf5ab-134">Fare clic **su Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-134">Click **Close**.</span></span> <span data-ttu-id="bf5ab-135">Le persone che aggiungi a un team riceveranno un messaggio di posta elettronica che informa che sono ora membri del team e che il team verrà visualizzato nell'elenco dei team.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="bf5ab-136">Verrà quindi aggiunto un canale da usare con la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="bf5ab-137">Per aggiungere un canale</span><span class="sxs-lookup"><span data-stu-id="bf5ab-137">To add a channel</span></span>

1. <span data-ttu-id="bf5ab-138">In Teams trovare il team appena creato, fare clic su **Altre** opzioni (...), quindi fare clic **su Aggiungi canale.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="bf5ab-139">Digitare un nome e una descrizione per il canale e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf5ab-140">Passaggio 2 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="bf5ab-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="bf5ab-141">Passaggio 2 <br> Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="bf5ab-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="bf5ab-142">Per ogni coda di chiamata creata è necessario un account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="bf5ab-143">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="bf5ab-144">In questo passaggio creeremo l'account, gli assegniamo una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale e quindi lo useremo per iniziare a creare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="bf5ab-145">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="bf5ab-145">Create a resource account</span></span>

<span data-ttu-id="bf5ab-146">È possibile creare un account della risorsa nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="bf5ab-147">Nell'Teams di amministrazione espandere **Impostazioni a** livello di organizzazione e quindi fare clic su **Account risorse.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="bf5ab-148">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-148">Click **Add**.</span></span>

3. <span data-ttu-id="bf5ab-149">Nel riquadro **Aggiungi account risorsa** compilare **Nome** visualizzato , Nome **utente** e scegliere **Coda** di chiamata per il tipo di **account risorsa**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="bf5ab-150">Gli agenti visualizzano il nome visualizzato quando ricevono una chiamata in arrivo dalla coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add-cq.png)

4. <span data-ttu-id="bf5ab-152">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-152">Click **Save**.</span></span>

   <span data-ttu-id="bf5ab-153">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-153">The new account will appear in the list of accounts.</span></span>

   ![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="bf5ab-155">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="bf5ab-155">Assign a license</span></span>

<span data-ttu-id="bf5ab-156">È necessario assegnare una *licenza Microsoft 365 Sistema telefonico - Utente* virtuale all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="bf5ab-157">Nell'interfaccia di amministrazione di Microsoft 365 utenti attivi **nell'elenco** Utenti attivi fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="bf5ab-158">Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="bf5ab-159">Fare clic **su Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-159">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente per l'assegnazione di licenze nel interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="bf5ab-161">Creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="bf5ab-161">Create a call queue</span></span>

<span data-ttu-id="bf5ab-162">A questo punto, inizieremo a creare una nuova coda di chiamata e assegnare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="bf5ab-163">Nell'Teams di amministrazione espandere **Voce,** fare clic su **Code di chiamata** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="bf5ab-164">Digitare un nome per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="bf5ab-165">Fare **clic su Aggiungi account,** cercare l'account della risorsa che si vuole usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** </span><span class="sxs-lookup"><span data-stu-id="bf5ab-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="bf5ab-166">(Facoltativo) In **Assegna ID chiamata** fare clic su **Aggiungi**, cercare gli account delle risorse creati per l'operatore automatico, fare clic su Aggiungi **e** quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="bf5ab-167">In questo modo gli agenti di chiamata riceveranno l'ID chiamante della linea principale al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![Screenshot delle impostazioni dell'ID chiamata](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="bf5ab-169">Scegliere una lingua.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-169">Choose a language.</span></span> <span data-ttu-id="bf5ab-170">Questa lingua verrà usata per le istruzioni vocali generate dal sistema e per la trascrizione della segreteria telefonica (se abilitate).</span><span class="sxs-lookup"><span data-stu-id="bf5ab-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Screenshot delle impostazioni dell'account delle risorse](../media/call-queue-name-language.png)

4. <span data-ttu-id="bf5ab-172">Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="bf5ab-173">È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="bf5ab-174">Teams musica predefinita ai chiamanti mentre sono in attesa in una coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="bf5ab-175">Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bf5ab-176">La registrazione caricata non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="bf5ab-177">La musica predefinita fornita nelle code Teams chiamate è gratuita di eventuali royalty pagate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf5ab-178">Passaggio 3 - Chiamare gli agenti ></span><span class="sxs-lookup"><span data-stu-id="bf5ab-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="bf5ab-179">Passaggio 3 <br> Agenti di chiamata</span><span class="sxs-lookup"><span data-stu-id="bf5ab-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="bf5ab-180">Per aggiungere agenti alla coda di chiamata, li aggiungeremo al team e al canale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span> <span data-ttu-id="bf5ab-181">Per eseguire questa operazione, è necessario essere membri del team.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-181">You need to be a member of the team to do this.</span></span>

1. <span data-ttu-id="bf5ab-182">Selezionare **l'opzione Scegli un team** e fare clic **su Aggiungi canale.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-182">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="bf5ab-183">Digitare il nome del team creato, selezionarlo e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-183">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="bf5ab-184">Selezionare il canale creato per la coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-184">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="bf5ab-185">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-185">Click **Apply**.</span></span>

    ![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="bf5ab-187">Quando vengono aggiunti nuovi utenti al team, l'arrivo della prima chiamata può richiedere fino a otto ore.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-187">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf5ab-188">Passaggio 4 - Account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="bf5ab-188">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="bf5ab-189">Passaggio 4 <br> Routing delle chiamate</span><span class="sxs-lookup"><span data-stu-id="bf5ab-189">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="bf5ab-190">Scegliere il metodo di routing delle chiamate da usare.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-190">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="bf5ab-191">Impostare **la modalità conferenza** su **Automatico**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-191">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="bf5ab-192">Scegliere il **metodo di** instradamento da usare.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-192">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="bf5ab-193">Questo determina l'ordine in cui gli agenti ricevono le chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-193">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="bf5ab-194">È consigliabile **instradamento seriale** **o Round robin.**</span><span class="sxs-lookup"><span data-stu-id="bf5ab-194">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="bf5ab-195">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf5ab-195">Choose from these options:</span></span>

    - <span data-ttu-id="bf5ab-196">**Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-196">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="bf5ab-197">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-197">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="bf5ab-198">**Il routing seriale** chiama tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-198">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="bf5ab-199">Se un agente licenzia o non riceve una chiamata, la chiamata squillerà all'agente successivo e proverà tutti gli agenti fino a quando non viene ritirata o non si verifica il timeout.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-199">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="bf5ab-200">**Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata oscinda lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-200">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="bf5ab-201">Questo può essere utile in un ambiente di vendita in ingresso per garantire la stessa opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-201">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="bf5ab-202">**L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-202">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="bf5ab-203">Gli agenti il cui stato di presenza è Fuori rete per più di 10 minuti non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-203">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Screenshot delle impostazioni della modalità conferenza e del metodo di routing](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="bf5ab-205">Attivare **il routing basato sulla** presenza.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-205">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="bf5ab-206">In questo modo le chiamate vengono instradato agli agenti il cui stato di presenza è **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-206">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="bf5ab-207">Scegliere se consentire agli agenti di rifiutare esplicitamente le chiamate.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-207">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="bf5ab-208">Impostare un **tempo di avviso per** l'agente per specificare per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-208">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Screenshot delle impostazioni relative a routing, rifiuto esplicito e tempo di avviso](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf5ab-210">Passaggio 5 - Overflow delle chiamate ></span><span class="sxs-lookup"><span data-stu-id="bf5ab-210">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="bf5ab-211">Passaggio 5 <br> Overflow delle chiamate</span><span class="sxs-lookup"><span data-stu-id="bf5ab-211">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="bf5ab-212">Scegliere come gestire le chiamate che superano il massimo in coda.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-212">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="bf5ab-213">Impostare il **numero massimo di chiamate in coda**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-213">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="bf5ab-214">Scegliere l'operazione da eseguire quando viene raggiunto il numero massimo di chiamate.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-214">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="bf5ab-215">È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-215">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="bf5ab-216">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf5ab-216">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="bf5ab-217">**Persona dell'organizzazione,** una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="bf5ab-217">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="bf5ab-218">**App vocale:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-218">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="bf5ab-219">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-219">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="bf5ab-220">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-220">**External phone number** - any phone number.</span></span> <span data-ttu-id="bf5ab-221">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="bf5ab-221">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="bf5ab-222">**Segreteria telefonica:** è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-222">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf5ab-224">Passaggio 6 - Timeout chiamata ></span><span class="sxs-lookup"><span data-stu-id="bf5ab-224">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="bf5ab-225">Passaggio 6 <br> Timeout chiamata</span><span class="sxs-lookup"><span data-stu-id="bf5ab-225">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="bf5ab-226">Scegli cosa vuoi fare quando le chiamate sono in coda da troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-226">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="bf5ab-227">Impostare il **tempo di attesa massimo**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-227">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="bf5ab-228">Scegliere l'operazione da eseguire quando si verifica il timeout di una chiamata. È possibile disconnettere la chiamata o reindirizzarla.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-228">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="bf5ab-229">È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf5ab-229">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="bf5ab-230">**Persona dell'organizzazione,** una persona dell'organizzazione che è in grado di ricevere chiamate vocali</span><span class="sxs-lookup"><span data-stu-id="bf5ab-230">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="bf5ab-231">**App vocale:** un operatore automatico o un'altra coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-231">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="bf5ab-232">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-232">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="bf5ab-233">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-233">**External phone number** - any phone number.</span></span> <span data-ttu-id="bf5ab-234">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="bf5ab-234">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="bf5ab-235">**Segreteria telefonica:** è possibile usare la cassetta postale vocale del team creato.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-235">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Screenshot delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="bf5ab-237">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-237">Click **Save**.</span></span>

<span data-ttu-id="bf5ab-238">In questo modo viene completata la configurazione della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf5ab-238">This completes the setup of your call queue.</span></span> <span data-ttu-id="bf5ab-239">È quindi possibile configurare [un operatore automatico.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="bf5ab-239">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

