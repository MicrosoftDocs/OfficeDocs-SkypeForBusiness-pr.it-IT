---
title: Progettazione e creazione di flussi di lavoro di Response Group in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Progettare e creare flussi di lavoro di Response Group in Skype for Business Server VoIP aziendale. Vengono trattati sia i flussi di lavoro dei gruppi di risposta che i flussi di lavoro interattivi.
ms.openlocfilehash: ec92a0dfa378746db98a6377b2ebd51df0e77813
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864383"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Progettazione e creazione di flussi di lavoro di Response Group in Skype for Business

Progettare e creare flussi di lavoro di Response Group in Skype for Business Server VoIP aziendale. Vengono trattati sia i flussi di lavoro dei gruppi di risposta che i flussi di lavoro interattivi.

Un flusso di lavoro definisce il comportamento di una chiamata dal momento in cui il telefono squilla al momento in cui un qualcuno risponde. Il flusso di lavoro specifica la coda da utilizzare per la chiamata e specifica il metodo di routing da utilizzare per i flussi di lavoro dei gruppi di risposta o le domande e le risposte da utilizzare per i flussi di lavoro di Response Group interattivi.

Un flusso di lavoro inoltre definisce impostazioni quali il messaggio di benvenuto, la musica di attesa, l'orario di ufficio e le festività.

> [!NOTE]
> È necessario creare i gruppi di agenti e le code prima di creare il flusso di lavoro che li utilizza.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Creazione o modifica di un flusso di lavoro di un gruppo di risposta

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Per utilizzare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro di un gruppo di risposta

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.

4. Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.

5. Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera creare o modificare. Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.

    > [!NOTE]
    > Verrà aperto lo Strumento di configurazione di Response Group. È inoltre possibile aprire lo Strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL seguente: https:// \<webPoolFqdn\> /RgsConfig.

6. Eseguire una delle operazioni seguenti:

   - In **Crea un nuovo flusso di lavoro** fare clic su **Crea** accanto a **Gruppo di risposta**.

   - In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro che si desidera modificare e quindi fare clic su **Modifica** in **Azione**.

7. Se gli utenti possono iniziare a chiamare il flusso di lavoro immediatamente, selezionare **Attiva il flusso di lavoro**.

    > [!NOTE]
    >  Se si sta creando un flusso di lavoro gestito, è necessario selezionare **Attiva il flusso di lavoro**. Dopo aver salvato il flusso di lavoro gestito attivo, è possibile modificarlo e disattivarlo.

8. Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per federazione**. È inoltre necessario disporre di un criterio di accesso esterno che si applica all'applicazione Response Group configurata per la federazione.

    > [!NOTE]
    > Il criterio di accesso esterno globale si applica all'applicazione Response Group. È possibile configurare il criterio globale per la federazione di Response Group utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet **Set-CsExternalAccessPolicy** per impostare il parametro EnableOutsideAccess su True. Considerare che le impostazioni di criteri globali vengono applicate a tutti gli utenti, a meno che non dispongano di un criterio sito o utente assegnato. Prima di modificare questa impostazione per i Response Group, verificare quindi che le impostazioni della federazione soddisfino i requisiti dell'organizzazione. Per informazioni dettagliate sull'applicazione dei criteri agli utenti, vedere [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Per informazioni dettagliate sull'impostazione di federazione, [vedere Set-CsExternalAccessPolicy.](/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)

    > [!NOTE]
    > Gli utenti ospitati in Skype for Business Online non possono effettuare chiamate a Response Group ospitati in una distribuzione locale. Ciò vale sia nelle distribuzioni ibride che nei casi in cui una distribuzione locale è federata con una distribuzione Skype for Business online.

9. Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita anonimato agente**.

    > [!NOTE]
    > Le chiamate anonime non possono iniziare con un messaggio istantaneo o un video, sebbene l'agente o il chiamante possa aggiungere messaggi istantanei e video dopo l'attivazione della chiamata. Un agente anonimo può inoltre mettere le chiamate in attesa, eseguire trasferimenti di chiamata, nascosti o con consultazione del destinatario, nonché parcheggiare e recuperare le chiamate. Per le chiamate anonime non sono supportate conferenze, condivisione di applicazioni, condivisione del desktop, trasferimenti di file, collaborazione con lavagna e sui dati e registrazione delle chiamate. Gli agenti che utilizzano il plug-in VDI di Lync possono ricevere chiamate in ingresso in modo anonimo, ma non possono effettuare chiamate in uscita in modo anonimo.

