---
title: 'Lync Server 2013: creare o modificare un flusso di lavoro interattivo'
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
ms.openlocfilehash: 93df8640593769b7b90d8b4e157133f8f7df2f19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Creare o modificare un flusso di lavoro interattivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-11_

Per creare o modificare un flusso di lavoro interattivo, utilizzare una delle procedure seguenti.

<div>


> [!NOTE]  
> È possibile utilizzare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare flussi di lavoro interattivi. È possibile accedere allo strumento di configurazione di Response Group dal pannello di controllo di Lync Server o aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Per utilizzare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.

4.  Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.

5.  Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera creare o modificare. Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Verrà aperto lo strumento di configurazione di Response Group. È inoltre possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando il seguente URL: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Eseguire una delle operazioni seguenti:
    
      - In **Crea un nuovo flusso di lavoro**, accanto a **interattivo**, fare clic su **Crea**.
    
      - In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro che si desidera modificare e quindi fare clic su **Modifica** in **Azione**.

7.  Se non si desidera che gli utenti chiamino il flusso di lavoro immediatamente, deselezionare la casella di controllo **Attiva il flusso di lavoro**.
    
    <div>
    

    > [!NOTE]  
    > Se si desidera creare un flusso di lavoro gestito, selezionare <STRONG>Attiva il flusso di lavoro</STRONG>. Dopo aver salvato il flusso di lavoro gestito attivo, è possibile modificarlo e disattivarlo.

    
    </div>

8.  Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per federazione**. È inoltre necessario disporre di un criterio di accesso esterno che si applica all'applicazione Response Group configurata per la Federazione.
    
    <div>
    

    > [!NOTE]  
    > Il criterio di accesso esterno globale è valido per l'applicazione Response Group. È possibile configurare i criteri globali per la Federazione dei Response Group utilizzando il pannello di controllo di Lync Server oppure utilizzando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true. Considerare che le impostazioni di criteri globali vengono applicate a tutti gli utenti, a meno che non dispongano di un criterio sito o utente assegnato. Prima di modificare questa impostazione per i Response Group, verificare quindi che le impostazioni della federazione soddisfino i requisiti dell'organizzazione. Per informazioni dettagliate sulla modalità di applicazione dei criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external Access Policy in Lync Server 2013</A>. Per informazioni dettagliate sull'impostazione di federazione, vedere <STRONG>Set-CsExternalAccessPolicy</STRONG> nella documentazione di Lync Server Management Shell.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Gli utenti ospitati in Lync Online non possono effettuare chiamate ai Response Group ospitate in una distribuzione locale. Questo è vero sia nelle distribuzioni ibride sia nei casi in cui una distribuzione locale è federata con una distribuzione di Lync Online.

    
    </div>

9.  Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita anonimato agente**.
    
    <div>
    

    > [!NOTE]  
    > Le chiamate anonime non possono iniziare con un messaggio istantaneo o un video, sebbene l'agente o il chiamante possa aggiungere messaggi istantanei e video dopo l'attivazione della chiamata. Un agente anonimo può inoltre mettere le chiamate in attesa, eseguire trasferimenti di chiamata, nascosti o con consultazione del destinatario, nonché parcheggiare e recuperare le chiamate. Per le chiamate anonime non sono supportate conferenze, condivisione di applicazioni, condivisione del desktop, trasferimenti di file, collaborazione con lavagna e sui dati e registrazione delle chiamate. Gli agenti che utilizzano il plug-in di Lync VDI sono in grado di ricevere le chiamate in arrivo anonime, ma non possono effettuare chiamate in uscita in modo anonimo.

    
    </div>

10. In **Immettere l'indirizzo del gruppo che riceverà le chiamate** digitare l'indirizzo URI (Uniform Resource Identifier) SIP primario del gruppo che dovrà rispondere alle chiamate al flusso di lavoro.

11. In **nome visualizzato**Digitare il nome che si desidera visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.
    
    <div>
    

    > [!NOTE]  
    > Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato. Non utilizzare i nomi visualizzati seguenti poiché sono riservati: RGS Presence Watcher o Servizio Annuncio.

    
    </div>

12. In **Numero di telefono** digitare l'URI di linea per il Response Group, ad esempio +14255550165.

13. In **Numero visualizzato** digitare il numero nel modo in cui si desidera venga visualizzato per il Response Group, ad esempio +1 (425) 555-0165.

14. Optional In **Descrizione**Digitare una descrizione per il flusso di lavoro che si desidera venga visualizzata nella scheda contatto nel client Lync.

