---
title: 'Lync Server 2013: Panoramica del servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f2589e6c30a6ca928230dde2deb32f23e91967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Panoramica del servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Il servizio di registrazione centralizzato è stato creato per fornire un mezzo per la raccolta controllata di dati, con un ambito esteso o stretto. È possibile raccogliere dati da tutti i server della distribuzione contemporaneamente, definire specifici elementi di cui tenere traccia, impostare flag di traccia e restituire risultati della ricerca da un singolo computer o un'aggregazione di tutti i dati di tutti i server. Il servizio di registrazione centralizzato viene eseguito in tutti i server della distribuzione. L'architettura del servizio di registrazione centralizzato è costituita dai seguenti agenti e servizi:

  - *Agente di servizio di registrazione centralizzato*   ClsAgent. exe è il file eseguibile del servizio che comunica con il controller e riceve i comandi emessi dal controller dall'amministratore. L'agente viene eseguito come servizio in ogni computer Lync Server. Quando l'agente riceve un comando, lo esegue, invia messaggi ai componenti definiti per la traccia e scrive i log di traccia su disco. Legge inoltre i log di traccia per il computer e reinvia i dati di traccia al controller quando richiesto. ClsAgent è in attesa dei comandi sulle porte seguenti: **TCP 50001**, **TCP 50002** e **TCP 50003**.

  - *Controller del servizio di registrazione centralizzato*   ClsControllerLib. dll è il motore di esecuzione dei comandi per Lync Server Management Shell e per ClsController. exe. CLSControllerLib. dll invia i comandi Start, stop, Flush e Search a ClsAgent. Quando vengono inviati i comandi di ricerca, i registri risultanti vengono restituiti al ClsControllerLib. dll e aggregati. Il controller è responsabile dell'invio dei comandi all'agente, del ricevimento dello stato di tali comandi e della gestione dei dati dei file di registro di ricerca come restituiti da tutti gli agenti di qualsiasi computer nell'ambito di ricerca e dell'aggregazione dei dati del log in una forma significativa e ordinata. set di output. Le informazioni contenute negli argomenti seguenti sono incentrate sull'utilizzo di Lync Server Management Shell. ClsController. exe è limitato a un sottoinsieme delle funzionalità e delle funzioni disponibili in Lync Server Management Shell. La Guida di ClsController. exe è disponibile dalla riga di comando digitando `ClsController` la directory predefinita C\\: Program\\files common\\Files Microsoft Lync Server\\2013 ClsAgent.

**Comunicazioni di ClsController a ClsAgent**

