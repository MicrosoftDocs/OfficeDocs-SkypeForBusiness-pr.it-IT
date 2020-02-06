---
title: Cercare i log di acquisizione creati dal servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Riepilogo: informazioni su come cercare e leggere i registri di acquisizione dei servizi di registrazione centralizzati in Skype for Business Server 2015.'
ms.openlocfilehash: 234bcdcda4fbf4a0fa7cec364b9a8dbb7b757dc7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816575"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Cercare i log di acquisizione creati dal servizio di registrazione centralizzato in Skype for Business 2015
 
**Riepilogo:** Informazioni su come cercare e leggere i registri di acquisizione dei servizi di registrazione centralizzati in Skype for Business Server 2015.
  
Le funzionalità di ricerca nel servizio di registrazione centralizzata sono utili e potenti per i motivi seguenti: 
  
- Le ricerche e i risultati vengono eseguiti in un singolo computer, un pool, un sito o un ambito globale, in base ai criteri definiti.
    
- Le ricerche possono essere inizialmente ampie e quindi limitate a criteri più mirati, ad esempio ora, componente o computer. Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.
    
- I risultati della ricerca vengono raccolti da tutti i computer e i pool nell'ambito, raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca (limitati agli scenari in uso e ai dati acquisiti dall' scenari). Si usano strumenti noti come **Snooper** o **notepad** per leggere il file di output e i messaggi di analisi provenienti da tutta la distribuzione.
    
Il CLSAgent in ogni singolo computer crea i registri in base allo scenario o agli scenari (due scenari per ogni computer possono essere eseguiti in qualsiasi momento). I log e i file di indice e cache associati vengono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando Cerca indica a CLSAgent le informazioni che devono essere recuperate. CLSAgent esegue la query in base ai file di log, ai file di cache e ai file di indice e restituisce i risultati della ricerca al CLSContoller. CLSController riceve i risultati della ricerca da tutti i computer e i pool nell'ambito della ricerca. Il CLSController quindi aggrega i registri e li inserisce nell'ordine di Delta temporale, la prima voce più antica e procede in tempo fino all'ultima voce più recente.
  
Dopo ogni ricerca, il cmdlet **Sync-CsClsLogging** viene eseguito e svuota la cache usata dalle ricerche (da non confondere con i file di cache gestiti da CLSAgent). La cancellazione della cache consente di verificare che il buffer di acquisizione di file e traccia puliti sia pulito in CLSController per la successiva operazione di ricerca.
  
Per trarre il massimo vantaggio dal servizio di registrazione centralizzato, è necessario avere una buona conoscenza della configurazione della ricerca per restituire solo i messaggi di traccia dal computer e i registri del pool rilevanti per il problema che si sta ricercando. problemi
  
Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata usando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Il resto di questo argomento illustra come definire una ricerca per ottimizzare la risoluzione dei problemi.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base tramite il servizio di registrazione centralizzato

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Verificare di avere lo scenario AlwaysOn in uso nella distribuzione in ambito globale e quindi digitare quanto segue al prompt dei comandi:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Per impostazione predefinita, la ricerca-CsClsLogging invia i risultati della ricerca alla console. Se si vogliono salvare i risultati della ricerca in un file, usare il _ \<percorso\>di file_completo di stringa outputFilePath. Per definire il parametro-OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette, ad esempio. C:\LogFiles\SearchOutput.txt). In questo esempio, devi assicurarti che la directory C:\LogFiles esista e che tu abbia le autorizzazioni per la lettura e la scrittura dei file (autorizzazione NTFS Modify) nella cartella. L'output viene accodato e non viene sovrascritto. Se hai bisogno di file separati, definisci un nome di file distinto per ogni ricerca. 
  
Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base in un pool o un computer usando il servizio di registrazione centralizzato

1. Per limitare la ricerca a un pool o un computer specifico, usare il parametro-computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Per eseguire ricerche in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, ad esempio i seguenti:
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Se è necessario eseguire ricerche in un intero pool anziché in un singolo computer, cambiare il parametro-computer in pool, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separate da virgole.
    
    Ad esempio:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Quando si usano i comandi di ricerca, i pool possono essere qualsiasi pool nella distribuzione, ad esempio pool Front-End, pool di bordi, pool di server di chat permanenti o altri che sono definiti come pool nella distribuzione.
    
    Ad esempio:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Per eseguire una ricerca usando i parametri di ora

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per impostazione predefinita, l'ora di inizio per i parametri specifici del tempo di una ricerca è di 25 minuti prima di cinque minuti dopo il momento in cui si avvia la ricerca. In altre parole, se si cerca in 4:00:00 PM, l'ora di inizio della ricerca verrà visualizzata come 3:35:00 PM to 4:05:00 PM. Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, usare il parametro-StartTime e impostare la stringa di data e ora per indicare l'ora in cui si vuole che venga avviata la ricerca. 
    
    Ad esempio, usando-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 09:00 in 11/20/2012 nel pool. È possibile impostare il percorso di output per scrivere i risultati in un file denominato c:\logfile.txt come indicato di seguito:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La stringa di data e ora specificata può essere "data/ora" o "data di scadenza". "Il comando analizzerà la stringa e utilizzerà i valori appropriati per la data e l'ora e le impostazioni locali e della lingua nel computer in cui è in esecuzione cmdlet. 
  