15. In **Tipo di flusso di lavoro** selezionare **Gestito** se il flusso di lavoro verrà gestito da un responsabile di Response Group. Per assegnare i responsabili dei Response Group al flusso di lavoro, eseguire le operazioni seguenti:
    
    1.  Digitare l'URI SIP di un responsabile per il flusso di lavoro e fare clic su **Aggiungi**..
    
    2.  Digitare l'URI SIP di ulteriori responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**..
    
    <div>
    

    > [!IMPORTANT]  
    > A ogni utente designato come responsabile di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.

    
    </div>

16. In **Passaggio 2 Selezionare una lingua** fare clic sulla lingua da utilizzare per il riconoscimento vocale e la sintesi vocale.

17. Se si desidera configurare un messaggio di benvenuto, in **Passaggio 3 Configurare un messaggio di benvenuto** selezionare la casella di controllo **Riprodurre un messaggio di benvenuto**, quindi effettuare una delle operazioni seguenti:
    
      - Per immettere il messaggio di benvenuto come testo della sintesi vocale per i chiamanti, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

        
        </div>
    
      - Per utilizzare la registrazione di un file Wave o Windows Media Audio per il messaggio di benvenuto, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

18. In **Passaggio 4 Specificare l'orario di ufficio** fare clic sul fuso orario del flusso di lavoro nella casella **Fuso orario**.
    
    <div>
    

    > [!NOTE]  
    > È necessario specificare il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Il fuso orario viene utilizzato per calcolare le ore di apertura e di chiusura. Ad esempio, se il flusso di lavoro è configurato per l'utilizzo del fuso orario orientale del Nord America e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M. e chiudere alle 11:00 P.M., gli orari di apertura e di chiusura sono considerati rispettivamente 7:00 Eastern Time e 11:00 Eastern Time. È necessario immettere le ore nel formato a 24 ore.

    
    </div>

19. Selezionare il tipo di pianificazione dell'orario di ufficio che si desidera utilizzare eseguendo una delle operazioni seguenti:
    
      - Per utilizzare una pianificazione dell'orario di ufficio predefinita, fare clic su **Usa pianificazione preimpostata**, quindi selezionare la pianificazione che si desidera utilizzare nell'elenco a discesa.
        
        <div>
        

        > [!NOTE]  
        > Per potere selezionare questa opzione, è necessario che in precedenza sia stata definita almeno una pianificazione preimpostata. Per definire le pianificazioni preimpostate, utilizzare il cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire gli orari di ufficio di Response Group in Lync Server 2013</A>. Quando si seleziona una pianificazione preimpostata, nei campi <STRONG>Giorno</STRONG>, <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> vengono inseriti automaticamente i giorni e le ore in cui il Response Group è disponibile.

        
        </div>
    
      - Per utilizzare una pianificazione personalizzata da applicare solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.

20. Se si crea una pianificazione personalizzata per questo flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il Response Group è disponibile.

21. Se si crea una pianificazione personalizzata, digitare le ore in **Apri** e **Chiudi** in cui il Response Group è disponibile.
    
    <div>
    

    > [!NOTE]  
    > Le ore in <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> devono essere nel formato a 24 ore. Se l'ufficio, ad esempio, è operativo dalle 9.00 alle 17.00 con una pausa per il pranzo a mezzogiorno, è possibile specificare l'orario di ufficio impostando <STRONG>Apri</STRONG> su 9.00, <STRONG>Chiudi</STRONG> su 12.00, quindi di nuovo <STRONG>Apri</STRONG> su 13.00 e <STRONG>Chiudi</STRONG> su 17.00.

    
    </div>

22. Se si desidera riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il Response Group non è durante l'orario di ufficio**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:
    
      - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.

        
        </div>
    
      - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

23. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):
    
      - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\>
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com). Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.

24. In **Passaggio 5 Specificare le festività** fare clic sulle caselle di controllo per uno o più insiemi di festività che definiscono i giorni in cui il Response Group è chiuso.
    
    <div>
    

    > [!NOTE]  
    > È necessario definire le festività e i relativi insiemi prima di configurare il flusso di lavoro. Utilizzare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire le festività e i relativi insiemi. Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire i set di festività di Response Group in Lync Server 2013</A>.

    
    </div>

25. Se si desidera riprodurre un messaggio delle festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:
    
      - Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.

        
        </div>
    
      - Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

26. Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):
    
      - Per interrompere la chiamata, fare clic su **Interrompi chiamata**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica. Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente. Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\>
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono. Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com). Il nome di dominio viene utilizzato per il routing del chiamante alla destinazione corretta.