![Relazione tra CLSController e CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relazione tra CLSController e CLSAgent.")

È possibile emettere comandi utilizzando l'interfaccia della riga di comando di Windows Server o l'utilizzo di Lync Server Management Shell. I comandi vengono eseguiti nel computer a cui è connesso l'utente e inviati al ClsAgent locale o agli altri computer e pool della distribuzione.

ClsAgent mantiene un file di indice di tutti i file CACHE che si trova nel computer locale. ClsAgent li alloca in modo che vengano distribuiti uniformemente tra i volumi definiti mediante l'opzione CacheFileLocalFolders, senza mai occupare più dell'80% di ogni volume (ovvero il percorso della cache locale e la percentuale sono configurabili mediante il cmdlet **Set-CsClsConfiguration**). ClsAgent è anche responsabile dei file di traccia degli eventi (etl) in scadenza memorizzati nella cache del computer locale. Dopo due settimane (il periodo di tempo è configurabile mediante il cmdlet **Set-CsClsConfiguration**) questi file vengono copiati in una condivisione ed eliminati dal computer locale. Per dettagli, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Quando si riceve una richiesta di ricerca, i criteri di quest'ultima vengono usati per selezionare il set di file etl memorizzati nella cache per eseguire la ricerca in base ai valori nell'indice mantenuto dall'agente.

<div>


> [!NOTE]  
> I file che vengono spostati nella condivisione di file dal computer locale possono essere ricercati da ClsAgent. Dopo che ClsAgent sposta i file nella condivisione, la scadenza e la rimozione dei file non vengono gestite da ClsAgent. È necessario definire un'attività amministrativa per monitorare le dimensioni dei file nella condivisione ed eliminarli o archiviarli.



</div>

I file di log risultanti possono essere letti e analizzati mediante diversi strumenti, tra cui **Snooper.exe** e qualsiasi strumento in grado di leggere file di testo, come **Notepad.exe**. Snooper. exe fa parte degli strumenti di debug di Lync Server 2013 ed è disponibile come download Web da [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).

Come OCSLogger, il servizio di registrazione centralizzato dispone di diversi componenti su cui eseguire la traccia e fornisce le opzioni per selezionare i\_flag, ad\_esempio TF Component e TF diag. Il servizio di registrazione centralizzato conserva anche le opzioni del livello di registrazione di OCSLogger.

Il vantaggio più importante per l'utilizzo di Lync Server Management Shell tramite l'ClsController della riga di comando è che è possibile configurare e definire nuovi scenari utilizzando provider selezionati che si riferiscono allo spazio dei problemi, ai flag personalizzati e ai livelli di registrazione. Gli scenari disponibili in ClsController sono limitati a quelli definiti per l'eseguibile.

Nelle versioni precedenti, OCSLogger.exe consente agli amministratori e al personale di supporto di raccogliere file di traccia dai computer nella distribuzione. OCSLogger, nonostante tutti i punti di forza, ha una lacuna. È possibile collegare i log a un solo computer alla volta. È possibile accedere a più computer usando copie separate di OCSLogger, tuttavia ciò produce più log e nessun modo semplice per aggregare i risultati.

Quando un utente richiede una ricerca di log, ClsController determina i computer a cui inviare la richiesta (in base agli scenari selezionati). Determina anche se la ricerca deve essere inviata alla condivisione di file in cui sono stati salvati i file con estensione etl. Quando i risultati di riceva vengono restituiti a ClsController, il controller li unisce in un singolo set di risultati in ordine cronologico presentato all'utente. Gli utenti possono salvare i risultati di ricerca nel proprio computer locale per ulteriori analisi.

Quando si avvia una sessione di registrazione, si specificano scenari relativi al problema da risolvere. È possibile eseguire due scenari alla volta. Uno di questi scenari deve essere quello AlwaysOn, ovvero deve essere sempre in esecuzione nella distribuzione per raccogliere informazioni su tutti i computer, i pool e i componenti.

<div>


> [!IMPORTANT]  
> Per impostazione predefinita, lo scenario AlwaysOn non è in esecuzione nella distribuzione. È necessario avviarlo in modo esplicito. Una volta avviato, il servizio continua a essere eseguito fino all'arresto esplicito e lo stato di esecuzione permane nonostante i riavvii del computer. Per informazioni dettagliate sull'avvio e l'interruzione degli scenari, vedere <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">using Start for the accentrated Logging Service to capture logs in Lync server 2013</A> e <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using stop for the accentrated Logging Service in Lync Server 2013</A>.



</div>

Quando si verifica un problema, avviare un secondo scenario correlato al problema segnalato. Riprodurre il problema e arrestare la registrazione per il secondo scenario. Iniziare le ricerche dei log relativi al problema segnalato. La raccolta aggregata dei log produce un file di log contenente i messaggi di traccia di tutti i computer nel sito oppure dell'ambito globale della distribuzione. Se la ricerca restituisce più dati di quanti sia possibile analizzarne (condizione nota in genere come rapporto segnale/rumore, in cui il rumore è troppo elevato), è possibile eseguire un'altra ricerca con parametri più limitati. A questo punto, è possibile iniziare a osservare i modelli risultati in modo da formarsi un quadro più chiaro del problema. Infine, dopo aver eseguito un paio di ricerche perfezionate, è possibile individuare i dati rilevanti per il problema e dedurne la causa principale.

<div>


> [!TIP]  
> Quando viene presentato un problema in Lync Server, iniziare a chiedersi "che cosa è già noto sul problema?" Se si quantificano i limiti del problema, è possibile eliminare una parte importante delle entità operative in Lync Server.<BR>Considerare ad esempio uno scenario in cui si sa che gli utenti non ricevono risultati aggiornati quando cercano un contatto. Non vi è alcun motivo per cercare problemi nei componenti multimediali, VoIP aziendale, conferenze e un certo numero di altri componenti. Ciò che potrebbe non essere noto è la posizione effettiva da cui trae origine il problema: lato client o lato server? I contatti vengono raccolti da Active Directory da User Replicator e recapitati al client tramite il server della Rubrica (ABServer). ABServer ottiene gli aggiornamenti dal database RTC (dopo i dati sono stati scritti da User Replicator) e li raccoglie in file della rubrica per impostazione predefinita alle 1.30. I client di Lync Server recuperano la nuova rubrica in base a una pianificazione casuale. Poiché si sa come funziona il processo, è possibile ridurre la ricerca per la causa potenziale di un problema relativo ai dati raccolti da Active Directory da User Replicator, che il ABServer non ha recuperato e creato i file della Rubrica o che i client non scaricare il file della Rubrica.



</div>

</div>

<span> </span>

</div>

</div>

</div>