10. In **Immettere l'indirizzo del gruppo che riceverà le chiamate** digitare l'indirizzo URI (Uniform Resource Identifier) SIP primario del gruppo che dovrà rispondere alle chiamate al flusso di lavoro.

    > [!NOTE]
    > L'URI primario di un flusso di lavoro viene utilizzato come identificazione e riferimento per un flusso di lavoro. L'URI SIP immesso viene creato come oggetto contatto in Servizi di dominio Active Directory. Per creare l'URI, l'oggetto deve essere univoco in Active Directory.

11. In **Nome visualizzato** digitare il nome che si desidera visualizzare per il flusso di lavoro, ad esempio Sales Response Group.

    > [!NOTE]
    > Non includere i caratteri "<" o ">" nel nome visualizzato. Non utilizzare i nomi visualizzati seguenti, perché sono riservati: **RGS Presence Watcher** o **Servizio Annuncio**.

12. In **Numero di telefono** digitare l'URI di linea per il Response Group, ad esempio +14255550165.

13. In **Numero visualizzato** digitare il numero nel modo in cui si desidera venga visualizzato per il Response Group, ad esempio +1 (425) 555-0165.

14. (Facoltativo) In **Descrizione** digitare una descrizione per il flusso di lavoro che si desidera venga visualizzata nella scheda contatto in Skype for Business.

15. In **Tipo di flusso di lavoro** selezionare **Gestito** se il flusso di lavoro verrà gestito da un responsabile di Response Group. Eseguire le operazioni seguenti per assegnare i responsabili di Response Group al flusso di lavoro:

    a. Digitare l'URI SIP di un responsabile per questo flusso di lavoro e fare clic su **Aggiungi**.

    b. Digitare l'URI SIP di ulteriori responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.

    > [!IMPORTANT]
    > A ogni utente designato come responsabile di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.

16. In **Passaggio 2 Selezionare una lingua** fare clic sulla lingua che si desidera utilizzare per il riconoscimento vocale e la sintesi vocale.

17. Se si desidera configurare un messaggio di benvenuto, in **Passaggio 3 Configurare un messaggio di benvenuto** selezionare la casella di controllo **Riprodurre un messaggio di benvenuto**, quindi effettuare una delle operazioni seguenti:

    - Per immettere il messaggio di benvenuto come testo della sintesi vocale per i chiamanti, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file WAVE (WAV) o Windows Media Audio (WMA) per il messaggio di benvenuto, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. In **Passaggio 4 Specificare l'orario di ufficio** fare clic sul fuso orario del flusso di lavoro in **Fuso orario**.

    > [!NOTE]
    > È necessario specificare il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Il fuso orario viene utilizzato per calcolare le ore di apertura e di chiusura. Se, ad esempio, il flusso di lavoro è configurato per l'utilizzo del fuso orario orientale ed è pianificato per l'apertura alle 7.00 e la chiusura alle 23.00, si presuppone che le ore di apertura e di chiusura siano rispettivamente le 7.00 e le 23.00 del fuso orario orientale. È necessario immettere le ore nel formato a 24 ore.

