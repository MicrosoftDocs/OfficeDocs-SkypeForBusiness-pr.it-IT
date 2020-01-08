---
title: 'Lync Server 2013: Panoramica del servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Panoramica del servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Il servizio di registrazione centralizzato è progettato per creare un mezzo per la raccolta controllata di dati, con un ambito ampio o ridotto. È possibile raccogliere dati da tutti i server della distribuzione contemporaneamente, definire elementi specifici da analizzare, impostare i contrassegni di traccia e restituire i risultati della ricerca da un singolo computer o da un'aggregazione di tutti i dati di tutti i server. Il servizio di registrazione centralizzato viene eseguito in tutti i server della distribuzione. L'architettura del servizio di registrazione centralizzata include gli agenti e i servizi seguenti:

  - *Agente di servizio di registrazione centralizzato*   ClsAgent. exe è l'eseguibile del servizio che comunica con il controller e riceve i comandi emessi dal controller dall'amministratore. L'agente viene eseguito come servizio in ogni computer Lync Server. Quando l'agente riceve un comando, esegue il comando, invia i messaggi ai componenti definiti per la traccia e scrive i registri di traccia su disco. Legge anche i registri di traccia per il suo computer e invia i dati di traccia al controller quando richiesto. ClsAgent ascolta i comandi nelle porte seguenti: **tcp 50001**, **TCP 50002**e **TCP 50003**.

  - *Controller di servizio di registrazione centralizzato*   ClsControllerLib. dll è il motore di esecuzione dei comandi per Lync Server Management Shell e per ClsController. exe. CLSControllerLib. dll invia i comandi Start, stop, Flush e Search alla ClsAgent. Quando vengono inviati i comandi di ricerca, i log risultanti vengono restituiti a ClsControllerLib. dll e aggregati. Il controller è responsabile dell'invio di comandi all'agente, della ricezione dello stato di tali comandi e della gestione dei dati del file di log di ricerca che vengono restituiti da tutti gli agenti in qualsiasi computer nell'ambito della ricerca e dell'aggregazione dei dati di log in un formato significativo e ordinato set di output. Le informazioni degli argomenti seguenti sono incentrate sull'uso di Lync Server Management Shell. ClsController. exe è limitato a un sottoinsieme delle funzionalità e delle funzioni disponibili in Lync Server Management Shell. La Guida di ClsController. exe è disponibile dalla riga di comando digitando `ClsController` nella directory predefinita C\\: programmi\\file comuni\\di Microsoft Lync Server\\2013 ClsAgent.

**Comunicazioni ClsController a ClsAgent**

