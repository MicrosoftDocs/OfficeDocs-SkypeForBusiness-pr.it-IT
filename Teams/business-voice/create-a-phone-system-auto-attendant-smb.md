---
title: Configurare un operatore automatico per Microsoft teams-Small Business tutorial
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
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909640"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="b6978-103">Configurare un operatore automatico-esercitazione sulle piccole imprese</span><span class="sxs-lookup"><span data-stu-id="b6978-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="b6978-104">Gli operatori automatici consentono alle persone di chiamare l'organizzazione e di spostarsi in un sistema di menu per parlare con il reparto di destra, la coda di chiamata, la persona o un operatore.</span><span class="sxs-lookup"><span data-stu-id="b6978-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="b6978-105">È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b6978-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="b6978-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b6978-106">Before you begin</span></span>

<span data-ttu-id="b6978-107">Ottenere i numeri di servizio necessari per gli operatori automatici a cui si vuole accedere tramite chiamata diretta dall'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6978-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="b6978-108">Questo potrebbe includere il [trasferimento di numeri da un altro provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la [richiesta di nuovi numeri di servizio](../getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="b6978-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="b6978-109">Ottenere un [sistema telefonico-licenza utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare.</span><span class="sxs-lookup"><span data-stu-id="b6978-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="b6978-110">Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche extra nel caso in cui decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="b6978-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="b6978-111">Per fare in modo che le chiamate di routing per l'operatore automatico vengano effettuate diversamente durante le festività, [creare le festività che si desidera utilizzare prima di](../set-up-holidays-in-teams.md) creare l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="b6978-112">Seguire questa procedura per configurare l'operatore automatico</span><span class="sxs-lookup"><span data-stu-id="b6978-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="b6978-113">Numero di <br> telefono passaggio 1</span><span class="sxs-lookup"><span data-stu-id="b6978-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="b6978-114">Ogni operatore automatico creato richiede un account di risorse.</span><span class="sxs-lookup"><span data-stu-id="b6978-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="b6978-115">Questo è simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="b6978-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="b6978-116">In questo passaggio verrà creato l'account, assegnato a *Microsoft 365 Phone System-licenza utente virtuale* e quindi assegnato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="b6978-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="b6978-117">Creare un account di risorse</span><span class="sxs-lookup"><span data-stu-id="b6978-117">Create a resource account</span></span>

<span data-ttu-id="b6978-118">È possibile creare un account risorse nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="b6978-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="b6978-119">Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.</span><span class="sxs-lookup"><span data-stu-id="b6978-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="b6978-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6978-120">Click **Add**.</span></span>

3. <span data-ttu-id="b6978-121">Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato**, **nomeutente** e scegliere **operatore automatico** per il **tipo di account risorse**</span><span class="sxs-lookup"><span data-stu-id="b6978-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Screenshot dell'interfaccia utente Aggiungi account risorse](../media/resource-account-add.png)

4. <span data-ttu-id="b6978-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6978-123">Click **Save**.</span></span>

<span data-ttu-id="b6978-124">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="b6978-124">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="b6978-126">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="b6978-126">Assign a license</span></span>

<span data-ttu-id="b6978-127">È necessario assegnare un *sistema telefonico Microsoft 365-licenza utente virtuale* per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b6978-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="b6978-128">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="b6978-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="b6978-129">Nella scheda **licenze e app** , in **licenze**, selezionare **Microsoft 365 Phone System-Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="b6978-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="b6978-130">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="b6978-130">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="b6978-132">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="b6978-132">Assign a service number</span></span>