19. Selezionare il tipo di pianificazione dell'orario di ufficio che si desidera utilizzare eseguendo una delle operazioni seguenti:

    - Per utilizzare una pianificazione dell'orario di ufficio predefinita, fare clic su **Usa pianificazione preimpostata**, quindi selezionare la pianificazione che si desidera utilizzare nell'elenco a discesa.

      > [!NOTE]
      > Per potere selezionare questa opzione, è necessario che in precedenza sia stata definita almeno una pianificazione preimpostata. Per definire le pianificazioni preimpostate, utilizzare il cmdlet **New-CSRgsHoursOfBusiness**. Per informazioni dettagliate, [vedere (Facoltativo) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Quando si seleziona una pianificazione preimpostata, nei campi **Giorno**, **Apri** e **Chiudi** vengono inseriti automaticamente i giorni e le ore in cui il Response Group è disponibile.

    - Per utilizzare una pianificazione personalizzata da applicare solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si crea una pianificazione personalizzata per questo flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il Response Group è disponibile.

21. Se si sta creando una  pianificazione  personalizzata, digitare le ore di apertura e chiusura per ogni giorno della settimana in cui il Response Group è disponibile.

    > [!NOTE]
    > Le ore in **Apri** e **Chiudi** devono essere nel formato a 24 ore. Se l'ufficio, ad esempio, è operativo dalle 9.00 alle 17.00 con una pausa per il pranzo a mezzogiorno, è possibile specificare l'orario di ufficio impostando **Apri** su 9.00, **Chiudi** su 12.00, quindi di nuovo **Apri** su 13.00 e **Chiudi** su 17.00.

22. Se si desidera riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il Response Group non è durante l'orario di ufficio**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:

    - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file audio supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):

    - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo del sistema di caselle vocali *\<username\>* @ *\<domainName\>* è ( ad esempio, bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il formato dell'indirizzo utente è _\<username\>_ @ _\<domainName\>_ .

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono *\<number\>* @ *\<domainName\>* è (ad esempio, +14255550121@contoso.com). Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.

24. In **Passaggio 5 Specificare le festività** fare clic sulle caselle di controllo per uno o più insiemi di festività che definiscono i giorni in cui il Response Group è chiuso.

    > [!NOTE]
    > È necessario definire le festività e i relativi insiemi prima di configurare il flusso di lavoro. Utilizzare i cmdlet **New-CsRgsHoliday** e **New-CsRgsHolidaySet** per definire le festività e i relativi insiemi. Per informazioni dettagliate, vedere [(Facoltativo) Definire](optional-define-response-group-holiday-sets.md)i set di festività di Response Group in Skype for Business .

25. Se si desidera riprodurre un messaggio delle festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:

    - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file audio supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):

    - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo del sistema di caselle vocali *\<username\>* @ *\<domainName\>* è ( ad esempio, bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il formato dell'indirizzo utente è _\<username\>_ @ _\<domainName\>_ .

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono *\<number\>* @ *\<domainName\>* è (ad esempio, +14255550121@contoso.com). Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.

27. In **Passaggio 6 Configurare una coda** selezionare la coda in cui si desidera mettere in attesa i chiamanti fino a quando non diventa disponibile un agente in **Selezionare la coda che riceverà le chiamate**.

28. In **Passaggio 7 Configurare la musica di attesa** scegliere la musica che si desidera riprodurre per i chiamanti in attesa della risposta di un agente effettuando una delle operazioni seguenti:

    - Per utilizzare la registrazione della musica di attesa predefinita, fare clic su **Usa predefinita**.

    - Per utilizzare la registrazione di un file audio per la musica di attesa, fare clic su **Selezionare un file musicale**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **un file musicale**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare e quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file audio supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

29. Fare clic su **Distribuisci**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Per utilizzare Skype for Business Server Management Shell per creare o modificare un flusso di lavoro di un gruppo di risposta

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**

3. Creare il messaggio di benvenuto e salvarlo in una variabile. Nella riga di comando digitare il comando seguente:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Ad esempio:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Per utilizzare un file audio per il messaggio, eseguire il cmdlet **Import-CsRgsAudioFile**. Per informazioni dettagliate, [vedere Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Ottenere l'identità della coda o informazioni sull'indirizzamento delle chiamate. Nella riga di comando digitare il comando seguente:

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Per informazioni dettagliate sulla creazione della coda, [vedere New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Definire l'azione predefinita da eseguire quando viene aperto un flusso di lavoro durante l'orario di ufficio e salvarla in una variabile. Nella riga di comando digitare il comando seguente:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Per i flussi di lavoro di gruppi di risposta, l'azione predefinita consiste nell'indirizzare la chiamata a una coda. Questo parametro è obbligatorio per i flussi di lavoro attivi. Non è obbligatorio invece per i flussi di lavoro inattivi.

    Ad esempio:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Se si desidera definire l'orario di ufficio e le festività, è necessario crearli prima della creazione o della modifica del flusso di lavoro. Per informazioni dettagliate, vedere [(Facoltativo) Definire](optional-define-response-group-business-hours.md) l'orario di ufficio di Response Group in Skype for Business [e (Facoltativo) Definire i](optional-define-response-group-holiday-sets.md)set di festività di Response Group in Skype for Business .

7. Se si desidera definire messaggi per le chiamate ricevute al di fuori dell'orario di ufficio o durante le festività, utilizzare il cmdlet **New-CsRgsPrompt** per definire il messaggio e il cmdlet **New-CsRgsCallAction** per definire l'azione da eseguire dopo il messaggio. Per informazioni dettagliate, [vedere New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps) e [New-CsRgsCallAction.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)

8. Recuperare il nome del servizio per il servizio Response Group di Lync Server e assegnarlo a una variabile. Nella riga di comando digitare il comando seguente:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Creare o modificare il flusso di lavoro. Per creare un flusso di lavoro, utilizzare **New-CsRgsWorkflow**. Per modificare un flusso di lavoro, utilizzare **Set-CsRgsWorkflow**. Nella riga di comando digitare il comando seguente:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Ad esempio:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > A tutti gli utenti designati come responsabili dei flussi di lavoro deve essere assegnato il ruolo CsResponseGroupManager.

     > [!NOTE]
     > Per informazioni dettagliate sui parametri facoltativi aggiuntivi, vedere [New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps) o [Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Progettazione di un flusso di lavoro interattivo

È possibile utilizzare Interactive Voice Response (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata verso la coda appropriata. Coppie di domande e risposte stabiliscono la coda da utilizzare. A seconda della risposta del chiamante, il chiamante sente una domanda di follow-up o viene instradato alla coda appropriata. Le domande dell'IVR e le risposte del chiamante vengono fornite all'agente che accetta la chiamata, fornendo informazioni preziose all'agente.

### <a name="overview-of-ivr-features"></a>Panoramica delle funzionalità del sistema IVR

L'applicazione Response Group offre funzionalità di riconoscimento vocale e sintesi vocale in 26 lingue. È possibile immettere domande IVR utilizzando la sintesi vocale oppure un file WAVE (WAV) o Windows Media Audio (WMA). I chiamanti possono rispondere tramite input vocale o multifrequenza (DTMF, Dual-Tone Multi-Frequency).

I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che prevede fino a quattro possibili risposte. L'IVR pone al chiamante una domanda e, a seconda della risposta del chiamante, instrada il chiamante a una coda o pone una seconda domanda. Anche la seconda domanda prevede quattro possibili risposte. A seconda della risposta alla domanda di secondo livello, il chiamante verrà instradato alla coda appropriata.

> [!NOTE]
> Quando si progettano flussi di chiamate utilizzando Skype for Business Server Management Shell, è possibile definire qualsiasi numero di livelli di domande IVR e qualsiasi numero di risposte. Tuttavia, per la facilità di utilizzo del chiamante, è consigliabile non utilizzare più di tre livelli di domande, con non più di cinque risposte per ognuno. Inoltre, se si progetta un flusso di chiamate con più di due livelli di domande con più di quattro risposte ciascuna, non è possibile modificare il flusso di chiamata utilizzando il Skype for Business Server Pannello di controllo.

Le domande dell'IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata.

### <a name="working-with-speech-technologies"></a>Utilizzo di tecnologie vocali

Le tecnologie vocali, quali il riconoscimento vocale e la sintesi vocale, consentono di ottimizzare l'esperienza utente e di accedere alle informazioni in modo più naturale ed efficace. Vi sono alcuni casi, tuttavia, in cui il testo specificato e/o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore di sintesi vocale. Il simbolo "#", ad esempio, viene convertito nella parola "numero" dal motore di sintesi vocale. È possibile correggere questo problema nel modo seguente:

- Il motore di sintesi vocale consente al chiamante quattro tentativi per rispondere alla domanda. Se il chiamante risponde in modo errato alla domanda, ovvero la risposta non è una di quelle specificate, oppure non fornisce alcuna risposta, ottiene un'altra possibilità di rispondere. Il chiamante ha a disposizione cinque tentativi per rispondere alla domanda prima di essere disconnesso. È possibile configurare il sistema IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante. La domanda viene ripetuta ogni volta.

- Per ridurre la possibilità che il rumore ambientale venga interpretato come una risposta dal motore di sintesi vocale, utilizzare risposte più lunghe. Ad esempio, le risposte dovrebbero essere costituite da più di una sillaba e devono avere suoni diversi tra loro.

- Se le domande prevedono risposte vocali e DTMF, configurare le risposte vocali con parole che rappresentano il concetto anziché la risposta DTMF. Ad esempio, anziché "Premere o dire uno" utilizzare "Premere 1 o dire fatturazione".

- Dopo avere progettato il sistema IVR, chiamare il flusso di lavoro, ascoltare le richieste, fornire risposte vocali a ognuna delle richieste e verificare che il sistema funzioni nel modo previsto. È quindi possibile modificare il sistema IVR per correggere eventuali errori di interpretazione. In base all'esempio precedente, se è necessario fare riferimento al tasto #, è possibile riscrivere la richiesta IVR per utilizzare il nome del tasto anziché il simbolo #. Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".

### <a name="ivr-design-examples"></a>Esempi di progettazione del sistema IVR

Nelle sezioni seguenti sono riportati gli esempi di diversi scenari IRV e coppie di domande/risposte.

#### <a name="ivr-with-one-level-of-questions"></a>Sistema IVR con un livello di domande

Nell'esempio seguente è illustrato un sistema IVR con un singolo livello di domande. Utilizza il riconoscimento vocale per rilevare la risposta del chiamante.

 **Domanda:** "Grazie per aver chiamato il reparto Risorse umane. Se desidera parlare con la sezione addetta alle retribuzioni, dica retribuzioni. Altrimenti, dica risorse umane".

- **Viene selezionata l'opzione 1:** il chiamante viene instradato alla sezione addetta alle retribuzioni.

- **Viene selezionata l'opzione 2:** il chiamante viene instradato al reparto Risorse umane.

Nella figura seguente viene illustrato il flusso delle chiamate.

 **Flusso di chiamate interattivo a un livello**

![Progettare i flussi delle chiamate utilizzando Interactive Voice Respo.](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>Sistema IVR con due livelli di domande

Nell'esempio seguente viene illustrato un sistema IVR con due livelli di domande. Il sistema consente ai chiamanti di rispondere tramite input vocale o DTMF con tastiera.

 **Domanda:** "Grazie per aver chiamato il supporto tecnico del reparto IT. Se il problema riguarda l'accesso di rete, prema 1 o dica Rete. Se il problema riguarda il software, prema 2 o dica Software. Se riguarda l'hardware, prema 3 o dica Hardware."

- **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto di rete.

- **Viene selezionata l'opzione 2:** al chiamante viene formulata un'altra domanda.

    **Domanda:** "Se il problema riguarda il sistema operativo, prema 1 o dica Sistema operativo. Se riguarda un'applicazione interna, prema 2 o dica Applicazione interna. Altrimenti, prema 3 o dica Altro".

  - **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto del sistema operativo.

  - **Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto delle applicazioni interne.

  - **Viene selezionata l'opzione 3:** il chiamante viene instradato al team del supporto software.

- **Viene selezionata l'opzione 3:** al chiamante viene formulata un'altra domanda.

    **Domanda:** "Se il problema riguarda una stampante, prema 1. Altrimenti, prema 2".

  - **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto delle stampanti.

  - **Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto hardware.

Nella figura seguente viene illustrato il flusso delle chiamate.

 **Flusso di chiamate interattivo a due livelli**

![Progettare i flussi delle chiamate utilizzando Interactive Voice Respo.](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Procedure consigliate

Nell'elenco seguente vengono descritte alcune procedure consigliate nella progettazione del sistema IVR:

- Consentire al chiamante di selezionare l'attività rapidamente. Evitare di includere troppe informazioni o messaggi di marketing lunghi nel sistema IVR.

- Se si desidera includere un messaggio lungo, è consigliabile aggiungerlo alla fine della prima domanda anziché dopo il messaggio iniziale. I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio iniziale.

- Parla nella lingua del chiamante. Evita la lingua a palafitte. Parla in modo naturale.

- Scrivere domande efficienti ed efficaci. Rimuovere le opzioni non necessarie. Strutturare le informazioni in modo che la risposta prevista del chiamante si trova alla fine della frase. Ad esempio, "Per parlare con il team vendite, premere 1".

- Scegliere risposte vocali semplici. Ad esempio, se si specificano sia risposte DTMF che risposte vocali, utilizzare "Per parlare con il team vendite, prema 1 o dica vendite".

- Testare il sistema IVR con un gruppo di utenti prima di distribuirlo nell'intera organizzazione.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Creazione o modifica di un flusso di lavoro interattivo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Per utilizzare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.

4. Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.

5. Nel campo di ricerca **Selezionare un** servizio digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera creare o modificare. Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.

    > [!NOTE]
    > Verrà aperto lo Strumento di configurazione di Response Group. È inoltre possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL seguente: https:// \<webPoolFqdn\> /RgsConfig.

6. Eseguire una delle operazioni seguenti:

   - In **Crea nuovo flusso di** lavoro fare clic su Crea accanto **a Interattivo.**

   - In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro che si desidera modificare e quindi fare clic su **Modifica** in **Azione**.

7. Se non si desidera che gli utenti chiamino il flusso di lavoro immediatamente, deselezionare la casella di controllo **Attiva il flusso di lavoro**.

    > [!NOTE]
    >  Se si sta creando un flusso di lavoro gestito, è necessario selezionare **Attiva il flusso di lavoro**. Dopo aver salvato il flusso di lavoro gestito attivo, è possibile modificarlo e disattivarlo.

8. Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per federazione**. È inoltre necessario disporre di un criterio di accesso esterno che si applica all'applicazione Response Group configurata per la federazione.

    > [!NOTE]
    > Il criterio di accesso esterno globale si applica all'applicazione Response Group. È possibile configurare il criterio globale per la federazione di Response Group utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet **Set-CsExternalAccessPolicy** per impostare il parametro EnableOutsideAccess su True. Considerare che le impostazioni di criteri globali vengono applicate a tutti gli utenti, a meno che non dispongano di un criterio sito o utente assegnato. Prima di modificare questa impostazione per i Response Group, verificare quindi che le impostazioni della federazione soddisfino i requisiti dell'organizzazione. Per informazioni dettagliate sull'applicazione dei criteri agli utenti, vedere [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Per informazioni dettagliate sull'impostazione di federazione, **vedere Set-CsExternalAccessPolicy** nella documentazione.

    > [!NOTE]
    > Gli utenti ospitati in Skype for Business Online non possono effettuare chiamate a Response Group ospitati in una distribuzione locale. Ciò vale sia nelle distribuzioni ibride che nei casi in cui una distribuzione locale è federata con una distribuzione Skype for Business online.

9. Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita anonimato agente**.

    > [!NOTE]
    > Le chiamate anonime non possono iniziare con un messaggio istantaneo o un video, sebbene l'agente o il chiamante possa aggiungere messaggi istantanei e video dopo l'attivazione della chiamata. Un agente anonimo può inoltre mettere le chiamate in attesa, eseguire trasferimenti di chiamata, nascosti o con consultazione del destinatario, nonché parcheggiare e recuperare le chiamate. Per le chiamate anonime non sono supportate conferenze, condivisione di applicazioni, condivisione del desktop, trasferimenti di file, collaborazione con lavagna e sui dati e registrazione delle chiamate. Gli agenti che utilizzano il plug-in VDI di Lync possono ricevere chiamate in ingresso in modo anonimo, ma non possono effettuare chiamate in uscita in modo anonimo.

10. In **Immettere l'indirizzo del gruppo che riceverà le chiamate** digitare l'indirizzo URI (Uniform Resource Identifier) SIP primario del gruppo che dovrà rispondere alle chiamate al flusso di lavoro.

11. In **Nome visualizzato** digitare il nome che si desidera visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.

    > [!NOTE]
    > Non includere i \<" or "\> caratteri " " nel nome visualizzato. Non utilizzare i nomi visualizzati seguenti, perché sono riservati: **RGS Presence Watcher** o **Servizio Annuncio**.

12. In **Numero di telefono** digitare l'URI di linea per il Response Group, ad esempio +14255550165.

13. In **Numero visualizzato** digitare il numero nel modo in cui si desidera venga visualizzato per il Response Group, ad esempio +1 (425) 555-0165.

14. (Facoltativo) In **Descrizione** digitare una descrizione per il flusso di lavoro che si desidera visualizzare nella scheda contatto in Skype for Business.

15. In **Tipo di flusso di lavoro** selezionare **Gestito** se il flusso di lavoro verrà gestito da un responsabile di Response Group. Eseguire le operazioni seguenti per assegnare i responsabili di Response Group al flusso di lavoro:

    a. Digitare l'URI SIP di un responsabile per questo flusso di lavoro e fare clic su **Aggiungi**.

    b. Digitare l'URI SIP di ulteriori responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.

    > [!IMPORTANT]
    > A ogni utente designato come responsabile di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.

16. In **Passaggio 2 Selezionare una lingua** fare clic sulla lingua da utilizzare per il riconoscimento vocale e la sintesi vocale.

17. Se si desidera configurare un messaggio di benvenuto, in **Passaggio 3 Configurare un messaggio di benvenuto** selezionare la casella di controllo **Riprodurre un messaggio di benvenuto**, quindi effettuare una delle operazioni seguenti:

    - Per immettere il messaggio di benvenuto come testo della sintesi vocale per i chiamanti, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file Wave o Windows Media Audio per il messaggio di benvenuto, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. In **Passaggio 4 Specificare l'orario di ufficio** fare clic sul fuso orario del flusso di lavoro nella casella **Fuso orario**.

    > [!NOTE]
    > È necessario specificare il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Il fuso orario viene utilizzato per calcolare le ore di apertura e di chiusura. Ad esempio, se il flusso di lavoro è configurato per l'utilizzo del fuso orario nordamericano orientale e il flusso di lavoro è pianificato per l'apertura alle 7.00. e chiudere alle 23.00, si presuppone che gli orari di apertura e chiusura siano rispettivamente alle 7.00 ora orientale e alle 11.00 ora orientale. È necessario immettere le ore nel formato a 24 ore.

19. Selezionare il tipo di pianificazione dell'orario di ufficio che si desidera utilizzare eseguendo una delle operazioni seguenti:

    - Per utilizzare una pianificazione dell'orario di ufficio predefinita, fare clic su **Usa pianificazione preimpostata**, quindi selezionare la pianificazione che si desidera utilizzare nell'elenco a discesa.

      > [!NOTE]
      > Per potere selezionare questa opzione, è necessario che in precedenza sia stata definita almeno una pianificazione preimpostata. È possibile definire pianificazioni preimpostate utilizzando il cmdlet **New-CsRgsHoursOfBusiness.** Per informazioni dettagliate, vedere [(Facoltativo) Definire l'orario di ufficio](optional-define-response-group-business-hours.md)di Response Group in Skype for Business . Quando si seleziona una pianificazione preimpostata, nei campi **Giorno**, **Apri** e **Chiudi** vengono inseriti automaticamente i giorni e le ore in cui il Response Group è disponibile.

    - Per utilizzare una pianificazione personalizzata da applicare solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si crea una pianificazione personalizzata per questo flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il Response Group è disponibile.

21. Se si sta creando una pianificazione  personalizzata, digitare **l'orario** di apertura e chiusura quando il Response Group sarà disponibile.

     > [!NOTE]
     > Le ore in **Apri** e **Chiudi** devono essere nel formato a 24 ore. Se l'ufficio, ad esempio, è operativo dalle 9.00 alle 17.00 con una pausa per il pranzo a mezzogiorno, è possibile specificare l'orario di ufficio impostando **Apri** su 9.00, **Chiudi** su 12.00, quindi di nuovo **Apri** su 13.00 e **Chiudi** su 17.00.

22. Se si desidera riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il Response Group non è durante l'orario di ufficio**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:

    - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):

    - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo del sistema di caselle vocali *\<username\>* @ *\<domainname\>* è ad esempio bob@contoso.com.

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il formato dell'indirizzo utente è _\<username\>_ @ _\<domainname\>_ .

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono *\<number\>* @ *\<domainname\>* è (ad esempio, +14255550121@contoso.com). Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.

24. In **Passaggio 5 Specificare le festività** fare clic sulle caselle di controllo per uno o più insiemi di festività che definiscono i giorni in cui il Response Group è chiuso.

    > [!NOTE]
    > È necessario definire le festività e i relativi insiemi prima di configurare il flusso di lavoro. Utilizzare i cmdlet **New-CsRgsHoliday** e **New-CsRgsHolidaySet** per definire le festività e i relativi insiemi. Per informazioni dettagliate, vedere [(Facoltativo) Definire](optional-define-response-group-holiday-sets.md)i set di festività di Response Group in Skype for Business .

25. Se si desidera riprodurre un messaggio delle festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:

    - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file audio supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):

    - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo del sistema di caselle vocali *\<username\>* @ *\<domainname\>* è ad esempio bob@contoso.com.

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il formato dell'indirizzo utente è _\<username\>_ @ _\<domainname\>_ .

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono *\<number\>* @ *\<domainname\>* è (ad esempio, +14255550121@contoso.com). Il nome di dominio viene utilizzato per il routing del chiamante alla destinazione corretta.

27. In **Passaggio 6 Configurare la musica di attesa** scegliere la musica che si desidera riprodurre per i chiamanti in attesa della risposta di un agente effettuando una delle operazioni seguenti:

    - Per utilizzare la registrazione musicale predefinita per le chiamate in attesa, fare clic su **Usa predefinito**.

    - Per utilizzare la registrazione di un file audio per la musica di attesa, fare clic su **Selezionare un file musicale**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **un file musicale**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare e quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

28. In **Passaggio 7 Configurare Interactive Voice Response** specificare la domanda da rivolgere al chiamante nell'intestazione **L'utente ascolterà il seguente testo o messaggio registrato** come indicato di seguito:

    - Per immettere la domanda in formato testo, fare clic su **Usa sintesi vocale**, quindi digitare la domanda nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

    > [!NOTE]
    > Il simbolo "#" viene convertito nella parola "numero" dal motore di sintesi vocale. Se è necessario fare riferimento al tasto #, utilizzare il nome del tasto anziché il simbolo nella richiesta. Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".

    - Per utilizzare un file audio preregistrato contenente la domanda, fare clic su Seleziona una registrazione **e** quindi sul collegamento **a** una registrazione per caricare il file. Nella nuova finestra del browser fare clic **su Sfoglia,** selezionare il file audio e quindi fare clic su **Apri.** Fare **clic Upload** per caricare il file e facoltativamente è possibile digitare la domanda nella casella di testo, in modo da consentire l'inoltro della domanda e della risposta del chiamante all'agente che risponde.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

29. In **Risposta 1** specificare la prima risposta possibile alla domanda effettuando le operazioni seguenti:

    > [!IMPORTANT]
    > Non utilizzare le virgolette doppie (") nelle risposte vocali poiché il sistema IVR potrebbe non funzionare.

    > [!NOTE]
    > È possibile scegliere di consentire ai chiamanti di rispondere a voce o tramite tastierino alfanumerico oppure in entrambi i modi.

    - Se si desidera consentire al chiamante di rispondere a voce, immettere la risposta in **Immettere una risposta vocale**.

    - Se si desidera consentire al chiamante di rispondere premendo un tasto, in **Cifra** fare clic sulla cifra desiderata.

30. Specificare se instradare il chiamante a una coda o se formulare un'altra domanda nel modo seguente:

    - Per instradare il chiamante a una coda, fare clic su **Invia a una coda** e in **Seleziona una coda** fare clic sulla coda che si desidera utilizzare.

    - Per rivolgere un'altra domanda, fare clic su **Formula un'altra domanda**, quindi fare clic su **Usa sintesi vocale** e digitare la domanda oppure fare clic su **Selezionare una registrazione**. Utilizzare i raggruppamenti di risposte di questa sezione per specificare un massimo di quattro possibili risposte alla domanda aggiuntiva e la coda da utilizzare per ogni risposta. Per specificare una terza o una quarta possibile risposta, fare clic sulla casella di controllo **Risposta 3** o **Risposta 4**.

31. Specificare un massimo di altre tre possibili risposte alla domanda originale ripetendo i passaggi 28 e 29 per definire le possibili risposte e l'azione da intraprendere per ciascuna risposta. Per specificare una terza o una quarta risposta possibile, selezionare la casella **di controllo Risposta 3** o **Risposta 4.**

32. Fare clic su **Distribuisci**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Per utilizzare Skype for Business Server Management Shell per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**

3. Recuperare il nome del servizio Response Group Service e assegnarlo a una variabile. Nella riga di comando digitare il comando seguente:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti. Creare innanzitutto i gruppi di agenti. Eseguire: 

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Creare le code. Eseguire: 

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Creare il primo prompt di Response Group. Eseguire: 

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Crea quindi l'azione da eseguire dopo il prompt. Eseguire: 

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Creare la prima risposta di Response Group. Eseguire: 

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Ora crea il secondo prompt, l'azione di chiamata e la risposta. Crea innanzitutto il prompt. Eseguire: 

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Creare la seconda azione di chiamata. Eseguire: 

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Creare la seconda risposta di Response Group. Eseguire: 

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Creare il prompt di primo livello. Eseguire: 

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Creare la domanda di primo livello. Eseguire: 

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Creare ora il flusso di lavoro. Eseguire: 

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > A tutti gli utenti designati come manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.

## <a name="see-also"></a>Vedere anche

[(Facoltativo) Definire i set di festività di Response Group in Skype for Business](optional-define-response-group-holiday-sets.md)

[(Facoltativo) Definire l'orario di ufficio di Response Group in Skype for Business](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)