27. In **Passaggio 6 Configurare la musica di attesa** scegliere la musica che si desidera riprodurre per i chiamanti in attesa della risposta di un agente effettuando una delle operazioni seguenti:
    
      - Per utilizzare la registrazione musicale predefinita per le chiamate in attesa, fare clic su **Usa predefinito**.
    
      - Per utilizzare la registrazione di un file audio per la musica di attesa, fare clic su **Selezionare un file musicale**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **un file musicale**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare e quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

28. In **Passaggio 7 Configurare Interactive Voice Response** specificare la domanda da rivolgere al chiamante nell'intestazione **L'utente ascolterà il seguente testo o messaggio registrato** come indicato di seguito:
    
      - Per immettere la domanda in formato testo, fare clic su **Usa sintesi vocale**, quindi digitare la domanda nella casella di testo.
        
        <div>
        

        > [!NOTE]  
        > Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Il simbolo "#" viene convertito nella parola "numero" dal motore di sintesi vocale. Se è necessario fare riferimento al tasto #, utilizzare il nome del tasto anziché il simbolo nella richiesta. Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".

        
        </div>
    
      - Per utilizzare un file con audio preregistrato contenente la domanda, fare clic su **Selezionare una registrazione**, quindi fare clic sul collegamento **una registrazione** per caricare il file. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file, quindi facoltativamente è possibile digitare la domanda nella casella di testo. In questo modo la domanda e la risposta del chiamante verranno inoltrate all'agente che risponde.
        
        <div>
        

        > [!NOTE]  
        > Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici. Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

29. In **Risposta 1** specificare la prima risposta possibile alla domanda effettuando le operazioni seguenti:
    
    <div>
    

    > [!IMPORTANT]  
    > Non utilizzare le virgolette doppie (") nelle risposte vocali poiché il sistema IVR potrebbe non funzionare.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > È possibile scegliere di consentire ai chiamanti di rispondere a voce o tramite tastierino alfanumerico oppure in entrambi i modi.

    
    </div>
    
      - Se si desidera consentire al chiamante di rispondere a voce, immettere la risposta in **Immettere una risposta vocale**.
    
      - Se si desidera consentire al chiamante di rispondere premendo un tasto, in **Cifra** fare clic sulla cifra desiderata.

30. Specificare se instradare il chiamante a una coda o se formulare un'altra domanda nel modo seguente:
    
      - Per instradare il chiamante a una coda, fare clic su **Invia a una coda** e in **Seleziona una coda** fare clic sulla coda che si desidera utilizzare.
    
      - Per rivolgere un'altra domanda, fare clic su **Formula un'altra domanda**, quindi fare clic su **Usa sintesi vocale** e digitare la domanda oppure fare clic su **Selezionare una registrazione**. Utilizzare i raggruppamenti di risposte di questa sezione per specificare un massimo di quattro possibili risposte alla domanda aggiuntiva e la coda da utilizzare per ogni risposta. Per specificare una terza o una quarta possibile risposta, fare clic sulla casella di controllo **Risposta 3** o **Risposta 4**.

31. Specificare un massimo di altre tre possibili risposte alla domanda originale ripetendo i passaggi 28 e 29 per definire le possibili risposte e l'azione da intraprendere per ciascuna risposta. Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo **Response 3** o la casella di controllo **Response 4** .

32. Fare clic su **Distribuisci**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Per utilizzare Windows PowerShell per creare o modificare un flusso di lavoro interattivo

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Recuperare il nome del servizio Response Group Service e assegnarlo a una variabile. Nella riga di comando digitare il comando seguente:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti. Per prima cosa, creare i gruppi di agenti. Eseguire: 
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  Creare le code. Eseguire: 
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  Creare il primo prompt di Response Group. Eseguire: 
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  Creare quindi l'azione da eseguire dopo il prompt. Eseguire: 
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  Creare la risposta del primo Response Group. Eseguire: 
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  A questo punto, creare la seconda richiesta, l'azione di chiamata e la risposta. Creare innanzitutto il prompt. Eseguire: 
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. Creare la seconda azione di chiamata. Eseguire: 
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. Creare la seconda risposta Response Group. Eseguire: 
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. Creare il prompt di primo livello. Eseguire: 
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. Creare la domanda di primo livello. Eseguire: 
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. A questo punto, creare il flusso di lavoro. Eseguire: 
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > Tutti gli utenti designati come Manager di un Response Group devono essere assegnati al ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

