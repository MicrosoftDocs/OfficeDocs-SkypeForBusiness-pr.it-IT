---
title: Progettazione e creazione di flussi di lavoro di Response Group in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Progettare e creare flussi di lavoro di Response Group in Skype for Business Server VoIP aziendale. Sono coperti sia i flussi di lavoro di gruppo di ricerca che i flussi di lavoro interattivi.
ms.openlocfilehash: a8e53ea6e36a175a33648e4e1783bf2040556c8f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767359"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Progettazione e creazione di flussi di lavoro di Response Group in Skype for business

Progettare e creare flussi di lavoro di Response Group in Skype for Business Server VoIP aziendale. Sono coperti sia i flussi di lavoro di gruppo di ricerca che i flussi di lavoro interattivi.

Un flusso di lavoro definisce il comportamento di una chiamata dall'ora in cui il telefono squilla per l'ora in cui qualcuno risponde alla chiamata. Il flusso di lavoro specifica la coda da usare per la chiamata e specifica il metodo di routing da usare per i flussi di lavoro di gruppo di caccia o le domande e le risposte da usare per i flussi di lavoro di Response Group interattivi.

Un flusso di lavoro definisce anche le impostazioni, ad esempio un messaggio di benvenuto, la musica in attesa, le ore lavorative e le festività.

> [!NOTE]
> È necessario creare gruppi di agenti e code prima di creare un flusso di lavoro che li usa.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Creazione o modifica di un flusso di lavoro di Hunt Group

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro di Hunt Group

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.

4. Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.

5. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si vuole creare o modificare. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.

    > [!NOTE]
    > Viene aperto lo strumento di configurazione Response Group. È anche possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL\<seguente\>: https://webPoolFqdn/rgsconfig.

6. Esegui una delle operazioni seguenti:

   - In **creare un nuovo flusso di lavoro**, accanto a **Cerca gruppo**, fare clic su **Crea**.

   - In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.

7. Se si è pronti per gli utenti a iniziare a chiamare il flusso di lavoro, selezionare **attiva il flusso di lavoro**.

    > [!NOTE]
    >  Se si sta creando un flusso di lavoro gestito, è necessario selezionare **attiva il flusso di lavoro**. Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.

8. Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** . Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.

    > [!NOTE]
    > I criteri di accesso esterno globale si applicano all'applicazione Response Group. Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Skype for Business Server o usando il cmdlet **Set-CsExternalAccessPolicy** per impostare il parametro EnableOutsideAccess su true. Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente. Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione. Per informazioni dettagliate su come applicare i criteri agli utenti, vedere [gestire i criteri di accesso esterno per l'organizzazione](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Per informazioni dettagliate sull'impostazione della Federazione, vedere [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Gli utenti ospitati in Skype for business online non possono inserire le chiamate ai gruppi di risposte ospitati in una distribuzione locale. Questo vale sia per le distribuzioni ibride sia per i casi in cui una distribuzione locale è federata con una distribuzione di Skype for business online.

9. Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita agente anonimato** .

    > [!NOTE]
    > Le chiamate anonime non possono iniziare con la messaggistica istantanea (IM) o il video, anche se l'agente o il chiamante può aggiungere messaggi istantanei e video dopo che la chiamata è stata stabilita. Un agente anonimo può anche inserire chiamate in attesa, trasferire chiamate (sia i trasferimenti non vedenti che consultivi) e parcheggiare e recuperare le chiamate. Le chiamate anonime non supportano le conferenze, la condivisione di applicazioni e la condivisione desktop, il trasferimento di file, la lavagna e la collaborazione ai dati e la registrazione delle chiamate. Gli agenti che usano il plug-in di Lync VDI possono ricevere chiamate in arrivo in forma anonima, ma non possono effettuare chiamate in uscita in modo anonimo.

10. In **immettere l'indirizzo del gruppo che riceverà le chiamate**Digitare l'indirizzo URI (Uniform Resource Identifier) SIP principale del gruppo che risponderà alle chiamate al flusso di lavoro.

    > [!NOTE]
    > L'URI principale di un flusso di lavoro è la modalità di identificazione e riferimento del flusso di lavoro. L'URI SIP immesso viene creato come oggetto contatto in servizi di dominio Active Directory. Per creare l'URI, l'oggetto deve essere univoco in Active Directory.

11. In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro (ad esempio, Sales Response Group).

    > [!NOTE]
    > Non includere i caratteri "<" o ">" nel nome visualizzato. Non usare i nomi visualizzati seguenti perché sono riservati: **Watcher presenza di RGS** o **servizio di annuncio**.

12. In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.

13. In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).

14. Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto in Skype for business.

15. In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte. Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:

    un. Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**.

    b. Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.

    > [!IMPORTANT]
    > A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

16. In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua che si vuole usare per il riconoscimento vocale e la sintesi vocale.

17. Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:

    - Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file Wave (WAV) o Windows Media Audio (con estensione WMA) per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. In **passaggio 4 specificare gli orari di ufficio**, nel **fuso orario**, fare clic sul fuso orario per il flusso di lavoro.

    > [!NOTE]
    > Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Viene usato per calcolare le ore di apertura e chiusura. Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M. e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 23:00 Eastern Time rispettivamente. È necessario immettere gli orari nella notazione a 24 ore.

19. Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:

    - Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.

      > [!NOTE]
      > Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata. Puoi definire le pianificazioni predefinite usando il cmdlet **New-CsRgsHoursOfBusiness** . Per informazioni dettagliate, vedere [(facoltativo) definire le ore lavorative del gruppo di risposte in Skype for business](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Quando si seleziona una programmazione preimpostata, il **giorno**, l' **apertura**e la **chiusura** vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.

    - Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.

21. Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** per ogni giorno della settimana in cui il gruppo di risposte è disponibile.

    > [!NOTE]
    > Le ore di **apertura** e **chiusura** devono essere in notazione oraria 24 ore. Ad esempio, se il tuo ufficio lavora a un giorno lavorativo da 9 a 5 e chiude a mezzogiorno per pranzo, gli orari di apertura sono specificati come **apri** 9:00, **Chiudi** 12:00, **Apri** 13:00 e **Chiudi** 17:00.

22. Se si vuole riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il gruppo di risposte si trova al di fuori degli orari lavorativi** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:

    - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):

    - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria telefonica è * \<nomeutente\>*@*\<NomeDominio\> * (ad esempio, Bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è _ \<nomeutente\>_@_\<NomeDominio\>_.

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono * \<è\>Number*@*\<NomeDominio\> * , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

24. In **passaggio 5 specificare le festività**, fare clic sulle caselle di controllo relative a uno o più set di festività che definiscono i giorni in cui il gruppo di risposte viene chiuso per le aziende.

    > [!NOTE]
    > Prima di configurare il flusso di lavoro, è necessario definire le festività e i set di festività. Usare i cmdlet **New-CsRgsHoliday** e **New-CsRgsHolidaySet** per definire festività e set di festività. Per informazioni dettagliate, vedere [(facoltativo) definire set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md).

25. Se si vuole riprodurre un messaggio in festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:

    - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):

    - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria telefonica è * \<nomeutente\>*@*\<NomeDominio\> * (ad esempio, Bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è _ \<nomeutente\>_@_\<NomeDominio\>_.

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono * \<è\>Number*@*\<NomeDominio\> * , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

27. In **passaggio 6 configurare una coda**in **selezionare la coda che riceverà le chiamate**Selezionare la coda che si vuole includere per i chiamanti fino a quando non sarà disponibile un agente.

28. In **passaggio 7 configurare la musica in attesa**, scegliere la musica che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:

    - Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.

    - Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Fare clic su **Distribuisci**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Per usare Skype for Business Server Management Shell per creare o modificare un flusso di lavoro di gruppo di ricerca

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. Creare il prompt da riprodurre per il messaggio di benvenuto e salvarlo in una variabile. Nella riga di comando eseguire:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Ad esempio:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Per usare un file audio per la richiesta, usare il cmdlet **Import-CsRgsAudioFile** . Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Ottenere l'identità della coda o della domanda in cui verranno indirizzate le chiamate. Nella riga di comando eseguire:

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Per informazioni dettagliate sulla creazione della coda, vedere [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Definire l'azione predefinita da intraprendere quando un flusso di lavoro viene aperto durante l'orario di ufficio e salvarlo in una variabile. Nella riga di comando eseguire:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Per i flussi di lavoro di gruppo di ricerca, l'azione predefinita deve indirizzare la chiamata a una coda. Questo parametro è obbligatorio per i flussi di lavoro attivi. Non è necessario per i flussi di lavoro inattivi.

    Ad esempio:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Se si vogliono definire le ore di lavoro e le festività, è necessario crearle prima di creare o modificare il flusso di lavoro. Per informazioni dettagliate, vedere [(facoltativo) definire le ore lavorative del gruppo di risposte in Skype for business](optional-define-response-group-business-hours.md) e [(facoltativo) definire set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md).

7. Se si vogliono ricevere richieste per le chiamate ricevute fuori sede o in vacanza, usare il cmdlet **New-CsRgsPrompt** per definire il prompt e usare il **nuovo CsRgsCallAction** per definire l'azione da eseguire dopo il prompt. Per informazioni dettagliate, vedere [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Recuperare il nome del servizio per il servizio Response Group di Lync Server e assegnarlo a una variabile. Al comando eseguire:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Creare o modificare il flusso di lavoro. Per creare un flusso di lavoro, USA **New-CsRgsWorkflow**. Per modificare un flusso di lavoro, usare **Set-CsRgsWorkflow**. Nella riga di comando digitare:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Ad esempio:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > A tutti gli utenti designati come Manager per i flussi di lavoro deve essere assegnato il ruolo CsResponseGroupManager.

     > [!NOTE]
     > Per informazioni dettagliate sui parametri facoltativi aggiuntivi, vedere [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) o [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Progettazione di un flusso di lavoro interattivo

Puoi usare la risposta vocale interattiva (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata alla coda appropriata. Le coppie domande e risposte determinano la coda da usare. A seconda della risposta del chiamante, il chiamante sente una domanda di completamento o viene instradato alla coda appropriata. Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata, fornendo informazioni preziose all'agente.

### <a name="overview-of-ivr-features"></a>Panoramica delle funzionalità IVR

L'applicazione Response Group offre funzionalità di riconoscimento vocale e di sintesi vocale in 26 lingue. È possibile immettere domande IVR usando un file di sintesi vocale o Wave (con estensione wav) o Windows Media Audio (con estensione WMA). I chiamanti possono rispondere usando le risposte DTMF (Voice o Dual-Tone Multifrequency).

I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che contiene fino a quattro possibili risposte. Il IVR chiede una domanda al chiamante e, a seconda della risposta del chiamante, instrada il chiamante in una coda o pone una seconda domanda. La seconda domanda può anche avere quattro risposte possibili. A seconda della risposta alla domanda di secondo livello, il chiamante viene indirizzato alla coda appropriata.

> [!NOTE]
> Quando si progetta il flusso delle chiamate con Skype for Business Server Management Shell, è possibile definire qualsiasi livello di domande IVR e un numero qualsiasi di risposte. Tuttavia, per l'usabilità del chiamante, ti consigliamo di non usare più di tre livelli di domande, con non più di cinque risposte ciascuna. Inoltre, se si progetta un flusso di chiamata con più di due livelli di domande con più di quattro risposte, non è possibile modificare il flusso delle chiamate usando il pannello di controllo di Skype for Business Server.

Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata.

### <a name="working-with-speech-technologies"></a>Uso delle tecnologie per la sintesi vocale

Le tecnologie vocali, ad esempio il riconoscimento vocale e la sintesi vocale, possono migliorare l'esperienza dei clienti e consentire agli utenti di accedere alle informazioni in modo più naturale ed efficace. Tuttavia, possono esserci casi in cui il testo specificato o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore vocale. Ad esempio, il simbolo "#" viene tradotto dal motore di sintesi vocale come parola "numero". Questo problema può essere mitigato dalle operazioni seguenti:

- Il motore vocale assegna al chiamante cinque tentativi per rispondere alla domanda. Se il chiamante risponde alla domanda in modo non corretto (ovvero la risposta non è una delle risposte specificate) o non fornisce una risposta, il chiamante riceverà un'altra opportunità per rispondere alla domanda. Il chiamante ha cinque tentativi per rispondere alla domanda prima di essere disconnessa. Puoi configurare il IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante. La domanda viene ripetuta ogni volta.

- Per ridurre al minimo la possibilità di interpretare il rumore ambientale dal motore vocale come risposta, usare risposte più lunghe. Ad esempio, le risposte dovrebbero avere più di una sillaba e dovrebbero sembrare molto diverse tra loro.

- Se le domande hanno risposte sia vocali che DTMF, configurare le risposte vocali con parole che rappresentano il concetto piuttosto che la risposta DTMF. Ad esempio, invece di usare "premi o pronuncia uno" USA "premi 1 o pronuncia fatturazione".

- Dopo aver progettato il tuo IVR, chiama il flusso di lavoro, ascolta le richieste, Rispondi a ogni prompt usando la voce e verifica che i suoni IVR e si comportano come previsto. Puoi quindi modificare il IVR per risolvere eventuali problemi di interpretazione. Dopo l'esempio precedente, se è necessario fare riferimento al tasto #, è possibile riscrivere il prompt di IVR per usare il nome della chiave anziché il simbolo #. Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".

### <a name="ivr-design-examples"></a>Esempi di progettazione IVR

Le sezioni seguenti contengono esempi di diversi scenari IVR e coppie domande e risposte.

#### <a name="ivr-with-one-level-of-questions"></a>IVR con un livello di domande

L'esempio seguente mostra un IVR che usa un livello di domande. Usa il riconoscimento vocale per rilevare la risposta del chiamante.

 **Domanda:** "Grazie per aver chiamato le risorse umane. Se si vuole parlare con il libro paga, dire libro paga. In caso contrario, dire HR. "

- L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team paghe.

- **Opzione 2 selezionata:** Il chiamante viene indirizzato al team risorse umane.

La figura seguente mostra il flusso delle chiamate.

 **Flusso delle chiamate interattive a un livello**

![Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR con due livelli di domande

L'esempio seguente mostra un IVR che usa due livelli di domande. Consente ai chiamanti di rispondere usando l'input della tastiera vocale o DTMF.

 **Domanda:** "Grazie per aver chiamato l'help desk IT. Se si ha un problema di accesso alla rete, premere 1 o Say Network. Se si ha un problema con il software, premere 2 o dire software. Se si ha un problema hardware, premere 3 o dire hardware.

- L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della rete.

- **Opzione 2 selezionata:** Al chiamante viene posta una domanda di follow-up:

    **Domanda:** "Se si tratta di un problema di sistema operativo, premere 1 o dire sistema operativo. Se si tratta di un problema con un'applicazione interna, premere 2 o dire applicazione interna. In caso contrario, premere 3 o dire altro.

  - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto dei sistemi operativi.

  - **Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto delle applicazioni interne.

  - **Opzione 3 selezionata:** Il chiamante viene indirizzato al team di supporto software.

- **Opzione 3 selezionata:** Al chiamante viene posta una domanda di follow-up:

    **Domanda:** "Se si tratta di un problema di stampante, premere 1. In caso contrario, premere 2. "

  - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della stampante.

  - **Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto hardware.

La figura seguente mostra il flusso delle chiamate.

 **Flusso delle chiamate interattive a due livelli**

![Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Procedure consigliate

Nell'elenco seguente vengono illustrate alcune procedure consigliate per la progettazione del dispositivo IVR:

- Consentire al chiamante di accedere rapidamente all'attività. Evitare di fornire troppe informazioni o lunghi messaggi di marketing nel sistema IVR.

- Se si vuole includere un messaggio lungo, valutare la possibilità di accodarlo alla prima domanda anziché al messaggio di benvenuto. I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio di benvenuto.

- Parla nella lingua del chiamante. Evitare la lingua stilata. Parla in modo naturale.

- Scrivere richieste efficienti ed efficaci. Rimuovere eventuali opzioni non necessarie. Strutturare le informazioni in modo che la risposta prevista del chiamante si trovi alla fine della frase. Ad esempio, "per parlare con il team di vendita, premere 1".

- Rendere le risposte vocali intuitive. Ad esempio, se specifichi sia il DTMF che le risposte vocali, USA qualcosa di simile a: "per parlare con il team di vendita, premi 1 o pronuncia vendite".

- Testare il IVR su un gruppo di utenti prima di distribuirlo nell'organizzazione.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Creazione o modifica di un flusso di lavoro interattivo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.

4. Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.

5. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si vuole creare o modificare. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.

    > [!NOTE]
    > Viene aperto lo strumento di configurazione Response Group. È anche possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL\<seguente\>: https://webPoolFqdn/rgsconfig.

6. Esegui una delle operazioni seguenti:

   - In **creare un nuovo flusso di lavoro**, accanto a **interattivo**, fare clic su **Crea**.

   - In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.

7. Se non si è pronti per consentire agli utenti di iniziare a chiamare il flusso di lavoro, deselezionare la casella di controllo **Attiva flusso di lavoro** .

    > [!NOTE]
    >  Se si sta creando un flusso di lavoro gestito, è necessario selezionare **attiva il flusso di lavoro**. Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.

8. Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** . Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.

    > [!NOTE]
    > I criteri di accesso esterno globale si applicano all'applicazione Response Group. Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Skype for Business Server o usando il cmdlet **Set-CsExternalAccessPolicy** per impostare il parametro EnableOutsideAccess su true. Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente. Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione. Per informazioni dettagliate su come applicare i criteri agli utenti, vedere [gestire i criteri di accesso esterno per l'organizzazione](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Per informazioni dettagliate sull'impostazione della Federazione, vedere **Set-CsExternalAccessPolicy** in Documentation.

    > [!NOTE]
    > Gli utenti ospitati in Skype for business online non possono inserire le chiamate ai gruppi di risposte ospitati in una distribuzione locale. Questo vale sia per le distribuzioni ibride sia per i casi in cui una distribuzione locale è federata con una distribuzione di Skype for business online.

9. Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita agente anonimato** .

    > [!NOTE]
    > Le chiamate anonime non possono iniziare con la messaggistica istantanea (IM) o il video, anche se l'agente o il chiamante può aggiungere messaggi istantanei e video dopo che la chiamata è stata stabilita. Un agente anonimo può anche inserire chiamate in attesa, trasferire chiamate (sia i trasferimenti non vedenti che consultivi) e parcheggiare e recuperare le chiamate. Le chiamate anonime non supportano le conferenze, la condivisione di applicazioni e la condivisione desktop, il trasferimento di file, la lavagna e la collaborazione ai dati e la registrazione delle chiamate. Gli agenti che usano il plug-in di Lync VDI possono ricevere chiamate in arrivo in forma anonima, ma non possono effettuare chiamate in uscita in modo anonimo.

10. In **immettere l'indirizzo del gruppo che riceverà le chiamate**Digitare l'indirizzo URI (Uniform Resource Identifier) SIP principale del gruppo che risponderà alle chiamate al flusso di lavoro.

11. In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.

    > [!NOTE]
    > Non includere i caratteri "\<" o "\>" nel nome visualizzato. Non usare i nomi visualizzati seguenti perché sono riservati: **Watcher presenza di RGS** o **servizio di annuncio**.

12. In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.

13. In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).

14. Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto in Skype for business.

15. In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte. Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:

    un. Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**.

    b. Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.

    > [!IMPORTANT]
    > A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

16. In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua da usare per il riconoscimento vocale e la sintesi vocale.

17. Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:

    - Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file audio Wave o Windows Media per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. In **passaggio 4 specificare gli orari di ufficio**, nella casella **fuso orario** fare clic sul fuso orario del flusso di lavoro.

    > [!NOTE]
    > Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Viene usato per calcolare le ore di apertura e chiusura. Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M. e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 11:00 Eastern Time rispettivamente. È necessario immettere gli orari nella notazione a 24 ore.

19. Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:

    - Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.

      > [!NOTE]
      > Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata. Puoi definire le pianificazioni predefinite usando il cmdlet **New-CsRgsHoursOfBusiness** . Per informazioni dettagliate, vedere [(facoltativo) definire le ore lavorative del gruppo di risposte in Skype for business](optional-define-response-group-business-hours.md). Quando si seleziona una programmazione preimpostata, il **giorno**, l' **apertura**e la **chiusura** vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.

    - Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.

21. Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** in cui il gruppo di risposte sarà disponibile.

     > [!NOTE]
     > Le ore di **apertura** e **chiusura** devono essere in notazione oraria 24 ore. Ad esempio, se il tuo ufficio lavora a un giorno lavorativo da 9 a 5 e chiude a mezzogiorno per pranzo, gli orari di apertura sono specificati come **apri** 9:00, **Chiudi** 12:00, **Apri** 13:00 e **Chiudi** 17:00.

22. Se si vuole riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il gruppo di risposte si trova al di fuori degli orari lavorativi** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:

    - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):

    - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria telefonica è * \<nomeutente\>*@*\<NomeDominio\> * (ad esempio, Bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è _ \<nomeutente\>_@_\<NomeDominio\>_.

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono * \<è\>Number*@*\<NomeDominio\> * , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

24. In **passaggio 5 specificare le festività**, fare clic sulle caselle di controllo relative a uno o più set di festività che definiscono i giorni in cui il gruppo di risposte viene chiuso per le aziende.

    > [!NOTE]
    > Prima di configurare il flusso di lavoro, è necessario definire le festività e i set di festività. Usare i cmdlet **New-CsRgsHoliday** e **New-CsRgsHolidaySet** per definire festività e set di festività. Per informazioni dettagliate, vedere [(facoltativo) definire set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md).

25. Se si vuole riprodurre un messaggio in festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:

    - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.

      > [!NOTE]
      > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):

    - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.

    - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria telefonica è * \<nomeutente\>*@*\<NomeDominio\> * (ad esempio, Bob@contoso.com).

    - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è _ \<nomeutente\>_@_\<NomeDominio\>_.

    - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono * \<è\>Number*@*\<NomeDominio\> * , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

27. In **passaggio 6 configurare la musica in attesa**, scegliere ciò che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:

    - Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.

    - Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.

    > [!NOTE]
    > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

28. In **passaggio 7 configurare la risposta vocale interattiva**, in l' **utente sentirà il testo o l'intestazione del messaggio registrato seguente** , specificare la domanda per chiedere ai chiamanti come segue:

    - Per immettere la domanda in formato testo, fare clic su **USA sintesi vocale**e digitare la domanda nella casella di testo.

    > [!NOTE]
    > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

    > [!NOTE]
    > Il simbolo "#" viene tradotto dal motore di sintesi vocale come parola "Number". Se devi fare riferimento al tasto #, devi usare il nome della chiave, invece del simbolo, nella richiesta. Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".

    - Per usare un file audio preregistrato che contiene la domanda, fare clic su **Seleziona una registrazione**e quindi fare clic sul collegamento **registrazione** per caricare il file. Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file e quindi, facoltativamente, è possibile digitare la domanda nella casella di testo (questo consente alla domanda e alla risposta del chiamante di essere inoltrati all'agente che risponde).

      > [!NOTE]
      > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. In **risposta 1**specificare la prima risposta possibile alla domanda eseguendo le operazioni seguenti:

    > [!IMPORTANT]
    > Non usare le virgolette (") in qualsiasi risposta vocale. Le virgolette causano un errore di IVR.

    > [!NOTE]
    > Puoi scegliere di consentire ai chiamanti di rispondere usando il riconoscimento vocale, l'input della tastiera alfanumerica o entrambi.

    - Se si vuole consentire al chiamante di rispondere con il riconoscimento vocale, immettere la risposta in **immettere una risposta vocale**.

    - Se si vuole consentire al chiamante di rispondere premendo un tasto sulla tastiera, nella **cifra**fare clic sulla cifra del tastierino numerico.

30. Specificare se instradare il chiamante a una coda oppure porre un'altra domanda nel modo seguente:

    - Per instradare il chiamante a una coda, fare clic su **Invia a una coda**e in **selezionare una coda**fare clic sulla coda che si vuole usare.

    - Per porre un'altra domanda, fare clic su **Richiedi un'altra domanda**e quindi fare clic su **USA sintesi vocale** e digitare la domanda oppure fare clic su **Seleziona una registrazione**. Usare i raggruppamenti di risposta in questa sezione per specificare fino a quattro possibili risposte alla domanda aggiuntiva e alla coda da usare per ogni risposta. Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo **Response 3** o sulla casella di controllo **Response 4** .

31. Specificare fino a tre risposte più possibili alla domanda originale ripetendo i passaggi 28 e 29 per specificare le possibili risposte e l'azione da eseguire per ogni risposta. Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo Rispondi **3** o sulla casella di controllo **risposta 4** .

32. Fare clic su **Distribuisci**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Per usare Skype for Business Server Management Shell per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile. Nella riga di comando eseguire:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti. Prima di tutto, crea i gruppi di agenti. Eseguire

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Creare le code. Eseguire

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Creare il primo prompt di Response Group. Eseguire

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Crea quindi l'azione da eseguire dopo il prompt. Eseguire

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Creare la risposta al primo Response Group. Eseguire

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Ora crea il secondo messaggio, l'azione chiama e rispondi. Crea prima di tutto il prompt. Eseguire

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Creare la seconda azione di chiamata. Eseguire

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Creare la seconda risposta di Response Group. Eseguire

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Creare la richiesta di primo livello. Eseguire

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Creare la domanda di primo livello. Eseguire

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Creare ora il flusso di lavoro. Eseguire

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

## <a name="see-also"></a>Vedere anche

[Opzionale Definire set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md)

[Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

