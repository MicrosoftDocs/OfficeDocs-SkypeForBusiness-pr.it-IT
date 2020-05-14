---
title: Servizio di registrazione centralizzato in Skype for business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Riepilogo: informazioni sui componenti del servizio e le impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: e65ea3a0a5ed4d86591b630df6d84e436a7efd66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221890"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Servizio di registrazione centralizzato in Skype for business 2015
 
**Riepilogo:** Informazioni sui componenti di servizio e le impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.
  
Il servizio di registrazione centralizzato può: 
  
- Avviare o interrompere la registrazione su uno o più computer e pool con un singolo comando da una posizione centrale.
    
- Registri di ricerca su uno o più computer e pool. È possibile personalizzare la ricerca per restituire tutti i registri su tutti i computer o restituire risultati più concisi.
    
- Configurare sessioni di registrazione come segue:
    
  - Definire uno **Scenario**, oppure utilizzarne uno predefinito. Uno scenario nel servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome dello scenario per identificare lo scopo dello scenario e uno o più provider. È possibile eseguire lo scenario predefinito e uno scenario definito in un determinato momento su un computer.
    
  - Utilizzare un provider esistente, o crearne uno nuovo. Aprovider definisce la raccolta della sessione di registrazione, il livello di dettaglio, i componenti da tracciare e gli elementi applicati ai flag.
    
    > [!TIP]
    >  Se si ha familiarità con OCSLogger, termproviders si riferisce all'insieme di **componenti** (ad esempio, S4, SipStack), a un **tipo di registrazione** (ad esempio, WPP, EventLog o logfile IIS), a un **livello di traccia** , ad esempio all, Verbose, debug, e **flag** , ad esempio TF_COMPONENT TF_DIAG. Questi elementi sono definiti nel provider (variabile di Windows PowerShell) e vengono passati al comando del servizio di registrazione centralizzato.
  
  - Configurare i registri per computer e pool specifici.
    
  - Definire l'ambito della sessione di registrazione dal **sito** opzioni (per eseguire le acquisizioni di registrazione solo nei computer del sito) oppure **Global** (per eseguire acquisizioni di registrazione in tutti i computer della distribuzione).
    
Il servizio di registrazione centralizzato è un potente strumento per la risoluzione dei problemi di grandi o piccole dimensioni, dall'analisi delle cause radice ai problemi di prestazioni. Tutti gli esempi vengono visualizzati con Skype for Business Server Management Shell. La guida viene fornita per lo strumento da riga di comando tramite lo strumento stesso, ma esiste un insieme limitato di funzioni che è possibile eseguire dalla riga di comando. Utilizzando Skype for Business Server Management Shell, è possibile accedere a un insieme di caratteristiche molto più grande e configurabile, in modo da essere sempre la prima scelta. 
  
## <a name="logging-service-components"></a>Componenti del servizio di registrazione

 Il servizio di registrazione centralizzato viene eseguito in tutti i server della distribuzione ed è costituito dai seguenti agenti e servizi:
  
- L'agente di servizio di registrazione centralizzato ClsAgent viene eseguito su tutti i computer in cui è distribuito Skype for Business Server. Ascolta (sulle porte **TCP 50001-50003**) per i comandi di CLSCONTROLLER su WCF e invia nuovamente risposte al controller. Gestisce le sessioni di registro (avvio/arresto/aggiornamento) e cerca i log. Esegue anche operazioni di pulizia come l'archiviazione dei log e le eliminazioni. 
    
- Cmdlet del controller del servizio di registrazione centralizzato Skype for Business Server Management Shell invia i comandi Start, stop, Flush e Search al ClsAgent. Quando vengono inviati i comandi di ricerca, i registri risultanti vengono restituiti al ClsControllerLib. dll e aggregati. Il controller invia comandi all'agente, riceve lo stato di tali comandi e gestisce i dati del file del registro di ricerca quando viene restituito da tutti gli agenti su qualsiasi computer nell'ambito di ricerca e aggrega i dati del registro in un set di output significativo e ordinato. Le informazioni contenute negli argomenti seguenti sono incentrate sull'utilizzo di Skype for Business Server Management Shell.
    
**Comunicazioni di ClsController a ClsAgent**

