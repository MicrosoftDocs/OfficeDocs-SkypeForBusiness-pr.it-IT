---
title: Servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Riepilogo: informazioni sui componenti del servizio e sulle impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: a02d2a283716dd01572e0cbd8cccf075b29fd9b8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186833"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Servizio di registrazione centralizzato in Skype for Business 2015
 
**Riepilogo:** Informazioni sui componenti del servizio e sulle impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.
  
Il servizio di registrazione centralizzato può: 
  
- Avviare o interrompere la registrazione in uno o più computer e pool con un singolo comando da una posizione centrale.
    
- Eseguire ricerche nei registri in uno o più computer e pool. È possibile personalizzare la ricerca per restituire tutti i log in tutti i computer oppure restituire risultati più concisi.
    
- Configurare le sessioni di registrazione nel modo seguente:
    
  - Definire uno **scenario**oppure usare uno scenario predefinito. Uno scenario in un servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome di scenario per identificare lo scopo dello scenario e uno o più provider. Puoi eseguire lo scenario predefinito e uno scenario definito in un determinato momento in un computer.
    
  - Utilizzare un provider esistente o creare un nuovo provider. Aprovider definisce la raccolta della sessione di registrazione, il livello di dettaglio, i componenti da tracciare e i contrassegni applicati.
    
    > [!TIP]
    >  Se si ha familiarità con OCSLogger, termproviders fa riferimento alla raccolta di **componenti** (ad esempio, S4, SipStack), a un **tipo di registrazione** (ad esempio, WPP, EventLog o Logfile di IIS), a un livello di **traccia** , ad esempio all, Verbose, debug. e **Contrassegni** (ad esempio, TF_COMPONENT, TF_DIAG). Questi elementi sono definiti nel provider (una variabile di Windows PowerShell) e passati al comando servizio registrazione centralizzato.
  
  - Configurare i registri per computer e pool specifici.
    
  - Definire l'ambito della sessione di registrazione dal **sito** delle opzioni (per eseguire le acquisizioni di registrazione nei computer solo in questo sito) o **globale** (per eseguire le acquisizioni di registrazione in tutti i computer della distribuzione).
    
Il servizio di registrazione centralizzato è un potente strumento per la risoluzione dei problemi di grandi o piccole dimensioni, dall'analisi causa radice ai problemi di prestazioni. Tutti gli esempi vengono visualizzati con Skype for Business Server Management Shell. La guida viene fornita per lo strumento della riga di comando tramite lo strumento stesso, ma esiste un set limitato di funzioni che è possibile eseguire dalla riga di comando. Usando Skype for Business Server Management Shell, hai accesso a un set di caratteristiche molto più ampio e molto più configurabile, in modo che sia sempre la prima scelta. 
  
## <a name="logging-service-components"></a>Registrazione di componenti di servizio

 Il servizio di registrazione centralizzato viene eseguito in tutti i server della distribuzione ed è costituito dai seguenti agenti e servizi:
  
- Agente di servizio di registrazione centralizzato ClsAgent viene eseguito su tutti i computer con Skype for Business Server distribuito. Viene ascoltata (sulle porte **TCP 50001-50003**) per i comandi di CLSCONTROLLER su WCF e restituisce le risposte al controller. Gestisce le sessioni di log (avvio/arresto/aggiornamento) e cerca i registri. Esegue anche operazioni di pulizia come l'archiviazione e l'eliminazione dei log. 
    
- Cmdlet del controller del servizio di registrazione centralizzato Skype for Business Server Management Shell invia i comandi Start, stop, Flush e Search al ClsAgent. Quando vengono inviati i comandi di ricerca, i log risultanti vengono restituiti a ClsControllerLib. dll e aggregati. Il controller invia comandi all'agente, riceve lo stato di questi comandi e gestisce i dati del file di log di ricerca mentre viene restituito da tutti gli agenti in qualsiasi computer nell'ambito della ricerca e aggrega i dati del log in un set di output significativo e ordinato. Le informazioni degli argomenti seguenti sono incentrate sull'uso di Skype for Business Server Management Shell.
    
**Comunicazioni ClsController a ClsAgent**

