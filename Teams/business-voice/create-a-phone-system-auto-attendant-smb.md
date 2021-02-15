---
title: Configurare un operatore automatico per Microsoft Teams - esercitazione per piccole aziende
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
description: Scopri come configurare e testare gli operatori automatici per Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909640"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="e5f8a-103">Configurare un operatore automatico - esercitazione per piccole aziende</span><span class="sxs-lookup"><span data-stu-id="e5f8a-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="e5f8a-104">Gli operatori automatici consentono alle persone di chiamare l'organizzazione ed esplorare un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="e5f8a-105">È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="e5f8a-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e5f8a-106">Before you begin</span></span>

<span data-ttu-id="e5f8a-107">Ottenere i numeri di servizio necessari per gli operatori automatici che si desidera siano accessibili componendo direttamente dall'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="e5f8a-108">Può includere il [trasferimento di numeri da un altro provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la richiesta di nuovi numeri di [servizio.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="e5f8a-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="e5f8a-109">Ottenere un [Sistema telefonico - Licenza Utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="e5f8a-110">Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore prodotto se decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="e5f8a-111">Se si vuole impostare il percorso dell'operatore [](../set-up-holidays-in-teams.md) automatico in modo diverso durante le festività, creare le festività da usare prima di creare l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="e5f8a-112">Seguire questa procedura per configurare l'operatore automatico</span><span class="sxs-lookup"><span data-stu-id="e5f8a-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="e5f8a-113">Passaggio 1 <br> Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="e5f8a-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="e5f8a-114">Ogni operatore automatico che crei richiede un account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="e5f8a-115">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="e5f8a-116">In questo passaggio creeremo l'account, gli assegniamo una licenza Sistema telefonico - Utente virtuale di *Microsoft 365* e quindi assegniamo un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="e5f8a-117">Creare un account delle risorse</span><span class="sxs-lookup"><span data-stu-id="e5f8a-117">Create a resource account</span></span>

<span data-ttu-id="e5f8a-118">È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="e5f8a-119">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="e5f8a-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-120">Click **Add**.</span></span>

3. <span data-ttu-id="e5f8a-121">Nel riquadro **Aggiungi account risorsa,** compilare **Nome visualizzato**, **Nome** utente e scegliere **Operatore** automatico per il **tipo di account Risorsa**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Screenshot dell'interfaccia utente aggiungi account risorsa](../media/resource-account-add.png)

4. <span data-ttu-id="e5f8a-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-123">Click **Save**.</span></span>

<span data-ttu-id="e5f8a-124">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-124">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="e5f8a-126">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="e5f8a-126">Assign a license</span></span>

<span data-ttu-id="e5f8a-127">È necessario assegnare una *licenza Sistema telefonico Microsoft 365 -* Utente virtuale all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="e5f8a-128">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="e5f8a-129">Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="e5f8a-130">Fare clic **su Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-130">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="e5f8a-132">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="e5f8a-132">Assign a service number</span></span>

<span data-ttu-id="e5f8a-133">Se è necessario che questo operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="e5f8a-134">Nell'interfaccia di amministrazione  di Teams, nella pagina Account risorse, selezionare l'account della risorsa a cui assegnare un numero di servizio e quindi fare clic su **Assegna/Annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="e5f8a-135">**Nell'elenco a** discesa Tipo di numero di telefono scegliere il tipo di numero da usare.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="e5f8a-136">Nella casella **Numero di telefono assegnato,** cerca il numero che desideri utilizzare e fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Screenshot dell'interfaccia utente Assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="e5f8a-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-139">Fase 2 - Informazioni generali sull'operatore ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="e5f8a-140">Informazioni generali su Step 2 <br> Attendant</span><span class="sxs-lookup"><span data-stu-id="e5f8a-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="e5f8a-141">Per impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="e5f8a-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="e5f8a-142">Nell'interfaccia di amministrazione di Teams espandi **Voce,** fai clic **su Operatori** automatici, quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="e5f8a-143">Digita un nome per l'operatore automatico nella casella in alto.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="e5f8a-144">Se si vuole designare un operatore, specificare la destinazione delle chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="e5f8a-145">Questo passaggio è facoltativo (ma consigliato).</span><span class="sxs-lookup"><span data-stu-id="e5f8a-145">This is optional (but recommended).</span></span> <span data-ttu-id="e5f8a-146">È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="e5f8a-147">Specifica il fuso orario per questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="e5f8a-148">Il fuso orario viene utilizzato per calcolare l'orario di ufficio se si crea un flusso delle chiamate separato per l'orario di uscita.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="e5f8a-149">Specifica una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="e5f8a-150">Questa è la lingua che verrà usata per i comandi vocali generati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="e5f8a-151">Scegli se abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="e5f8a-152">Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="e5f8a-153">Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1, oppure possono dire "Vendite" per selezionare l'opzione di menu denominata "Vendite".</span><span class="sxs-lookup"><span data-stu-id="e5f8a-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Schermata delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="e5f8a-155">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-156">Passaggio 3 - Flusso delle chiamate ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="e5f8a-157">Passaggio 3 <br> Flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e5f8a-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="e5f8a-158">Scegliere le opzioni del flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e5f8a-158">Choose your call flow options</span></span>