3. Se si vogliono recuperare i log a partire da 11:00:00 AM su 11/20/2012, è possibile definire il-StartTime. L'intervallo di tempo predefinito per la ricerca è di 30 minuti a meno che non si definisca un specifico-EndTime. La ricerca risultante restituirà i log dal computer o dai pool definiti da 11:00:00 AM a 11:30:00 AM.
    
Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Per eseguire una ricerca di log in un determinato periodo di tempo, Definisci a-StartTime e an-EndTime. È necessario eseguire il log dalle 1 PM alle 2:45 PM nel computer edge01.contoso.net. 
    
Ad esempio:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Per eseguire una ricerca avanzata usando altri criteri e le opzioni di corrispondenza

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per eseguire un comando per raccogliere tracce per componenti specifici, digitare quanto segue:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La ricerca risultante restituisce tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e i pool della distribuzione per i 30 minuti scorsi.
    
3. Per limitare la ricerca con gli stessi componenti solo al pool Front-End denominato pool01.contoso.net, digitare:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. La logica di ricerca predefinita per i comandi con più parametri consiste nell'usare il valore logico o con ognuno dei parametri definiti. Puoi modificare questo comportamento specificando il parametro **-MatchAll** . A tale scopo, digitare quanto segue:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Se gli scenari sono impostati per l'esecuzione costante, ad esempio AlwaysOn, oppure è stato definito un log dello scenario a esecuzione prolungata, è possibile che il computer locale venga disattivato nella condivisione file. Puoi definire la condivisione di file usando il parametro CacheFileNetworkFolder usando New-CsClsConfiguration per creare una nuova configurazione o modificare una configurazione esistente con Set-CsClsConfiguration. Se non si vuole che la ricerca includa la condivisione file nella raccolta di log in cui eseguire la ricerca, usare il parametro SkipNetworkLogs nel modo seguente:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Leggere i registri di acquisizione dal servizio di registrazione centralizzato

Dopo aver eseguito la ricerca, è possibile realizzare il vero vantaggio del servizio di registrazione centralizzato e si ha un file che può essere usato per rintracciare un problema segnalato. È possibile leggere il file in diversi modi. Il file di output è in formato testo standard ed è possibile usare Notepad. exe o qualsiasi altra applicazione che consentirà di aprire e leggere un file di testo. Per i file più grandi e i problemi più complessi, puoi usare uno strumento come Snooper. exe progettato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato. Snooper è incluso negli strumenti di debug disponibili come download separato. È possibile scaricare gli strumenti di debug qui [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257):. Quando si installano gli strumenti di debug, non vengono creati scorciatoie e voci di menu. Dopo aver installato gli strumenti di debug, aprire Esplora risorse, una finestra della riga di comando o Skype for Business Server Management Shell e accedere alla directory (posizione predefinita) C:\Program Skype for Business Server 2015 \ Debugging Tools. Fare doppio clic su Snooper. exe o digitare Snooper. exe, quindi premere INVIO se si usa la riga di comando o Skype for Business Server Management Shell.
  
> [!IMPORTANT]
> Lo scopo di questo argomento non è dettagliare e discutere le tecniche di risoluzione dei problemi. La risoluzione dei problemi e i processi che la circondano sono un argomento complesso. Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere il [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)manuale del Resource Kit di Microsoft Lync Server 2010. I processi e le procedure si applicano ancora a Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Per aprire un file di log in Snooper

1. Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log. Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi. 
    
2. Dopo l'installazione degli strumenti di debug (LyncDebugTools. msi), cambiare directory nella posizione di Snooper. exe usando Esplora risorse o dalla riga di comando. Per impostazione predefinita, gli strumenti di debug si trovano in C:\Program Skype for Business Server 2015 \ Debugging Tools. Fare doppio clic su o eseguire Snooper. exe.
    
3. Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di log, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.
    
4. I messaggi di **traccia** del file di log vengono visualizzati nella scheda **traccia** . fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.
    
### <a name="to-display-a-call-flow-diagram"></a>Per visualizzare un diagramma di flusso delle chiamate

1. Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log. Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.
    
2. Aprire un file di log e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi o selezionare un componente di traccia nella scheda **traccia** .
    
3. Fare clic su **flusso di chiamata**.
    
> [!NOTE]
> Se si fa clic su un messaggio o una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow". Scegliere un altro messaggio o traccia e il flusso di chiamata viene visualizzato se il messaggio o la traccia fa parte di un flusso di chiamata. 
  
4. Spostarsi tra i messaggi o le linee di traccia e notare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.
    
5. Posizionare il puntatore del mouse sugli elementi per ottenere informazioni su messaggi di chiamata, endpoint e altri componenti.
