---
title: 'Lync Server 2013: creare o modificare un flusso di lavoro di gruppo di ricerca'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e56a93ae0be1fd6f047dc6cde724afbea7aa4064
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Creare o modificare un flusso di lavoro di gruppo di ricerca in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-11_

Usare una delle procedure seguenti per creare o modificare un flusso di lavoro di gruppo di ricerca.

<div>


> [!NOTE]  
> È possibile usare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare i flussi di lavoro di gruppo di ricerca. È possibile accedere allo strumento di configurazione del gruppo di risposte dal pannello di controllo di Lync Server oppure aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro di Hunt Group

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
    
      - In **creare un nuovo flusso di lavoro**, accanto a **Cerca gruppo, fare clic su Crea**.
    
      - In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.

7.  Se si è pronti per gli utenti a iniziare a chiamare il flusso di lavoro, selezionare **attiva il flusso di lavoro**.
    
    <div>
    

    > [!NOTE]  
    > Per creare un flusso di lavoro gestito, è necessario selezionare <STRONG>attiva il flusso di lavoro</STRONG>. Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.

    
    </div>

8.  Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** . Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.
    
    <div>
    

    > [!NOTE]  
    > I criteri di accesso esterno globale si applicano all'applicazione Response Group. Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Lync Server o usando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true. Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente. Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione. Per informazioni dettagliate su come applicare i criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>. Per informazioni dettagliate sull'impostazione della Federazione, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.

    
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
    
    <div>
    

    > [!NOTE]  
    > L'URI principale di un flusso di lavoro è la modalità di identificazione e riferimento del flusso di lavoro. L'URI SIP immesso viene creato come oggetto contatto in servizi di dominio Active Directory. Per creare l'URI, l'oggetto deve essere univoco in Active Directory.

    
    </div>

11. In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro (ad esempio, Sales Response Group).
    
    <div>
    

    > [!NOTE]  
    > Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato. Non usare i nomi visualizzati seguenti perché sono riservati: <STRONG>Watcher presenza di RGS</STRONG> o <STRONG>servizio di annuncio</STRONG>.

    
    </div>

12. In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.

13. In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).

14. Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto del client Lync.

15. In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte. Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:
    
    1.  Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**.
    
    2.  Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.
    
    <div>
    

    > [!IMPORTANT]  
    > A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.

    
    </div>

16. In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua che si vuole usare per il riconoscimento vocale e la sintesi vocale.

17. Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:
    
      - Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML, viene visualizzato un messaggio di errore.

        
        </div>
    
      - Per usare una registrazione di file Wave (WAV) o Windows Media Audio (con estensione WMA) per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

18. In **passaggio 4 specificare gli orari di ufficio**, nel **fuso orario**, fare clic sul fuso orario per il flusso di lavoro.
    
    <div>
    

    > [!NOTE]  
    > Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Viene usato per calcolare le ore di apertura e chiusura. Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M. e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 23:00 Eastern Time rispettivamente. È necessario immettere gli orari nella notazione a 24 ore.

    
    </div>

19. Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:
    
      - Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.
        
        <div>
        

        > [!NOTE]  
        > Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata. Puoi definire le pianificazioni predefinite usando il cmdlet <STRONG>New-CsRgsHoursOfBusiness</STRONG> . Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Quando si seleziona una programmazione preimpostata, il <STRONG>giorno</STRONG>, l' <STRONG>apertura</STRONG>e la <STRONG>chiusura</STRONG> vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.

        
        </div>
    
      - Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.

21. Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** per ogni giorno della settimana in cui il gruppo di risposte è disponibile.
    
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
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
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

27. In **passaggio 6 configurare una coda**in **selezionare la coda che riceverà le chiamate**Selezionare la coda che si vuole includere per i chiamanti fino a quando non sarà disponibile un agente.

28. In **passaggio 7 configurare la musica in attesa**, scegliere la musica che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:
    
      - Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.
    
      - Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**. Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** . Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**. Fare clic su **carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti. Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.

        
        </div>

29. Fare clic su **Distribuisci**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Per usare Windows PowerShell per creare o modificare un flusso di lavoro di gruppo di ricerca

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Creare il prompt da riprodurre per il messaggio di benvenuto e salvarlo in una variabile. Nella riga di comando eseguire:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Ad esempio:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> . Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Ottenere l'identità della coda o della domanda in cui verranno indirizzate le chiamate. Nella riga di comando eseguire:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Per informazioni dettagliate sulla creazione della coda, vedere [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Definire l'azione predefinita da intraprendere quando un flusso di lavoro viene aperto durante l'orario di ufficio e salvarlo in una variabile. Nella riga di comando eseguire:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Per i flussi di lavoro di gruppo di ricerca, l'azione predefinita deve indirizzare la chiamata a una coda. Questo parametro è obbligatorio per i flussi di lavoro attivi. Non è necessario per i flussi di lavoro inattivi.

    
    </div>
    
    Ad esempio:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Se si vogliono definire le ore di lavoro e le festività, è necessario crearle prima di creare o modificare il flusso di lavoro. Per informazioni dettagliate, vedere [(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(facoltativo) definire set di festività di Response Group in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Se si vogliono ricevere richieste per le chiamate ricevute fuori sede o in vacanza, usare il cmdlet **New-CsRgsPrompt** per definire il prompt e usare il **nuovo CsRgsCallAction** per definire l'azione da eseguire dopo il prompt. Per informazioni dettagliate, vedere [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Recuperare il nome del servizio per il servizio Response Group di Lync Server e assegnarlo a una variabile. Al comando eseguire:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Creare o modificare il flusso di lavoro. Per creare un flusso di lavoro, USA **New-CsRgsWorkflow**. Per modificare un flusso di lavoro, usare **Set-CsRgsWorkflow**. Nella riga di comando digitare:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Ad esempio:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > A tutti gli utenti designati come Manager per i flussi di lavoro deve essere assegnato il ruolo CsResponseGroupManager.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sui parametri facoltativi aggiuntivi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Opzionale Definire set di festività di Response Group in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