<span data-ttu-id="b6978-133">Se è necessario che l'operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b6978-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="b6978-134">Nell'interfaccia di amministrazione di teams, nella pagina **account risorse** , selezionare l'account delle risorse a cui si vuole assegnare un numero di servizio e quindi fare clic su **assegna/Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="b6978-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="b6978-135">Nell'elenco a discesa **tipo di numero di telefono** scegliere il tipo di numero che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b6978-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="b6978-136">Nella casella **numero di telefono assegnato** cercare il numero che si vuole usare e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6978-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="b6978-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6978-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-139">Passaggio 2-informazioni generali sull'operatore automatico ></span><span class="sxs-lookup"><span data-stu-id="b6978-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="b6978-140">Informazioni generali su Step 2 <br> Attendant</span><span class="sxs-lookup"><span data-stu-id="b6978-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="b6978-141">Per configurare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="b6978-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="b6978-142">Nell'interfaccia di amministrazione di teams espandere **Voice**, fare clic su **operatore automatico** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6978-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="b6978-143">Digitare un nome per l'operatore automatico nella casella nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="b6978-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="b6978-144">Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="b6978-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="b6978-145">Questa opzione è facoltativa (ma consigliata).</span><span class="sxs-lookup"><span data-stu-id="b6978-145">This is optional (but recommended).</span></span> <span data-ttu-id="b6978-146">Puoi impostare l'opzione **operator** per consentire ai chiamanti di uscire dai menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="b6978-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="b6978-147">Specificare il fuso orario per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="b6978-148">Il fuso orario viene usato per calcolare le ore lavorative se si crea un flusso di chiamata separato per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="b6978-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="b6978-149">Specificare una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="b6978-150">Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b6978-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="b6978-151">Scegliere se si desidera abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="b6978-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="b6978-152">Quando è abilitata, il nome di ogni opzione del menu diventa una parola chiave per il riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="b6978-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="b6978-153">Ad esempio, i chiamanti possono pronunciare "uno" per selezionare l'opzione di menu mappata con il tasto 1 oppure possono dire "vendite" per selezionare l'opzione di menu denominata "Sales".</span><span class="sxs-lookup"><span data-stu-id="b6978-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Screenshot delle impostazioni di operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="b6978-155">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6978-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-156">Passaggio 3->flusso delle chiamate </span><span class="sxs-lookup"><span data-stu-id="b6978-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="b6978-157">Passaggio 3 <br> flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b6978-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="b6978-158">Scegliere le opzioni di flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b6978-158">Choose your call flow options</span></span>