![Relazione tra CLSController e CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Puoi emettere comandi usando l'interfaccia della riga di comando di Windows Server o usando Skype for Business Server Management Shell. I comandi vengono eseguiti nel computer in cui è stato effettuato l'accesso e inviati a ClsAgent localmente o agli altri computer e pool della distribuzione.
  
ClsAgent gestisce un file di indice di tutti. Memorizzare nella CACHE i file presenti nel computer locale. ClsAgent li alloca in modo che siano distribuiti equamente tra i volumi definiti dall'opzione CacheFileLocalFolders, non consumando mai più di 80% di ogni volume (ovvero la posizione della cache locale e la percentuale è configurabile usando il ** Cmdlet Set-CsClsConfiguration** ). ClsAgent è anche responsabile dell'invecchiamento dei vecchi file del log di traccia dell'evento memorizzato nella cache (ETL) dal computer locale. Dopo due settimane, ovvero l'intervallo di tempo configurabile con il cmdlet **Set-CsClsConfiguration** , questi file vengono copiati in una condivisione file ed eliminati dal computer locale. Per informazioni dettagliate, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando viene ricevuta una richiesta di ricerca, vengono usati i criteri di ricerca per selezionare il set di file ETL memorizzati nella cache per eseguire la ricerca in base ai valori nell'indice gestito dall'agente.
  
> [!NOTE]
> I file spostati nella condivisione file dal computer locale possono essere cercati da ClsAgent. Quando ClsAgent sposta i file nella condivisione file, l'invecchiamento e la rimozione dei file non viene mantenuta da ClsAgent. Devi definire un'attività amministrativa per monitorare le dimensioni dei file nella condivisione file ed eliminarle o archiviarle. 
  
I file di log risultanti possono essere letti e analizzati usando una varietà di strumenti, tra cui **Snooper. exe** e qualsiasi strumento in grado di leggere un file di testo, ad esempio **notepad. exe**. Snooper. exe fa parte degli strumenti di debug di Skype for Business Server 2015 ed è disponibile come [download Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Come OCSLogger, il servizio di registrazione centralizzato ha diversi componenti a cui eseguire la traccia e fornisce le opzioni per selezionare i contrassegni, ad esempio TF_COMPONENT e TF_DIAG. Il servizio di registrazione centralizzato mantiene anche le opzioni del livello di registrazione di OCSLogger.
  
Il vantaggio più importante per l'uso di Skype for Business Server Management Shell sul ClsController della riga di comando è che puoi configurare e definire nuovi scenari usando i provider selezionati che si rivolgono allo spazio dei problemi, ai contrassegni personalizzati e ai livelli di registrazione. Gli scenari disponibili per ClsController sono limitati a quelli definiti per l'eseguibile.
  
Nelle versioni precedenti è stato fornito OCSLogger. exe per consentire agli amministratori e al personale di supporto di raccogliere file di traccia dai computer della distribuzione. OCSLogger, per tutti i suoi punti di forza, ha avuto un difetto. È possibile raccogliere i log solo in un computer in un momento specifico. È possibile accedere a più computer utilizzando copie separate di OCSLogger, ma si è finito con più registri e non è possibile aggregare i risultati in modo semplice.
  
Quando un utente richiede una ricerca nel log, ClsController determina i computer a cui inviare la richiesta, ovvero in base agli scenari selezionati. Determina anche se la ricerca deve essere inviata alla condivisione file in cui si trovano i file con estensione ETL salvati. Quando i risultati della ricerca vengono restituiti a ClsController, il controller unisce i risultati in un unico set di risultati ordinato in tempo che viene presentato all'utente. Gli utenti possono salvare i risultati della ricerca nel computer locale per un'ulteriore analisi.
  
Quando si avvia una sessione di registrazione, si specificano scenari relativi al problema che si sta provando a risolvere. Puoi eseguire due scenari in qualsiasi momento. Uno di questi due scenari dovrebbe essere lo scenario AlwaysOn. Come suggerisce il nome, deve essere sempre in uso nella distribuzione, raccogliendo informazioni su tutti i computer, i pool e i componenti.
  
> [!IMPORTANT]
> Per impostazione predefinita, lo scenario AlwaysOn non è in uso nella distribuzione. È necessario avviare esplicitamente lo scenario. Una volta avviato, continuerà a essere eseguito fino a quando non è stato interrotto in modo esplicito e lo stato in esecuzione verrà mantenuto tramite il riavvio dei computer. Per informazioni dettagliate su come avviare e arrestare gli scenari, vedere [avviare o interrompere l'acquisizione di log CLS in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Quando si verifica un problema, avviare un secondo scenario correlato al problema segnalato. Riprodurre il problema e interrompere la registrazione per il secondo scenario. Iniziare le ricerche del log in relazione al problema segnalato. La raccolta aggregata di registri produce un file di log contenente i messaggi di traccia provenienti da tutti i computer del sito o dell'ambito globale della distribuzione. Se la ricerca restituisce più dati che puoi analizzare tenerne (in genere noto come rapporto segnale/rumore, in cui il rumore è troppo alto), puoi eseguire un'altra ricerca con parametri più stretti. A questo punto, puoi iniziare a notare i modelli visualizzati e può aiutarti a ottenere uno stato attivo più chiaro sul problema. Infine, dopo aver eseguito un paio di ricerche ricercate, è possibile trovare dati rilevanti per il problema e individuare la causa radice.
  
> [!TIP]
> Quando si presenta uno scenario di problemi in Skype for Business Server, iniziare a chiedersi "che cosa si conosce già del problema?" Se si quantificano i limiti del problema, è possibile eliminare gran parte delle entità operative in Skype for Business Server. 
  
Si consideri uno scenario di esempio in cui si sa che gli utenti non ottengono risultati correnti quando cercano un contatto. Non ha senso cercare problemi nei componenti multimediali, VoIP aziendale, servizi di conferenza e un certo numero di altri componenti. Non è possibile sapere se il problema è effettivamente: nel client o si tratta di un problema lato server? I contatti vengono raccolti da Active Directory da User Replicator e recapitati al client tramite il server della Rubrica (ABServer). Il ABServer riceve gli aggiornamenti dal database RTC (dove User Replicator li scrive) e li raccoglie in file della Rubrica, per impostazione predefinita-1:30 AM. I client di Skype for Business Server recuperano la nuova rubrica in una programmazione randomizzata. Dato che si sa come funziona il processo, è possibile ridurre la ricerca del potenziale causa di un problema relativo ai dati raccolti da Active Directory da User Replicator, che ABServer non recupera e crea i file della Rubrica o i client non Download del file della Rubrica.
  
## <a name="current-configuration"></a>Configurazione corrente

Il servizio di registrazione centralizzato è configurato per definire il modo in cui il servizio di registrazione è destinato a raccogliere, come raccoglie, da dove raccoglierà e quali sono le impostazioni del log. Puoi definire queste impostazioni a livello globale (ovvero, per l'intera distribuzione) o per un sito (ovvero un sito denominato nella distribuzione). Tutte le registrazioni definitive utilizzeranno le impostazioni appropriate per l'identità usata per i comandi per avviare, arrestare, svuotare e cercare i registri.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Per visualizzare la configurazione del servizio di registrazione centralizzata corrente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Digitare quanto segue al prompt della riga di comando:
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo `-Identity` e un ambito, ad esempio "site: Redmond", per restituire solo il CsClsConfiguration per il sito Redmond. Per informazioni dettagliate su una determinata parte della configurazione, è possibile reindirizzare l'output in un altro cmdlet di Windows PowerShell. Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Output di esempio di Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Il risultato del cmdlet Visualizza la configurazione corrente del servizio di registrazione centralizzata.
    
|**Impostazione di configurazione**|**Descrizione**|
|:-----|:-----|
|**Identity** <br/> |Identifica l'ambito e il nome per questa configurazione. Esiste una sola configurazione globale e una configurazione per ogni sito.  <br/> |
|**Scenari** <br/> |Elenco di tutti gli scenari definiti per questa configurazione.  <br/> |
|**SearchTerms** <br/> |Termini di ricerca definiti per la configurazione. Office 365, non distribuzioni locali.  <br/> |
|**SecurityGroups** <br/> |I gruppi di sicurezza definiti che controllano chi, ovvero i membri dei gruppi di sicurezza, possono vedere i computer in base al sito in cui si trovano. Il sito, in questo contesto, è il sito definito in Generatore di topologie.  <br/> |
|**Aree geografiche** <br/> |Le aree definite vengono usate per raccogliere SecurityGroups in un'area geografica, ad esempio EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Il parametro indica la dimensione massima del file di log prima che venga creato un nuovo file di log di traccia eventi (ETL). Viene creato un nuovo file di log quando viene raggiunta la dimensione definita anche se il tempo massimo impostato in EtlFileRolloverMinutes non è ancora stato raggiunto.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Intervallo di tempo massimo definito, in minuti, che un log può trascorrere prima che venga creato un nuovo file con estensione ETL. Viene creato un nuovo file di log quando il timer scade anche se la dimensione massima impostata in EtlFileRolloverSizeMB non è ancora stata raggiunta.  <br/> |
|**TmfFileSearchPath** <br/> |Posizione in cui cercare i file di formato del messaggio di traccia.  <br/> |
|**CacheFileLocalFolders** <br/> |Percorso definito nella posizione in cui vengono scritti i file di cache nei computer. CLSAgent scrive i file della cache ed è in esecuzione nel contesto del servizio di rete. In questo caso,% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Per impostazione predefinita, i file di cache e i file di log vengono scritti nella stessa directory.  <br/> |
|**CacheFileNetworkFolder** <br/> |Puoi definire un percorso UNC (Universal Naming Convention) per ricevere i file della cache durante le operazioni di registrazione.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definito come il tempo massimo, in giorni, in cui vengono conservati i file della cache.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definita come percentuale di spazio su disco che può essere usata dai file di cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limitatore automatico della valvola a farfalla.  <br/> |
|**ComponentThrottleSample** <br/> |Numero di volte in 60 secondi che il ComponentThrottleLimit può essere superato.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |La versione minima di CLSAgent è consentita per l'esecuzione. Questo elemento è destinato a Office 365.  <br/> |
   

