---
title: Configurare un operatore automatico per Microsoft Teams - Esercitazione su Small Business
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
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per Microsoft 365 Business Voice.
ms.openlocfilehash: 7ee7dad833119778ceb64bd1e52bd30da4529ba8
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506653"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="9b7c0-103">Configurare un operatore automatico - Esercitazione sulle piccole imprese</span><span class="sxs-lookup"><span data-stu-id="9b7c0-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="9b7c0-104">Gli operatori automatici consentono alle persone di chiamare l'organizzazione e navigare in un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore giusto.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="9b7c0-105">È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="9b7c0-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9b7c0-106">Before you begin</span></span>

<span data-ttu-id="9b7c0-107">Ottenere i numeri di servizio necessari per gli operatori automatici a cui si vuole accedere tramite chiamata diretta dall'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="9b7c0-108">Questo può includere [il trasferimento di numeri da un altro provider o](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) la richiesta di nuovi numeri di [servizio.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="9b7c0-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="9b7c0-109">Ottenere una [licenza Sistema telefonico - Utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="9b7c0-110">Queste licenze sono gratuite, quindi ti consigliamo di ottenere un po' di più se decidi di apportare modifiche alla configurazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="9b7c0-111">Se si vuole che l'operatore automatico instradi le chiamate in modo diverso durante le festività, creare le festività da usare prima di creare l'operatore automatico. [](../set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9b7c0-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="9b7c0-112">Seguire questa procedura per configurare l'operatore automatico</span><span class="sxs-lookup"><span data-stu-id="9b7c0-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="9b7c0-113">Passaggio 1 <br> Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="9b7c0-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="9b7c0-114">Ogni operatore automatico creato richiede un account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="9b7c0-115">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="9b7c0-116">In questo passaggio verrà creato l'account, verrà assegnato un sistema telefonico *Microsoft 365 -* licenza utente virtuale e quindi verrà assegnato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="9b7c0-117">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="9b7c0-117">Create a resource account</span></span>

<span data-ttu-id="9b7c0-118">È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="9b7c0-119">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="9b7c0-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-120">Click **Add**.</span></span>

3. <span data-ttu-id="9b7c0-121">Nel riquadro **Aggiungi account risorsa** compilare **Nome** visualizzato , Nome **utente** e scegliere **Operatore** automatico per il **tipo di account risorsa**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

4. <span data-ttu-id="9b7c0-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-123">Click **Save**.</span></span>

<span data-ttu-id="9b7c0-124">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-124">The new account will appear in the list of accounts.</span></span>

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="9b7c0-126">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="9b7c0-126">Assign a license</span></span>

<span data-ttu-id="9b7c0-127">È necessario assegnare una licenza Sistema telefonico - Utente virtuale di *Microsoft 365* all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="9b7c0-128">Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="9b7c0-129">Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="9b7c0-130">Fare clic **su Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-130">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente per l'assegnazione delle licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="9b7c0-132">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="9b7c0-132">Assign a service number</span></span>

<span data-ttu-id="9b7c0-133">Se è necessario che questo operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="9b7c0-134">Nella pagina Account risorse  dell'interfaccia di amministrazione di Teams selezionare l'account della risorsa a cui si vuole assegnare un numero di servizio e quindi fare clic su **Assegna/annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="9b7c0-135">**Nell'elenco a discesa Tipo** di numero di telefono scegliere il tipo di numero da usare.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="9b7c0-136">Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="9b7c0-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-139">Passaggio 2 - Informazioni generali sull'operatore automatico ></span><span class="sxs-lookup"><span data-stu-id="9b7c0-139">Step 2 - Auto attendant general info ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="9b7c0-140">Passaggio 2 <br> Informazioni generali su Attendant</span><span class="sxs-lookup"><span data-stu-id="9b7c0-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="9b7c0-141">Per configurare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="9b7c0-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="9b7c0-142">Nell'interfaccia di amministrazione di Teams espandere **Voce,** fare clic su **Operatori automatici** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="9b7c0-143">Digitare un nome per l'operatore automatico nella casella in alto.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="9b7c0-144">Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="9b7c0-145">Questa opzione è facoltativa (ma consigliata).</span><span class="sxs-lookup"><span data-stu-id="9b7c0-145">This is optional (but recommended).</span></span> <span data-ttu-id="9b7c0-146">È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="9b7c0-147">Specificare il fuso orario per questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="9b7c0-148">Il fuso orario viene usato per calcolare l'orario di ufficio se si crea un flusso di chiamata separato per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="9b7c0-149">Specificare una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="9b7c0-150">Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="9b7c0-151">Scegliere se abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="9b7c0-152">Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="9b7c0-153">Ad esempio, i chiamanti possono pronunciare "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure pronunciare "Vendite" per selezionare l'opzione di menu denominata "Vendite".</span><span class="sxs-lookup"><span data-stu-id="9b7c0-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Screenshot delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="9b7c0-155">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-156">Passaggio 3 - Flusso di chiamate ></span><span class="sxs-lookup"><span data-stu-id="9b7c0-156">Step 3 - Call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="9b7c0-157">Passaggio 3 <br> Flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="9b7c0-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="9b7c0-158">Scegliere le opzioni del flusso di chiamata</span><span class="sxs-lookup"><span data-stu-id="9b7c0-158">Choose your call flow options</span></span>

1. <span data-ttu-id="9b7c0-159">Scegliere se si vuole riprodurre un messaggio di saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="9b7c0-160">Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Carica **file** per caricare un messaggio di saluto registrato salvato come audio in . WAV, . MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="9b7c0-161">La registrazione non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="9b7c0-162">Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Screenshot delle impostazioni dei messaggi di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="9b7c0-164">Scegli come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="9b7c0-165">Se si seleziona **Disconnetti**, l'operatore automatico riaggancia la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="9b7c0-166">Se si seleziona **Reindirizza chiamata,** è possibile scegliere una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="9b7c0-167">Se si seleziona **Opzioni di menu** Riproduci , è possibile scegliere Riproduci un file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni di menu e la ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Screenshot delle impostazioni di routing delle chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="9b7c0-169">Se si vuole che i chiamanti usino i tasti di chiamata per spostarsi, in Imposta opzioni **di menu** scegliere cosa si vuole fare quando i chiamanti premono un tasto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="9b7c0-170">Se si sta creando questo operatore automatico come elenco aziendale, lasciare vuote le opzioni dei tasti di composizione.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="9b7c0-171">È possibile impostare uno dei tasti di chiamata per le destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b7c0-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="9b7c0-172">**Persona dell'organizzazione:** una persona dell'organizzazione che è in grado di ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="9b7c0-173">**App vocale:** un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="9b7c0-174">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="9b7c0-175">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="9b7c0-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="9b7c0-176">**Segreteria telefonica:** la cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="9b7c0-177">**Operatore:** l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="9b7c0-178">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-178">Defining an operator is optional.</span></span> <span data-ttu-id="9b7c0-179">L'operatore può essere definito come qualsiasi altra destinazione in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="9b7c0-180">È consigliabile impostare il tasto 0 sull'operatore.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="9b7c0-181">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9b7c0-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="9b7c0-182">**Tasto di composizione:** il tasto sul tastierino del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="9b7c0-183">**Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="9b7c0-184">Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e motivi".</span><span class="sxs-lookup"><span data-stu-id="9b7c0-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="9b7c0-185">**Reindirizza** a- dove vuoi che la chiamata vada quando i chiamanti scelgono questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="9b7c0-186">Se si esegue il reindirizzamento a un operatore automatico o a una coda di chiamata, scegliere l'account della risorsa associato.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Screenshot delle opzioni dei tasti di scelta](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="9b7c0-188">Se si vuole usare questo operatore automatico come directory aziendale, in **Ricerca directory** selezionare Chiama **per nome.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="9b7c0-189">Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="9b7c0-190">Qualsiasi utente online con licenza Sistema telefonico è un utente idoneo e può essere trovato con Chiama per nome.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="9b7c0-191">È possibile scegliere Chiama **per interno,** tuttavia l'estensione deve essere configurata in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="9b7c0-192">Dopo aver selezionato **un'opzione di ricerca nella directory,** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-193">Passaggio 4 - Flusso di chiamate dopo l'></span><span class="sxs-lookup"><span data-stu-id="9b7c0-193">Step 4 - After hours call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="9b7c0-194">Passaggio 4 <br> Dopo ore</span><span class="sxs-lookup"><span data-stu-id="9b7c0-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="9b7c0-195">È possibile impostare l'orario di ufficio per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="9b7c0-196">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="9b7c0-197">L'orario di ufficio può essere impostato con interruzioni di orario durante il giorno e tutte le ore non impostate come ore lavorative vengono considerate dopo l'orario.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="9b7c0-198">È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="9b7c0-199">A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo l'instradamento dopo l'orario di chiamata per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="9b7c0-200">Se si vuole un instradamento delle chiamate separato per i chiamanti non lavorativi, specificare l'orario di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="9b7c0-201">Fare **clic su Aggiungi nuova** ora per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Screenshot delle impostazioni del giorno e dell'ora dopo l'ora](../media/auto-attendant-business-hours.png)