1. <span data-ttu-id="b6978-159">Scegliere se si vuole riprodurre un saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="b6978-160">Se si seleziona **Riproduci un file audio** , è possibile usare il pulsante **Carica file** per caricare un messaggio di saluto registrato salvato come audio. WAV,. MP3 o. Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="b6978-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="b6978-161">La registrazione non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="b6978-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="b6978-162">Se si seleziona **digita un messaggio di saluto** , il sistema leggerà il testo del testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Screenshot delle impostazioni dei messaggi di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="b6978-164">Scegliere come si vuole instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="b6978-165">Se si seleziona **Disconnetti**, l'operatore automatico bloccherà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="b6978-166">Se si seleziona **reindirizza chiamata**, è possibile scegliere una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b6978-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="b6978-167">Se si seleziona **Opzioni di menu Riproduci**, è possibile scegliere di **riprodurre un file audio** o **digitare un messaggio di saluto** e quindi scegliere tra le opzioni del menu e la ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="b6978-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Screenshot delle impostazioni di routing delle chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="b6978-169">Se si vuole che i chiamanti usino i tasti di scelta rapida per spostarsi, quindi in **Opzioni del menu imposta** scegliere cosa si vuole che si verifichi quando i chiamanti premiano un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b6978-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="b6978-170">Se si sta creando questo operatore automatico come directory aziendale, uscire dalle opzioni del tasto di selezione vuoto.</span><span class="sxs-lookup"><span data-stu-id="b6978-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="b6978-171">È possibile impostare una qualsiasi delle chiavi di chiamata per le destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6978-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="b6978-172">**Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="b6978-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="b6978-173">**App vocale** : un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="b6978-174">**Numero di telefono esterno** -qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="b6978-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="b6978-175">Usare questo formato: + [codice paese] [prefisso] [numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="b6978-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="b6978-176">**Segreteria telefonica** : casella vocale associata a un gruppo Microsoft 365 specificato.</span><span class="sxs-lookup"><span data-stu-id="b6978-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="b6978-177">**Operator** : l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="b6978-178">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b6978-178">Defining an operator is optional.</span></span> <span data-ttu-id="b6978-179">L'operatore può essere definito come una qualsiasi delle altre destinazioni in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="b6978-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="b6978-180">Ti consigliamo di impostare il tasto 0 per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="b6978-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="b6978-181">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6978-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="b6978-182">**Tasto** di scelta rapida: il tasto sulla tastiera del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b6978-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="b6978-183">**Comando vocale** : definisce il comando vocale che può essere dato da un chiamante per accedere a questa opzione, se gli input vocali sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="b6978-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="b6978-184">Può contenere più parole come "Customer Service" o "Operations and grounds".</span><span class="sxs-lookup"><span data-stu-id="b6978-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="b6978-185">**Reindirizza a** -dove vuoi che la chiamata vada quando i chiamanti scelgono questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b6978-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="b6978-186">Se si reindirizza a un operatore automatico o a una coda di chiamata, scegliere l'account delle risorse associato.</span><span class="sxs-lookup"><span data-stu-id="b6978-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Screenshot delle opzioni dei tasti di scelta rapida](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="b6978-188">Se si vuole usare l'operatore automatico come directory aziendale, in **ricerca directory** selezionare **Componi per nome**.</span><span class="sxs-lookup"><span data-stu-id="b6978-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="b6978-189">Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="b6978-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="b6978-190">Qualsiasi utente online con una licenza di sistema telefonico è un utente idoneo e può essere trovato con chiamata per nome.</span><span class="sxs-lookup"><span data-stu-id="b6978-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="b6978-191">Puoi scegliere **dial by Extension**, ma l'estensione deve essere configurata in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b6978-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="b6978-192">Dopo aver selezionato un'opzione di **ricerca della directory** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6978-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-193">Passaggio 4-ore dopo il flusso delle chiamate ></span><span class="sxs-lookup"><span data-stu-id="b6978-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="b6978-194">Passaggio 4 <br> dopo le ore</span><span class="sxs-lookup"><span data-stu-id="b6978-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="b6978-195">Gli orari di ufficio possono essere impostati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="b6978-196">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="b6978-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="b6978-197">Gli orari di ufficio possono essere impostati con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orari di ufficio sono considerate after-hours.</span><span class="sxs-lookup"><span data-stu-id="b6978-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="b6978-198">È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e i messaggi di saluto per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="b6978-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="b6978-199">A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, è possibile che sia necessario specificare il routing delle chiamate after-hours per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="b6978-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="b6978-200">Se si vuole eseguire il routing delle chiamate separate per i chiamanti dopo le ore, specificare gli orari di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="b6978-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="b6978-201">Fare clic su **Aggiungi nuovo orario** per specificare più set di ore per un giorno specifico, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="b6978-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Screenshot delle impostazioni giorno e ora dopo ore](../media/auto-attendant-business-hours.png)