![Relazione tra CLSController e CLSAgent.] (images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relazione tra CLSController e CLSAgent.")

I comandi vengono rilasciati tramite l'interfaccia della riga di comando di Windows Server o tramite Lync Server Management Shell. I comandi vengono eseguiti nel computer in cui è stato effettuato l'accesso e inviati a ClsAgent localmente o agli altri computer e pool della distribuzione.

ClsAgent gestisce un file di indice di tutti. Memorizzare nella CACHE i file presenti nel computer locale. ClsAgent li alloca in modo che siano distribuiti equamente tra i volumi definiti dall'opzione CacheFileLocalFolders, non consumando mai più di 80% di ogni volume (ovvero la posizione della cache locale e la percentuale è configurabile tramite il cmdlet **Set-CsClsConfiguration** ). ClsAgent è anche responsabile dell'invecchiamento dei vecchi file del log di traccia dell'evento memorizzato nella cache (ETL) dal computer locale. Dopo due settimane, ovvero l'intervallo di tempo configurabile con il cmdlet **Set-CsClsConfiguration** , questi file vengono copiati in una condivisione file ed eliminati dal computer locale. Per informazioni dettagliate, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Quando viene ricevuta una richiesta di ricerca, vengono usati i criteri di ricerca per selezionare il set di file ETL memorizzati nella cache per eseguire la ricerca in base ai valori nell'indice gestito dall'agente.

<div>


> [!NOTE]  
> I file spostati nella condivisione file dal computer locale possono essere cercati da ClsAgent. Quando ClsAgent sposta i file nella condivisione file, l'invecchiamento e la rimozione dei file non viene mantenuta da ClsAgent. Devi definire un'attività amministrativa per monitorare le dimensioni dei file nella condivisione file ed eliminarle o archiviarle.



</div>

I file di log risultanti possono essere letti e analizzati usando una varietà di strumenti, tra cui **Snooper. exe** e qualsiasi strumento in grado di leggere un file di testo, ad esempio **notepad. exe**. Snooper. exe fa parte degli strumenti di debug di Lync Server 2013 ed è disponibile come download Web [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).

Come OCSLogger, il servizio di registrazione centralizzato ha diversi componenti da rintracciare e offre opzioni per selezionare contrassegni, ad esempio\_TF Component e\_TF diag. Il servizio di registrazione centralizzato mantiene anche le opzioni del livello di registrazione di OCSLogger.

Il vantaggio più importante per l'uso di Lync Server Management Shell tramite il ClsController della riga di comando è la possibilità di configurare e definire nuovi scenari usando i provider selezionati che si rivolgono allo spazio dei problemi, ai contrassegni personalizzati e ai livelli di registrazione. Gli scenari disponibili per ClsController sono limitati a quelli definiti per l'eseguibile.

Nelle versioni precedenti è stato fornito OCSLogger. exe per consentire agli amministratori e al personale di supporto di raccogliere file di traccia dai computer della distribuzione. OCSLogger, per tutti i suoi punti di forza, ha avuto un difetto. È possibile raccogliere i log solo in un computer in un momento specifico. È possibile accedere a più computer utilizzando copie separate di OCSLogger, ma si è finito con più registri e non è possibile aggregare i risultati in modo semplice.

Quando un utente richiede una ricerca nel log, ClsController determina i computer a cui inviare la richiesta, ovvero in base agli scenari selezionati. Determina anche se la ricerca deve essere inviata alla condivisione file in cui si trovano i file con estensione ETL salvati. Quando i risultati della ricerca vengono restituiti a ClsController, il controller unisce i risultati in un unico set di risultati ordinato in tempo che viene presentato all'utente. Gli utenti possono salvare i risultati della ricerca nel computer locale per un'ulteriore analisi.

Quando si avvia una sessione di registrazione, si specificano scenari relativi al problema che si sta provando a risolvere. Puoi eseguire due scenari in qualsiasi momento. Uno di questi due scenari dovrebbe essere lo scenario AlwaysOn. Come suggerisce il nome, deve essere sempre in uso nella distribuzione, raccogliendo informazioni su tutti i computer, i pool e i componenti.

<div>


> [!IMPORTANT]  
> Per impostazione predefinita, lo scenario AlwaysOn non è in uso nella distribuzione. È necessario avviare esplicitamente lo scenario. Una volta avviato, continuerà a essere eseguito fino a quando non è stato interrotto in modo esplicito e lo stato in esecuzione verrà mantenuto tramite il riavvio dei computer. Per informazioni dettagliate su come avviare e arrestare gli scenari, vedere <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">uso di Start per il servizio di registrazione centralizzata per acquisire i registri in Lync server 2013</A> e <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usare l'interruzione per il servizio di registrazione centralizzato in Lync Server 2013</A>.



</div>

Quando si verifica un problema, avviare un secondo scenario correlato al problema segnalato. Riprodurre il problema e interrompere la registrazione per il secondo scenario. Iniziare le ricerche del log in relazione al problema segnalato. La raccolta aggregata di registri produce un file di log contenente i messaggi di traccia provenienti da tutti i computer del sito o dell'ambito globale della distribuzione. Se la ricerca restituisce più dati che puoi analizzare tenerne (in genere noto come rapporto segnale/rumore, in cui il rumore è troppo alto), puoi eseguire un'altra ricerca con parametri più stretti. A questo punto, puoi iniziare a notare i modelli visualizzati e può aiutarti a ottenere uno stato attivo più chiaro sul problema. Infine, dopo aver eseguito un paio di ricerche ricercate, è possibile trovare dati rilevanti per il problema e individuare la causa radice.

<div>


> [!TIP]  
> Quando si presenta uno scenario di problemi in Lync Server, iniziare a chiedersi "che cosa si conosce già del problema?" Se si quantificano i limiti del problema, è possibile eliminare gran parte delle entità operative in Lync Server.<BR>Si consideri uno scenario di esempio in cui si sa che gli utenti non ottengono risultati correnti quando cercano un contatto. Non ha senso cercare problemi nei componenti multimediali, VoIP aziendale, servizi di conferenza e un certo numero di altri componenti. Non è possibile sapere se il problema è effettivamente: nel client o si tratta di un problema lato server? I contatti vengono raccolti da Active Directory da User Replicator e recapitati al client tramite il server della Rubrica (ABServer). Il ABServer riceve gli aggiornamenti dal database RTC (dove User Replicator li scrive) e li raccoglie in file della Rubrica, per impostazione predefinita-1:30 AM. I client di Lync Server recuperano la nuova rubrica in una programmazione randomizzata. Dato che si sa come funziona il processo, è possibile ridurre la ricerca del potenziale causa di un problema relativo ai dati raccolti da Active Directory da User Replicator, che ABServer non recupera e crea i file della Rubrica o i client non Download del file della Rubrica.



</div>

</div>

<span> </span>

</div>

</div>

</div>

