#### <a name="before-you-begin"></a><span data-ttu-id="942bf-101">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="942bf-101">Before you begin</span></span>

<span data-ttu-id="942bf-102">Ottenere i numeri di servizio (i numeri di servizio sono un tipo speciale di numero di telefono usato dagli operatori automatici) necessari per gli operatori automatici a cui si vuole essere accessibili componendo direttamente dall'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="942bf-102">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="942bf-103">Questo può includere [il trasferimento di numeri da un altro provider o](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) la richiesta di nuovi numeri di [servizio.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="942bf-103">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="942bf-104">A ogni operatore automatico deve essere assegnata una licenza Sistema telefonico - Utente virtuale.</span><span class="sxs-lookup"><span data-stu-id="942bf-104">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="942bf-105">Quando hai acquistato Business Voice, hai ricevuto anche un certo numero di licenze Sistema telefonico - Utente virtuale, quindi probabilmente non devi richiedere altro.</span><span class="sxs-lookup"><span data-stu-id="942bf-105">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="942bf-106">Tuttavia, se ne servono di più in futuro, è possibile [ottenerli](../teams-add-on-licensing/virtual-user.md)seguendo le istruzioni in Sistema telefonico - Licenza utente virtuale .</span><span class="sxs-lookup"><span data-stu-id="942bf-106">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="942bf-107">Se si vuole che l'operatore automatico instradi le chiamate in modo diverso durante le festività, creare le festività da usare prima di creare l'operatore automatico. [](../set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="942bf-107">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="942bf-108">Seguire questa procedura per configurare l'operatore automatico</span><span class="sxs-lookup"><span data-stu-id="942bf-108">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="942bf-109">Passaggio 1 <br> Telefono numero</span><span class="sxs-lookup"><span data-stu-id="942bf-109">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="942bf-110">Se si sta seguendo la procedura per configurare VoIP aziendale per la prima volta e si è al passaggio **6:** Configurare un operatore automatico per il numero di telefono principale dell'azienda, i passaggi in questa scheda sono già stati completati. Passare alla scheda successiva: Informazioni generali [sull'operatore automatico.](?tabs=general-info#steps)</span><span class="sxs-lookup"><span data-stu-id="942bf-110">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="942bf-111">Ogni operatore automatico creato richiede un account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="942bf-111">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="942bf-112">È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona.</span><span class="sxs-lookup"><span data-stu-id="942bf-112">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="942bf-113">In questo passaggio creeremo l'account, gli assegniamo una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale e quindi assegniamo un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="942bf-113">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="942bf-114">Creare un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="942bf-114">Create a resource account</span></span>

<span data-ttu-id="942bf-115">È possibile creare un account della risorsa nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="942bf-115">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="942bf-116">Nell'Teams di amministrazione espandere **Impostazioni a** livello di organizzazione e quindi fare clic su **Account risorse.**</span><span class="sxs-lookup"><span data-stu-id="942bf-116">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="942bf-117">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="942bf-117">Click **Add**.</span></span>

3. <span data-ttu-id="942bf-118">Nel riquadro **Aggiungi account risorsa** compilare **Nome** visualizzato , Nome **utente** e scegliere **Operatore** automatico per il **tipo di account risorsa**</span><span class="sxs-lookup"><span data-stu-id="942bf-118">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

4. <span data-ttu-id="942bf-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="942bf-120">Click **Save**.</span></span>

    <span data-ttu-id="942bf-121">Il nuovo account verrà visualizzato nell'elenco degli account.</span><span class="sxs-lookup"><span data-stu-id="942bf-121">The new account will appear in the list of accounts.</span></span>

    ![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="942bf-123">Assegnare una licenza</span><span class="sxs-lookup"><span data-stu-id="942bf-123">Assign a license</span></span>

<span data-ttu-id="942bf-124">È necessario assegnare una *licenza Microsoft 365 Sistema telefonico - Utente* virtuale all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="942bf-124">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="942bf-125">Nell'Microsoft 365 di amministrazione fare clic sull'account della risorsa a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="942bf-125">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="942bf-126">Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.</span><span class="sxs-lookup"><span data-stu-id="942bf-126">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="942bf-127">Fare clic **su Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="942bf-127">Click **Save changes**.</span></span>

    ![Screenshot dell'interfaccia utente per l'assegnazione di licenze nell'interfaccia Microsoft 365 di amministrazione](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="942bf-129">Assegnare un numero di servizio</span><span class="sxs-lookup"><span data-stu-id="942bf-129">Assign a service number</span></span>

<span data-ttu-id="942bf-130">Se è necessario che questo operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="942bf-130">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="942bf-131">Nella pagina Account risorse dell'interfaccia  di amministrazione di Teams selezionare l'account della risorsa a cui si vuole assegnare un numero di servizio e quindi fare clic su **Assegna/annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="942bf-131">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="942bf-132">**Nell'Telefono tipo di** numero selezionare il tipo di numero da usare.</span><span class="sxs-lookup"><span data-stu-id="942bf-132">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="942bf-133">Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="942bf-133">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="942bf-135">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="942bf-135">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-136">Passaggio 2 - Informazioni generali sull'operatore automatico ></span><span class="sxs-lookup"><span data-stu-id="942bf-136">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="942bf-137">Passaggio 2 <br> Informazioni generali su Attendant</span><span class="sxs-lookup"><span data-stu-id="942bf-137">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="942bf-138">Per configurare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="942bf-138">To set up an auto attendant</span></span>

1. <span data-ttu-id="942bf-139">Nell'Teams di amministrazione espandere **Voce,** fare clic su **Operatori automatici** e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="942bf-139">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="942bf-140">Digitare un nome per l'operatore automatico nella casella in alto.</span><span class="sxs-lookup"><span data-stu-id="942bf-140">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="942bf-141">Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="942bf-141">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="942bf-142">Questa opzione è facoltativa (ma consigliata).</span><span class="sxs-lookup"><span data-stu-id="942bf-142">This is optional (but recommended).</span></span> <span data-ttu-id="942bf-143">È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="942bf-143">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="942bf-144">Specificare il fuso orario per questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="942bf-144">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="942bf-145">Il fuso orario viene usato per calcolare l'orario di ufficio se si crea un flusso di chiamata separato per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="942bf-145">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="942bf-146">Specificare una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="942bf-146">Specify a language for this auto attendant.</span></span> <span data-ttu-id="942bf-147">Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="942bf-147">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="942bf-148">Scegliere se abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="942bf-148">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="942bf-149">Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="942bf-149">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="942bf-150">Ad esempio, i chiamanti possono pronunciare "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure pronunciare "Vendite" per selezionare l'opzione di menu denominata "Vendite".</span><span class="sxs-lookup"><span data-stu-id="942bf-150">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Screenshot delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="942bf-152">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="942bf-152">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-153">Passaggio 3 - Flusso di chiamate ></span><span class="sxs-lookup"><span data-stu-id="942bf-153">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="942bf-154">Passaggio 3 <br> Flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="942bf-154">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="942bf-155">Scegliere le opzioni del flusso di chiamata</span><span class="sxs-lookup"><span data-stu-id="942bf-155">Choose your call flow options</span></span>

1. <span data-ttu-id="942bf-156">Scegliere se si vuole riprodurre un messaggio di saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-156">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="942bf-157">Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Upload **file per** caricare un messaggio di saluto registrato salvato come audio in . WAV, .MP3 o . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="942bf-157">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="942bf-158">La registrazione non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="942bf-158">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="942bf-159">Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-159">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Screenshot delle impostazioni dei messaggi di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="942bf-161">Scegli come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-161">Choose how you want to route the call.</span></span>

    <span data-ttu-id="942bf-162">Se si seleziona **Disconnetti**, l'operatore automatico riaggancia la chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-162">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="942bf-163">Se si seleziona **Reindirizza chiamata,** è possibile scegliere una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="942bf-163">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="942bf-164">Se si seleziona **Opzioni di menu** Riproduci , è possibile scegliere Riproduci un file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni di menu e la ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="942bf-164">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Screenshot delle impostazioni di routing delle chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="942bf-166">Se si vuole che i chiamanti usino i tasti di chiamata per spostarsi, in Imposta opzioni **di menu** scegliere cosa si vuole fare quando i chiamanti premono un tasto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-166">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="942bf-167">Se si sta creando questo operatore automatico come elenco aziendale, lasciare vuote le opzioni dei tasti di composizione.</span><span class="sxs-lookup"><span data-stu-id="942bf-167">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="942bf-168">È possibile impostare uno dei tasti di chiamata per le destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="942bf-168">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="942bf-169">**Persona dell'organizzazione:** una persona dell'organizzazione che è in grado di ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="942bf-169">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="942bf-170">**App vocale:** un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-170">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="942bf-171">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="942bf-171">**External phone number** - any phone number.</span></span> <span data-ttu-id="942bf-172">Usare questo formato: +[codice paese][codice area][numero di telefono]</span><span class="sxs-lookup"><span data-stu-id="942bf-172">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="942bf-173">**Segreteria telefonica:** la cassetta postale vocale associata a Microsoft 365 gruppo specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="942bf-173">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="942bf-174">**Operatore:** l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="942bf-174">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="942bf-175">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="942bf-175">Defining an operator is optional.</span></span> <span data-ttu-id="942bf-176">L'operatore può essere definito come qualsiasi altra destinazione in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="942bf-176">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="942bf-177">È consigliabile impostare il tasto 0 sull'operatore.</span><span class="sxs-lookup"><span data-stu-id="942bf-177">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="942bf-178">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="942bf-178">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="942bf-179">**Tasto di composizione:** il tasto sul tastierino del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="942bf-179">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="942bf-180">**Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="942bf-180">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="942bf-181">Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e motivi".</span><span class="sxs-lookup"><span data-stu-id="942bf-181">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="942bf-182">**Reindirizza** a- dove vuoi che la chiamata vada quando i chiamanti scelgono questa opzione.</span><span class="sxs-lookup"><span data-stu-id="942bf-182">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="942bf-183">Se si esegue il reindirizzamento a un operatore automatico o a una coda di chiamata, scegliere l'account della risorsa associato.</span><span class="sxs-lookup"><span data-stu-id="942bf-183">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Screenshot delle opzioni dei tasti di scelta](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="942bf-185">Se si vuole usare questo operatore automatico come directory aziendale, in **Ricerca directory** selezionare Chiama **per nome.**</span><span class="sxs-lookup"><span data-stu-id="942bf-185">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="942bf-186">Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="942bf-186">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="942bf-187">Qualsiasi utente online con una Sistema telefonico licenza è un utente idoneo e può essere trovato con Chiama per nome.</span><span class="sxs-lookup"><span data-stu-id="942bf-187">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="942bf-188">È possibile scegliere Chiama **per interno,** tuttavia l'interno deve essere configurato in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="942bf-188">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="942bf-189">Dopo aver selezionato **un'opzione di ricerca nella directory,** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="942bf-189">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-190">Passaggio 4 - Flusso di chiamate dopo l'></span><span class="sxs-lookup"><span data-stu-id="942bf-190">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="942bf-191">Passaggio 4 <br> Dopo ore</span><span class="sxs-lookup"><span data-stu-id="942bf-191">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="942bf-192">È possibile impostare l'orario di ufficio per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="942bf-192">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="942bf-193">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="942bf-193">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="942bf-194">L'orario di ufficio può essere impostato con interruzioni di orario durante il giorno e tutte le ore non impostate come ore lavorative vengono considerate dopo l'orario.</span><span class="sxs-lookup"><span data-stu-id="942bf-194">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="942bf-195">È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="942bf-195">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="942bf-196">A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo l'instradamento dopo l'orario di chiamata per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="942bf-196">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="942bf-197">Se si vuole un instradamento delle chiamate separato per i chiamanti non lavorativi, specificare l'orario di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="942bf-197">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="942bf-198">Fare **clic su Aggiungi nuova** ora per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="942bf-198">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Screenshot delle impostazioni del giorno e dell'ora dopo l'ora](../media/auto-attendant-business-hours.png)

<span data-ttu-id="942bf-200">Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="942bf-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="942bf-201">Sono disponibili le stesse opzioni per l'instradamento delle chiamate in orario di ufficio specificato nel **passaggio 3 - Flusso chiamate.**</span><span class="sxs-lookup"><span data-stu-id="942bf-201">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="942bf-202">Al **termine,** fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="942bf-202">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-203">Passaggio 5 - Flusso delle chiamate natalizie ></span><span class="sxs-lookup"><span data-stu-id="942bf-203">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="942bf-204">Passaggio 5 <br> Festività</span><span class="sxs-lookup"><span data-stu-id="942bf-204">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="942bf-205">Le chiamate all'operatore automatico possono essere instradati in modo diverso nei giorni festivi rispetto agli altri giorni.</span><span class="sxs-lookup"><span data-stu-id="942bf-205">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="942bf-206">Se non si vuole avere un flusso di chiamate diverso per le festività, è possibile saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="942bf-206">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="942bf-207">L'operatore automatico può avere un flusso di chiamate per ogni festività impostata.</span><span class="sxs-lookup"><span data-stu-id="942bf-207">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="942bf-208">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="942bf-208">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="942bf-209">Nella pagina Impostazioni chiamata per le festività fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="942bf-209">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="942bf-210">Digitare un nome per questa impostazione di festività.</span><span class="sxs-lookup"><span data-stu-id="942bf-210">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="942bf-211">**Nell'elenco a** discesa Festività scegliere la festività da usare.</span><span class="sxs-lookup"><span data-stu-id="942bf-211">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="942bf-212">Scegliere il tipo di messaggio di saluto da usare.</span><span class="sxs-lookup"><span data-stu-id="942bf-212">Choose the type of greeting that you want to use.</span></span>

    ![Screenshot delle impostazioni per le festività e le festività](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="942bf-214">Scegliere se disconnettere **o** **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-214">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="942bf-215">Se si sceglie di reindirizzare la chiamata, scegliere la destinazione del routing delle chiamate per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="942bf-215">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="942bf-217">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="942bf-217">Click **Save**.</span></span>

    <span data-ttu-id="942bf-218">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="942bf-218">Repeat the procedure as needed for each additional holiday.</span></span>

    ![Screenshot delle impostazioni delle festività con le festività elencate](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="942bf-220">Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="942bf-220">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-221">Passaggio 6 - Scegliere chi è nella directory ></span><span class="sxs-lookup"><span data-stu-id="942bf-221">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="942bf-222">Passaggio 6 <br> Membri della directory</span><span class="sxs-lookup"><span data-stu-id="942bf-222">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="942bf-223">*L'ambito di* chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa la chiamata per nome o la chiamata per interno.</span><span class="sxs-lookup"><span data-stu-id="942bf-223">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="942bf-224">L'impostazione predefinita **di Tutti gli** utenti online include tutti gli utenti dell'organizzazione che hanno una licenza Sistema telefonico online.</span><span class="sxs-lookup"><span data-stu-id="942bf-224">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="942bf-225">È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato in Includi o Escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. </span><span class="sxs-lookup"><span data-stu-id="942bf-225">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="942bf-226">Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di composizione.</span><span class="sxs-lookup"><span data-stu-id="942bf-226">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="942bf-227">Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.</span><span class="sxs-lookup"><span data-stu-id="942bf-227">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Screenshot delle opzioni di inclusione ed esclusione dell'ambito di chiamata](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="942bf-229">L'elenco del nome di un nuovo utente nella directory potrebbe richiedere fino a 36 ore.</span><span class="sxs-lookup"><span data-stu-id="942bf-229">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="942bf-230">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="942bf-230">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="942bf-231">Passaggio 7 - Assegnare un account ></span><span class="sxs-lookup"><span data-stu-id="942bf-231">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="942bf-232">Passaggio 7 <br> Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="942bf-232">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="942bf-233">A tutti gli operatori automatici deve essere associato un account di risorsa.</span><span class="sxs-lookup"><span data-stu-id="942bf-233">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="942bf-234">Gli operatori automatici di primo livello dovranno avere almeno un account della risorsa a cui è associato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="942bf-234">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="942bf-235">Se si vuole, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="942bf-235">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="942bf-236">Per aggiungere un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="942bf-236">To add a resource account</span></span>

1. <span data-ttu-id="942bf-237">Fare **clic** su Aggiungi e cercare l'account da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="942bf-237">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="942bf-238">Fare **clic su** Aggiungi e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="942bf-238">Click **Add**, and then click **Add**.</span></span>

    ![Screenshot del riquadro Aggiungi account dell'account della risorsa](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="942bf-240">Dopo aver aggiunto gli account del servizio, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="942bf-240">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Screenshot dell'elenco degli account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="942bf-242">La configurazione dell'operatore automatico viene completata.</span><span class="sxs-lookup"><span data-stu-id="942bf-242">This completes the auto attendant configuration.</span></span>

---