<span data-ttu-id="b6978-203">Dopo aver specificato gli orari di ufficio, scegliere le opzioni di routing delle chiamate per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="b6978-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="b6978-204">Le stesse opzioni sono disponibili per il routing delle chiamate in orario di ufficio specificato nel **passaggio 3-flusso delle chiamate**.</span><span class="sxs-lookup"><span data-stu-id="b6978-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="b6978-205">Al termine, fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="b6978-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-206">Passaggio 5-flusso delle chiamate festive ></span><span class="sxs-lookup"><span data-stu-id="b6978-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="b6978-207">Passaggio 5 <br> festività</span><span class="sxs-lookup"><span data-stu-id="b6978-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="b6978-208">È possibile che le chiamate all'operatore automatico vengano instradate in modo diverso durante le festività rispetto agli altri giorni.</span><span class="sxs-lookup"><span data-stu-id="b6978-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="b6978-209">Se non si vuole avere un flusso di chiamata diverso per le festività, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b6978-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="b6978-210">L'operatore automatico può avere un flusso di chiamata per ogni festività configurata.</span><span class="sxs-lookup"><span data-stu-id="b6978-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="b6978-211">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="b6978-212">Nella pagina delle impostazioni delle chiamate festive fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6978-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="b6978-213">Digitare un nome per l'impostazione festività.</span><span class="sxs-lookup"><span data-stu-id="b6978-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="b6978-214">Nell'elenco a discesa **festività** scegliere la festività che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b6978-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="b6978-215">Scegliere il tipo di saluto che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b6978-215">Choose the type of greeting that you want to use.</span></span>

    ![Schermata delle impostazioni di saluto delle festività e delle festività](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="b6978-217">Scegliere se si vuole **disconnettere** o **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="b6978-218">Se si è scelto di reindirizzare, scegliere la destinazione di routing delle chiamate per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Schermata delle impostazioni di azione delle chiamate per le festività](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="b6978-220">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6978-220">Click **Save**.</span></span>

<span data-ttu-id="b6978-221">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b6978-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Screenshot delle impostazioni per le festività con le festività elencate](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="b6978-223">Dopo aver aggiunto tutte le festività, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6978-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-224">Passaggio 6-scegliere gli utenti nella directory ></span><span class="sxs-lookup"><span data-stu-id="b6978-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="b6978-225">Passaggio 6 <br> membri della directory</span><span class="sxs-lookup"><span data-stu-id="b6978-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="b6978-226">L' *ambito di chiamata* definisce gli utenti disponibili nella directory quando un chiamante usa la chiamata per nome o il dial-by-Extension.</span><span class="sxs-lookup"><span data-stu-id="b6978-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="b6978-227">Il valore predefinito di **tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="b6978-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="b6978-228">È possibile includere o escludere utenti specifici selezionando un **gruppo di utenti personalizzato** in **Includi** o **Escludi** e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6978-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="b6978-229">Ad esempio, potresti voler escludere i dirigenti dell'organizzazione dalla directory di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6978-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="b6978-230">Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.</span><span class="sxs-lookup"><span data-stu-id="b6978-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Screenshot dell'ambito di chiamata include ed Escludi le opzioni](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="b6978-232">Per un nuovo utente potrebbe essere necessario un massimo di 36 ore per avere il nome elencato nella directory.</span><span class="sxs-lookup"><span data-stu-id="b6978-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="b6978-233">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6978-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6978-234">Passaggio 7-assegnare un account di risorse ></span><span class="sxs-lookup"><span data-stu-id="b6978-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="b6978-235"><br>Account delle risorse del passaggio 7</span><span class="sxs-lookup"><span data-stu-id="b6978-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="b6978-236">Tutti gli operatori automatici devono avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="b6978-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="b6978-237">Per gli operatori automatici di primo livello sarà necessario almeno un account delle risorse con un numero di servizio associato.</span><span class="sxs-lookup"><span data-stu-id="b6978-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="b6978-238">Se lo si desidera, è possibile assegnare più account di risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="b6978-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="b6978-239">Per aggiungere un account di risorse</span><span class="sxs-lookup"><span data-stu-id="b6978-239">To add a resource account</span></span>

1. <span data-ttu-id="b6978-240">Fare clic su **Aggiungi account** e cercare l'account che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b6978-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="b6978-241">Fare clic su **Aggiungi** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6978-241">Click **Add**, and then click **Add**.</span></span>

    ![Screenshot del pannello account risorse Aggiungi account](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="b6978-243">Dopo aver aggiunto gli account del servizio, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="b6978-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Screenshot dell'elenco di account risorse che mostra l'account delle risorse con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="b6978-245">Viene completata la configurazione dell'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b6978-245">This completes the auto attendant configuration.</span></span>

---