![Relazione tra CLSController e CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
I comandi vengono rilasciati utilizzando l'interfaccia della riga di comando di Windows Server o l'utilizzo di Skype for Business Server Management Shell. I comandi vengono eseguiti nel computer a cui è connesso l'utente e inviati al ClsAgent locale o agli altri computer e pool della distribuzione.
  
ClsAgent mantiene un file di indice di tutti i file CACHE che si trova nel computer locale. ClsAgent li alloca in modo che vengano distribuiti uniformemente tra i volumi definiti mediante l'opzione CacheFileLocalFolders, senza mai occupare più dell'80% di ogni volume (ovvero il percorso della cache locale e la percentuale sono configurabili mediante il cmdlet **Set-CsClsConfiguration**). ClsAgent è anche responsabile dei file di traccia degli eventi (etl) in scadenza memorizzati nella cache del computer locale. Dopo due settimane (il periodo di tempo è configurabile mediante il cmdlet **Set-CsClsConfiguration**) questi file vengono copiati in una condivisione ed eliminati dal computer locale. Per dettagli, vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando si riceve una richiesta di ricerca, i criteri di quest'ultima vengono usati per selezionare il set di file etl memorizzati nella cache per eseguire la ricerca in base ai valori nell'indice mantenuto dall'agente.
  
> [!NOTE]
> I file che vengono spostati nella condivisione di file dal computer locale possono essere ricercati da ClsAgent. Dopo che ClsAgent sposta i file nella condivisione, la scadenza e la rimozione dei file non vengono gestite da ClsAgent. È necessario definire un'attività amministrativa per monitorare le dimensioni dei file nella condivisione ed eliminarli o archiviarli. 
  
I file di log risultanti possono essere letti e analizzati mediante diversi strumenti, tra cui **Snooper.exe** e qualsiasi strumento in grado di leggere file di testo, come **Notepad.exe**. Snooper. exe fa parte degli strumenti di debug di Skype for Business Server 2015 ed è disponibile come [download Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Come OCSLogger, il servizio di registrazione centralizzato dispone di diversi componenti su cui eseguire la traccia e fornisce le opzioni per selezionare i flag, ad esempio TF_COMPONENT e TF_DIAG. Il servizio di registrazione centralizzato conserva anche le opzioni del livello di registrazione di OCSLogger.
  
Il vantaggio più importante per l'utilizzo di Skype for Business Server Management Shell tramite la riga di comando di ClsController è che è possibile configurare e definire nuovi scenari utilizzando provider selezionati che si riferiscono allo spazio problematico, ai flag personalizzati e ai livelli di registrazione. Gli scenari disponibili in ClsController sono limitati a quelli definiti per l'eseguibile.
  
Nelle versioni precedenti, OCSLogger.exe consente agli amministratori e al personale di supporto di raccogliere file di traccia dai computer nella distribuzione. OCSLogger, nonostante tutti i punti di forza, ha una lacuna. È possibile collegare i log a un solo computer alla volta. È possibile accedere a più computer usando copie separate di OCSLogger, tuttavia ciò produce più log e nessun modo semplice per aggregare i risultati.
  
Quando un utente richiede una ricerca di log, ClsController determina i computer a cui inviare la richiesta (in base agli scenari selezionati). Determina anche se la ricerca deve essere inviata alla condivisione di file in cui sono stati salvati i file con estensione etl. Quando i risultati di riceva vengono restituiti a ClsController, il controller li unisce in un singolo set di risultati in ordine cronologico presentato all'utente. Gli utenti possono salvare i risultati di ricerca nel proprio computer locale per ulteriori analisi.
  
Quando si avvia una sessione di registrazione, si specificano scenari relativi al problema da risolvere. È possibile eseguire due scenari alla volta. Uno di questi scenari deve essere quello AlwaysOn, ovvero deve essere sempre in esecuzione nella distribuzione per raccogliere informazioni su tutti i computer, i pool e i componenti.
  
> [!IMPORTANT]
> Per impostazione predefinita, lo scenario AlwaysOn non è in esecuzione nella distribuzione. È necessario avviarlo in modo esplicito. Una volta avviato, il servizio continua a essere eseguito fino all'arresto esplicito e lo stato di esecuzione permane nonostante i riavvii del computer. Per informazioni dettagliate su come avviare e arrestare gli scenari, vedere [avviare o arrestare l'acquisizione dei log CLS in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Quando si verifica un problema, avviare un secondo scenario correlato al problema segnalato. Riprodurre il problema e arrestare la registrazione per il secondo scenario. Iniziare le ricerche dei log relativi al problema segnalato. La raccolta aggregata dei log produce un file di log contenente i messaggi di traccia di tutti i computer nel sito oppure dell'ambito globale della distribuzione. Se la ricerca restituisce più dati di quanti sia possibile analizzarne (condizione nota in genere come rapporto segnale/rumore, in cui il rumore è troppo elevato), è possibile eseguire un'altra ricerca con parametri più limitati. A questo punto, è possibile iniziare a osservare i modelli risultati in modo da formarsi un quadro più chiaro del problema. Infine, dopo aver eseguito un paio di ricerche perfezionate, è possibile individuare i dati rilevanti per il problema e dedurne la causa principale.
  
> [!TIP]
> Quando viene presentato un problema in Skype for Business Server, iniziare a chiedersi "che cosa è già noto del problema?" Se si quantificano i limiti del problema, è possibile eliminare una parte importante delle entità operative in Skype for Business Server. 
  
Considerare ad esempio uno scenario in cui si sa che gli utenti non ricevono risultati aggiornati quando cercano un contatto. Non vi è alcun motivo per cercare problemi nei componenti multimediali, VoIP aziendale, conferenze e un certo numero di altri componenti. Ciò che potrebbe non essere noto è la posizione effettiva da cui trae origine il problema: lato client o lato server? I contatti vengono raccolti da Active Directory da User Replicator e recapitati al client tramite il server della Rubrica (ABServer). Il ABServer ottiene gli aggiornamenti dal database RTC (in cui User Replicator le ha scritto) e li raccoglie nei file della Rubrica, per impostazione predefinita-1:30 AM. I client Skype for Business Server recuperano la nuova rubrica in base a una pianificazione casuale. Poiché si sa come funziona il processo, è possibile ridurre la ricerca per la causa potenziale di un problema relativo ai dati raccolti da Active Directory da User Replicator, che il ABServer non è in grado di recuperare e creare i file della rubrica oppure che i client non possono scaricare il file della Rubrica.
  
## <a name="current-configuration"></a>Configurazione corrente

Il servizio di registrazione centralizzato è configurato per definire la modalità di raccolta del servizio di registrazione, il modo in cui verrà raccolta, la raccolta e le impostazioni del registro. Queste impostazioni vengono definite globalmente, ovvero per l'intera distribuzione, o per un sito, ovvero un sito denominato nella distribuzione. Per tutte le attività di registrazione definite verranno utilizzate le impostazioni adatte all'identità utilizzata per i comandi di avvio, interruzione, scaricamento e ricerca dei log.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Per visualizzare la configurazione del servizio di registrazione centralizzata corrente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi su **Skype for Business Server Management Shell**.
    
2. Digitare quanto segue al prompt della riga di comando:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo `-Identity` e un ambito, ad esempio "site: Redmond" per restituire solo CsClsConfiguration per il sito Redmond. Se si desiderano informazioni dettagliate su una determinata parte della configurazione, è possibile eseguire il piping dell'output in un altro cmdlet di Windows PowerShell. Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Output di esempio da Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Il risultato del cmdlet consente di visualizzare la configurazione corrente del servizio di registrazione centralizzato.
    
|**Impostazione di configurazione**|**Descrizione**|
|:-----|:-----|
|**Identity** <br/> |Identifica l'ambito e il nome della configurazione corrente. Esistono una sola configurazione a livello globale e una sola per sito.  <br/> |
|**Scenari** <br/> |Elenco di tutti gli scenari definiti per questa configurazione.  <br/> |
|**SearchTerms** <br/> |Termini di ricerca definiti per la configurazione. Microsoft 365 o Office 365, distribuzioni non locali.  <br/> |
|**SecurityGroups** <br/> |Gruppi di sicurezza definiti che controllano gli utenti, ovvero i membri dei gruppi di sicurezza, che possono vedere i computer in base al sito in cui si trovano. Il sito, in questo contesto, è il sito come definito in Generatore di topologie.  <br/> |
|**Regioni** <br/> |Le aree definite vengono utilizzate per raccogliere i SecurityGroups in un'area, ad esempio EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Il parametro indica le dimensioni massime del file di log prima che venga creato un nuovo file di log traccia eventi (.etl). Viene creato un nuovo file di log quando si raggiungono le dimensioni definite anche se non è stato ancora esaurito il tempo massimo impostato in EtlFileRolloverMinutes.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Periodo di tempo massimo definito, espresso in minuti, che può trascorrere per un log prima che venga creato un nuovo file con estensione etl. Viene creato un nuovo file di log quando il timer scade anche se non sono ancora state raggiunte le dimensioni massime impostate in EtlFileRolloverSizeMB.  <br/> |
|**TmfFileSearchPath** <br/> |Posizione in cui cercare i file TMF (Trace Message Format).  <br/> |
|**CacheFileLocalFolders** <br/> |Percorso definito della posizione nei computer in cui vengono scritti i file di cache. CLSAgent scrive i file di cache e viene eseguito nel contesto del servizio di rete. In questo caso, %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Per impostazione predefinita, i file di cache e di log vengono scritti nella stessa directory.  <br/> |
|**CacheFileNetworkFolder** <br/> |È possibile definire un percorso UNC (Universal Naming Convention) per ricevere i file di cache durante le operazioni di registrazione.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definito come tempo massimo, espresso in giorni, di mantenimento dei file di cache.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definito come percentuale dello spazio su disco che può essere utilizzato dai file di cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limite di velocità automatico.  <br/> |
|**ComponentThrottleSample** <br/> |Numero di volte nell'arco di 60 secondi in cui è possibile superare ComponentThrottleLimit.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |Versione minima di CLSAgent di cui è consentita l'esecuzione. Questo elemento è destinato a Microsoft 365 o Office 365.  <br/> |
   

