---
title: 'Lync Server 2013: Creare o modificare un flusso di lavoro interattivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec10d1d9c3281485078b2d7823978c429ea1be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Creare o modificare un flusso di lavoro interattivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-11_

Usare una delle procedure seguenti per creare o modificare un flusso di lavoro interattivo.

<div>


> [!NOTE]  
> È possibile usare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare flussi di lavoro interattivi. È possibile accedere allo strumento di configurazione del gruppo di risposte dal pannello di controllo di Lync Server oppure aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.

4.  Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.

5.  Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si vuole creare o modificare. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Viene aperto lo strumento di configurazione Response Group. È anche possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Esegui una delle operazioni seguenti:
    
      - In **creare un nuovo flusso di lavoro**, accanto a **interattivo**, fare clic su **Crea**.
    
      - In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.

7.  Se non si è pronti per consentire agli utenti di iniziare a chiamare il flusso di lavoro, deselezionare la casella di controllo **Attiva flusso di lavoro** .
    
    <div>
    

    > [!NOTE]  
    > Per creare un flusso di lavoro gestito, è necessario selezionare <STRONG>attiva il flusso di lavoro</STRONG>. Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.

    
    </div>

8.  Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** . Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.
    
    <div>
    

    > [!NOTE]  
    > I criteri di accesso esterno globale si applicano all'applicazione Response Group. Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Lync Server o usando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true. Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente. Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione. Per informazioni dettagliate su come applicare i criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>. Per informazioni dettagliate sull'impostazione della Federazione, vedere <STRONG>Set-CsExternalAccessPolicy</STRONG> nella documentazione di Lync Server Management Shell.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Gli utenti ospitati in Lync Online non possono inserire le chiamate ai gruppi di risposte ospitati in una distribuzione locale. Questo vale sia per le distribuzioni ibride sia per i casi in cui una distribuzione locale è federata con una distribuzione Lync Online.

    
    </div>

9.  Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita agente anonimato** .
    
    <div>
    

    > [!NOTE]  
    > Le chiamate anonime non possono iniziare con la messaggistica istantanea (IM) o il video, anche se l'agente o il chiamante può aggiungere messaggi istantanei e video dopo che la chiamata è stata stabilita. Un agente anonimo può anche inserire chiamate in attesa, trasferire chiamate (sia i trasferimenti non vedenti che consultivi) e parcheggiare e recuperare le chiamate. Le chiamate anonime non supportano le conferenze, la condivisione di applicazioni e la condivisione desktop, il trasferimento di file, la lavagna e la collaborazione ai dati e la registrazione delle chiamate. Gli agenti che usano il plug-in di Lync VDI possono ricevere chiamate in arrivo in forma anonima, ma non possono effettuare chiamate in uscita in modo anonimo.

    
    </div>

10. In **immettere l'indirizzo del gruppo che riceverà le chiamate**Digitare l'indirizzo URI (Uniform Resource Identifier) SIP principale del gruppo che risponderà alle chiamate al flusso di lavoro.

11. In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.
    
    <div>
    

    > [!NOTE]  
    > Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato. Non usare i nomi visualizzati seguenti perché sono riservati: Watcher presenza di RGS o servizio di annuncio.

    
    </div>

12. In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.

13. In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).

14. Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto nel client Lync.

15. In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte. Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:
    
    1.  Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**..
    
    2.  Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**..
    
    <div>
    

    > [!IMPORTANT]  
    > A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

    
    </div>

16. In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua da usare per il riconoscimento vocale e la sintesi vocale.

17. Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:
    
      - Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

        
        </div>
    
      - Per usare una registrazione di file audio Wave o Windows Media per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

18. In **passaggio 4 specificare gli orari di ufficio**, nella casella **fuso orario** fare clic sul fuso orario del flusso di lavoro.
    
    <div>
    

    > [!NOTE]  
    > Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Viene usato per calcolare le ore di apertura e chiusura. Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M. e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 11:00 Eastern Time rispettivamente. È necessario immettere gli orari nella notazione a 24 ore.

    
    </div>

19. Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:
    
      - Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.
        
        <div>
        

        > [!NOTE]  
        > Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata. Puoi definire le pianificazioni predefinite usando il cmdlet <STRONG>New-CsRgsHoursOfBusiness</STRONG> . Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync Server 2013</A>. Quando si seleziona una programmazione preimpostata, il <STRONG>giorno</STRONG>, l' <STRONG>apertura</STRONG>e la <STRONG>chiusura</STRONG> vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.

        
        </div>
    
      - Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.

21. Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** quando il gruppo di risposte è disponibile.
    
    <div>
    

    > [!NOTE]  
    > Le ore di <STRONG>apertura</STRONG> e <STRONG>chiusura</STRONG> devono essere in notazione oraria 24 ore. Ad esempio, se il tuo ufficio lavora a un giorno lavorativo da 9 a 5 e chiude a mezzogiorno per pranzo, gli orari di apertura sono specificati come <STRONG>apri</STRONG> 9:00, <STRONG>Chiudi</STRONG> 12:00, <STRONG>Apri</STRONG> 13:00 e <STRONG>Chiudi</STRONG> 17:00.

    
    </div>

22. Se si vuole riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il gruppo di risposte si trova al di fuori degli orari lavorativi** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:
    
      - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

        
        </div>
    
      - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):
    
      - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

24. In **passaggio 5 specificare le festività**, fare clic sulle caselle di controllo relative a uno o più set di festività che definiscono i giorni in cui il gruppo di risposte viene chiuso per le aziende.
    
    <div>
    

    > [!NOTE]  
    > Prima di configurare il flusso di lavoro, è necessario definire le festività e i set di festività. Usare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire festività e set di festività. Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire set di festività di Response Group in Lync Server 2013</A>.

    
    </div>

25. Se si vuole riprodurre un messaggio in festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:
    
      - Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

        
        </div>
    
      - Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):
    
      - Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica. Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente. Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono. Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com. Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.

27. In **passaggio 6 configurare la musica in attesa**, scegliere ciò che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:
    
      - Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.
    
      - Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

28. In **passaggio 7 configurare la risposta vocale interattiva**, in l' **utente sentirà il testo o l'intestazione del messaggio registrato seguente** , specificare la domanda per chiedere ai chiamanti come segue:
    
      - Per immettere la domanda in formato testo, fare clic su **USA sintesi vocale**e digitare la domanda nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Il simbolo "#" viene tradotto dal motore di sintesi vocale come parola "Number". Se devi fare riferimento al tasto #, devi usare il nome della chiave, invece del simbolo, nella richiesta. Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".

        
        </div>
    
      - Per usare un file audio preregistrato che contiene la domanda, fare clic su **Seleziona una registrazione**e quindi fare clic sul collegamento **registrazione** per caricare il file. Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file e quindi, facoltativamente, è possibile digitare la domanda nella casella di testo (questo consente alla domanda e alla risposta del chiamante di essere inoltrati all'agente che risponde).
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

29. In **risposta 1**specificare la prima risposta possibile alla domanda eseguendo le operazioni seguenti:
    
    <div>
    

    > [!IMPORTANT]  
    > Non usare le virgolette (") in qualsiasi risposta vocale. Le virgolette causano un errore di IVR.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Puoi scegliere di consentire ai chiamanti di rispondere usando il riconoscimento vocale, l'input della tastiera alfanumerica o entrambi.

    
    </div>
    
      - Se si vuole consentire al chiamante di rispondere con il riconoscimento vocale, immettere la risposta in **immettere una risposta vocale**.
    
      - Se si vuole consentire al chiamante di rispondere premendo un tasto sulla tastiera, nella **cifra**fare clic sulla cifra del tastierino numerico.

30. Specificare se instradare il chiamante a una coda oppure porre un'altra domanda nel modo seguente:
    
      - Per instradare il chiamante a una coda, fare clic su **Invia a una coda**e in **selezionare una coda**fare clic sulla coda che si vuole usare.
    
      - Per porre un'altra domanda, fare clic su **Richiedi un'altra domanda**e quindi fare clic su **USA sintesi vocale** e digitare la domanda oppure fare clic su **Seleziona una registrazione**. Usare i raggruppamenti di risposta in questa sezione per specificare fino a quattro possibili risposte alla domanda aggiuntiva e alla coda da usare per ogni risposta. Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo **Response 3** o sulla casella di controllo **Response 4** .

31. Specificare fino a tre risposte più possibili alla domanda originale ripetendo i passaggi 28 e 29 per specificare le possibili risposte e l'azione da eseguire per ogni risposta. Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo Rispondi **3** o sulla casella di controllo **risposta 4** .

32. Fare clic su **Distribuisci**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Per usare Windows PowerShell per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile. Nella riga di comando eseguire:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti. Prima di tutto, crea i gruppi di agenti. Eseguire
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  Creare le code. Eseguire
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  Creare il primo prompt di Response Group. Eseguire
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  Crea quindi l'azione da eseguire dopo il prompt. Eseguire
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  Creare la risposta al primo Response Group. Eseguire
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  Ora crea il secondo messaggio, l'azione chiama e rispondi. Crea prima di tutto il prompt. Eseguire
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. Creare la seconda azione di chiamata. Eseguire
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. Creare la seconda risposta di Response Group. Eseguire
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. Creare la richiesta di primo livello. Eseguire
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. Creare la domanda di primo livello. Eseguire
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. Creare ora il flusso di lavoro. Eseguire
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > Tutti gli utenti designati come Manager di un Response Group devono essere assegnati al ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