1. <span data-ttu-id="e5f8a-159">Scegli se vuoi riprodurre un saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="e5f8a-160">Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Carica **file** per caricare un messaggio di saluto registrato salvato come audio in. WAV, . MP3, o . WMA.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="e5f8a-161">Le dimensioni della registrazione non possono essere superiori a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="e5f8a-162">Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Screenshot delle impostazioni del messaggio di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="e5f8a-164">Scegli come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="e5f8a-165">Se si seleziona **Disconnetti,** l'operatore automatico ggancia la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="e5f8a-166">Se si seleziona **Reindirizza** chiamata, è possibile scegliere una delle destinazioni di instradamento chiamate.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="e5f8a-167">Se si **selezionaNo le opzioni** del menu Riproduci, è possibile scegliere Riproduci file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni del menu e la ricerca in elenco.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Schermata delle impostazioni di instradamento chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="e5f8a-169">Se si vuole che i chiamanti usino i tasti di composizione per navigare, in Imposta opzioni di **menu** scegli cosa vuoi fare quando i chiamanti premono un tasto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="e5f8a-170">Se stai creando questo operatore automatico come elenco aziendale, lascia vuote le opzioni dei tasti di composizione.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="e5f8a-171">Puoi impostare uno qualsiasi dei tasti di composizione per le destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5f8a-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="e5f8a-172">**Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="e5f8a-173">**App voce:** un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="e5f8a-174">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="e5f8a-175">Usa questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="e5f8a-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="e5f8a-176">**Segreteria telefonica:** cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="e5f8a-177">**Operatore:** l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="e5f8a-178">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-178">Defining an operator is optional.</span></span> <span data-ttu-id="e5f8a-179">L'operatore può essere definito come una qualsiasi delle altre destinazioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="e5f8a-180">È consigliabile impostare il tasto 0 sull'operatore.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="e5f8a-181">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e5f8a-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="e5f8a-182">**Tasto di composizione:** il tasto sulla tastiera del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="e5f8a-183">**Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se sono abilitati gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="e5f8a-184">Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e basi".</span><span class="sxs-lookup"><span data-stu-id="e5f8a-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="e5f8a-185">**Redirect to** - where you want the call to go when callers choose this option.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="e5f8a-186">Se stai effettuando il reindirizzamento a un operatore automatico o a una coda di chiamata, scegli l'account delle risorse associato.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Schermata delle opzioni dei tasti di composizione](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="e5f8a-188">Se desideri utilizzare questo operatore automatico come elenco aziendale, seleziona Chiamata per nome in **Ricerca** **elenco.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="e5f8a-189">Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="e5f8a-190">Qualsiasi utente online con licenza Sistema telefonico è un utente idoneo e può essere trovato con Chiamata per nome.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="e5f8a-191">È possibile scegliere Chiamata **per interno,** tuttavia l'interno deve essere configurato in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="e5f8a-192">Dopo aver selezionato un'opzione **di ricerca nella directory,** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-193">Fase 4 - Flusso delle chiamate non in ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="e5f8a-194">Passaggio 4 <br> Ore successive</span><span class="sxs-lookup"><span data-stu-id="e5f8a-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="e5f8a-195">L'orario di ufficio può essere impostato per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="e5f8a-196">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="e5f8a-197">L'orario di ufficio può essere impostato con interruzioni durante il giorno e tutti gli orari non impostati come orario di ufficio sono considerati fuori orario.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="e5f8a-198">Puoi impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per il dopo orario.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="e5f8a-199">A seconda di come hai configurato gli operatori automatici e le code di chiamata, potresti dover specificare l'instradamento delle chiamate in orario di instradamento solo per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="e5f8a-200">Se si desidera un instradamento delle chiamate separato per i chiamanti non in orario di ufficio, specificare l'orario di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="e5f8a-201">Fare **clic su Aggiungi nuovo orario** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Screenshot delle impostazioni del giorno e dell'ora fuori orario](../media/auto-attendant-business-hours.png)

<span data-ttu-id="e5f8a-203">Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="e5f8a-204">Le stesse opzioni sono disponibili per l'instradamento delle chiamate in orario di ufficio specificato nel **Passaggio 3 - Flusso delle chiamate.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="e5f8a-205">Al **termine,** fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-206">Passaggio 5 - Flusso delle chiamate per le ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="e5f8a-207">Passaggio 5 <br> Festività</span><span class="sxs-lookup"><span data-stu-id="e5f8a-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="e5f8a-208">Le chiamate all'operatore automatico possono essere instradati in modo diverso durante le festività rispetto agli altri giorni.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="e5f8a-209">Se non si vuole avere un flusso delle chiamate diverso per le festività, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="e5f8a-210">L'operatore automatico può avere un flusso delle chiamate per ogni festività impostata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="e5f8a-211">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="e5f8a-212">Nella pagina delle impostazioni delle chiamate per le festività fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="e5f8a-213">Digitare un nome per l'impostazione delle festività.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="e5f8a-214">**Nell'elenco** a discesa Festività scegliere la festività da usare.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="e5f8a-215">Scegliere il tipo di messaggio di saluto da usare.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-215">Choose the type of greeting that you want to use.</span></span>

    ![Screenshot delle impostazioni per le festività e le festività](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="e5f8a-217">Scegli se vuoi disconnettere **o** **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="e5f8a-218">Se hai scelto di reindirizzare la chiamata, scegli la destinazione del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="e5f8a-220">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-220">Click **Save**.</span></span>

<span data-ttu-id="e5f8a-221">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Screenshot delle impostazioni delle festività con l'elenco delle festività](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="e5f8a-223">Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-224">Passaggio 6 - Scegliere chi è nella directory ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="e5f8a-225">Passaggio 6 <br> Membri della directory</span><span class="sxs-lookup"><span data-stu-id="e5f8a-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="e5f8a-226">*L'ambito* di chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa chiamata per nome o per interno.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="e5f8a-227">L'impostazione predefinita **Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="e5f8a-228">È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato in Includi o escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. </span><span class="sxs-lookup"><span data-stu-id="e5f8a-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="e5f8a-229">Ad esempio, è possibile escludere i dirigenti dell'organizzazione dalla directory di composizione.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="e5f8a-230">Se un utente è in entrambi gli elenchi, verrà escluso dalla directory.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Schermata delle opzioni di inclusione ed esclusione dell'ambito di chiamata](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="e5f8a-232">L'elenco dei nomi di un nuovo utente nella directory può richiedere fino a 36 ore.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="e5f8a-233">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5f8a-234">Passaggio 7 - Assegnare un account delle risorse ></span><span class="sxs-lookup"><span data-stu-id="e5f8a-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="e5f8a-235">Passaggio 7 <br> Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="e5f8a-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="e5f8a-236">Tutti gli operatori automatici devono avere un account delle risorse associato.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="e5f8a-237">Gli operatori automatici di primo livello dovranno avere almeno un account delle risorse a cui è associato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="e5f8a-238">Se si desidera, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="e5f8a-239">Per aggiungere un account di risorsa</span><span class="sxs-lookup"><span data-stu-id="e5f8a-239">To add a resource account</span></span>

1. <span data-ttu-id="e5f8a-240">Fare **clic su** Aggiungi account e cercare l'account che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="e5f8a-241">Fare **clic su** Aggiungi e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-241">Click **Add**, and then click **Add**.</span></span>

    ![Screenshot del riquadro Aggiungi account dell'account della risorsa](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="e5f8a-243">Dopo aver aggiunto gli account del servizio, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="e5f8a-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Screenshot dell'elenco di account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="e5f8a-245">La configurazione dell'operatore automatico è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e5f8a-245">This completes the auto attendant configuration.</span></span>

---