<span data-ttu-id="9b7c0-203">Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="9b7c0-204">Sono disponibili le stesse opzioni per l'instradamento delle chiamate in orario di ufficio specificato nel **passaggio 3 - Flusso chiamate.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="9b7c0-205">Al **termine,** fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-206">Passaggio 5 - Flusso delle chiamate natalizie ></span><span class="sxs-lookup"><span data-stu-id="9b7c0-206">Step 5 - Holiday call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="9b7c0-207">Passaggio 5 <br> Festività</span><span class="sxs-lookup"><span data-stu-id="9b7c0-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="9b7c0-208">Le chiamate all'operatore automatico possono essere instradati in modo diverso nei giorni festivi rispetto agli altri giorni.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="9b7c0-209">Se non si vuole avere un flusso di chiamate diverso per le festività, è possibile saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="9b7c0-210">L'operatore automatico può avere un flusso di chiamate per ogni festività impostata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="9b7c0-211">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="9b7c0-212">Nella pagina Impostazioni chiamata per le festività fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="9b7c0-213">Digitare un nome per questa impostazione di festività.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="9b7c0-214">**Nell'elenco a** discesa Festività scegliere la festività da usare.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="9b7c0-215">Scegliere il tipo di messaggio di saluto da usare.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-215">Choose the type of greeting that you want to use.</span></span>

    ![Screenshot delle impostazioni per le festività e le festività](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="9b7c0-217">Scegliere se disconnettere **o** **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="9b7c0-218">Se si sceglie di reindirizzare la chiamata, scegliere la destinazione del routing delle chiamate per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="9b7c0-220">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-220">Click **Save**.</span></span>

<span data-ttu-id="9b7c0-221">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Screenshot delle impostazioni delle festività con le festività elencate](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="9b7c0-223">Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-224">Passaggio 6 - Scegliere chi è nella directory ></span><span class="sxs-lookup"><span data-stu-id="9b7c0-224">Step 6 - Choose who's in the directory ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="9b7c0-225">Passaggio 6 <br> Membri della directory</span><span class="sxs-lookup"><span data-stu-id="9b7c0-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="9b7c0-226">*L'ambito di* chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa la chiamata per nome o la chiamata per interno.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="9b7c0-227">L'impostazione predefinita **di Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con una licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="9b7c0-228">È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato **in** Includi o Escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="9b7c0-229">Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di composizione.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="9b7c0-230">Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Screenshot delle opzioni di inclusione ed esclusione dell'ambito di chiamata](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="9b7c0-232">L'elenco del nome di un nuovo utente nella directory potrebbe richiedere fino a 36 ore.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="9b7c0-233">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9b7c0-234">Passaggio 7 - Assegnare un account ></span><span class="sxs-lookup"><span data-stu-id="9b7c0-234">Step 7 - Assign a resource account ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="9b7c0-235">Passaggio 7 <br> Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="9b7c0-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="9b7c0-236">A tutti gli operatori automatici deve essere associato un account di risorsa.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="9b7c0-237">Gli operatori automatici di primo livello dovranno avere almeno un account della risorsa a cui è associato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="9b7c0-238">Se si vuole, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="9b7c0-239">Per aggiungere un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="9b7c0-239">To add a resource account</span></span>

1. <span data-ttu-id="9b7c0-240">Fare **clic su Aggiungi account** e cercare l'account da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="9b7c0-241">Fare **clic su** Aggiungi e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-241">Click **Add**, and then click **Add**.</span></span>

    ![Screenshot del riquadro Aggiungi account dell'account della risorsa](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="9b7c0-243">Dopo aver aggiunto gli account del servizio, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="9b7c0-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Screenshot dell'elenco degli account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="9b7c0-245">La configurazione dell'operatore automatico viene completata.</span><span class="sxs-lookup"><span data-stu-id="9b7c0-245">This completes the auto attendant configuration.</span></span>

---


