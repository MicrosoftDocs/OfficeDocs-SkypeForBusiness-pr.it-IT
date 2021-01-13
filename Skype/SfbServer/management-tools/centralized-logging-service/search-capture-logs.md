---
title: Registri di acquisizione della ricerca creati dal servizio di registrazione centralizzato in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni su come eseguire la ricerca e la lettura dei log di acquisizione del servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835126"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Registri di acquisizione della ricerca creati dal servizio di registrazione centralizzato in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire la ricerca e la lettura dei log di acquisizione del servizio di registrazione centralizzato in Skype for Business Server 2015.
  
Le funzionalità di ricerca nel servizio di registrazione centralizzato sono utili e potenti per i motivi seguenti: 
  
- Le ricerche e i risultati vengono eseguiti su un unico computer, un pool, un sito o un ambito globale in base ai criteri definiti.
    
- Inizialmente è possibile eseguire ricerche ad ampio spettro e successivamente restringerle adottando criteri più mirati, ad esempio un'ora, un componente o un computer. Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.
    
- I risultati di ricerca prelevati da tutti i computer e i pool compresi nell'ambito vengono raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca, limitatamente agli scenari eseguiti e ai dati acquisiti. È possibile utilizzare strumenti noti come **Snooper** o **Blocco note** per leggere il file di output e i messaggi di traccia di tutta la distribuzione.
    
In ogni singolo computer il componente Agente del servizio di registrazione centralizzato (CLSAgent) crea i registri in base allo scenario o agli scenari in esecuzione (è possibile eseguire due scenari per computer in un dato momento). I log e i file di indice e cache associati sono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando di ricerca indica a CLSAgent quali informazioni recuperare. CLSAgent esegue la query nei file di log, cache e indice e restituisce i risultati della ricerca al Controller servizio di registrazione centralizzato (CLSContoller). Quest'ultimo riceve i risultati di ricerca da tutti i computer e pool compresi nell'ambito della ricerca. Quindi aggrega (combina) i log e li ordina in base a un intervallo di tempo, dalla voce meno recente alla più recente.
  
Al termine di ogni ricerca viene eseguito il cmdlet **Sync-CsClsLogging**, che scarica la cache utilizzata per le ricerche (da non confondere con i file cache gestiti da CLSAgent). Lo scaricamento della cache aiuta a garantire la presenza di un buffer di acquisizione del log e del file di traccia vuoto in CLSController per la successiva operazione di ricerca.
  
Per ottenere il massimo vantaggio dal servizio di registrazione centralizzato, è necessaria una buona conoscenza di come configurare la ricerca per restituire solo i messaggi di traccia provenienti dai registri del computer e del pool rilevanti per il problema che si sta ricercando. problemi
  
Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o del controllo di accesso basato sui ruoli di CsServerAdministrator oppure di un ruolo RBAC personalizzato che contenga uno dei due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Nel resto di questo argomento viene illustrato come definire una ricerca per ottimizzare la risoluzione dei problemi.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base utilizzando il servizio di registrazione centralizzato

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Verificare che nella distribuzione presso l'ambito globale sia in esecuzione lo scenario AlwaysOn e digitare quanto segue al prompt dei comandi:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Per impostazione predefinita, Search-CsClsLogging invia i risultati della ricerca alla console. Se si desidera salvare i risultati della ricerca in un file, utilizzare-OutputFilePath  _\<string fully qualified file path\>_ . Per definire il parametro-OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette (ad esempio, C:\LogFiles\SearchOutput.txt). Nell'esempio fornito è necessario verificare che la directory C:\LogFiles esista e di disporre delle autorizzazioni di lettura e scrittura (autorizzazione NTFS Modifica) dei file nella cartella. L'output viene aggiunto e non sovrascritto. Se sono necessari singoli file, definire un nome di file per ogni ricerca. 
  
Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base in un pool o in un computer utilizzando il servizio di registrazione centralizzato

1. Per limitare la ricerca a un pool o a un computer specifico, utilizzare il parametro-computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Per eseguire la ricerca in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, come l'esempio seguente:
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Se è necessario eseguire una ricerca in un intero pool anziché in un singolo computer, modificare il parametro-computer con i pool, rimuovere il nome del computer e sostituirlo con il pool o i pool racchiusi tra virgolette separate da virgole.
    
    Ad esempio:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Quando si utilizzano i comandi di ricerca, i pool possono essere tutti i pool della distribuzione, ad esempio i pool Front End, i pool di server perimetrali, i pool di Persistent Chat o altri che sono definiti come pool nella distribuzione.
    
    Ad esempio:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Per eseguire una ricerca utilizzando parametri temporali

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Per impostazione predefinita, l'ora di inizio dei parametri specifici per il tempo di una ricerca è di 25 minuti prima di cinque minuti dopo la data di avvio della ricerca. In altre parole, se si cerca a 4:00:00 PM, l'ora di inizio della ricerca mostrerà come 3:35:00 PM a 4:05:00 PM. Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, utilizzare il parametro-StartTime e impostare la stringa di data e ora per indicare l'ora in cui si desidera che venga avviata la ricerca. 
    
    Ad esempio, utilizzando-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 9.00 del 11/20/2012 sul pool. È possibile impostare il percorso di output in modo da scrivere i risultati in un file denominato c:\logfile.txt come segue:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La stringa di data e ora specificata può essere "data ora" o "data ora. "Il comando analizzerà la stringa e utilizzerà i valori corretti per la data e l'ora e le impostazioni locali e della lingua nel computer in cui si esegue il cmdlet. 
  
3. Se si desidera recuperare i log a partire da 11:00:00 su 11/20/2012, è possibile definire il-StartTime. L'intervallo di tempo predefinito per la ricerca è di 30 minuti, a meno che non si definisca una specifica-EndTime. La ricerca risultante restituirà i log dal computer o dai pool definiti dalle 11:00:00 alle 11:30:00.
    
Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Per eseguire una ricerca dei log entro un determinato periodo di tempo, definire a-StartTime e an-EndTime. Vengono cercati i log dalle 13.00 alle 14.45 del computer edge01.contoso.net. 
    
Ad esempio:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Per eseguire una ricerca avanzata utilizzando altri criteri e opzioni di corrispondenza

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Per eseguire un comando per raccogliere le tracce di specifici componenti, digitare quanto segue:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Ad esempio:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

Vengono restituite tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e pool della distribuzione negli ultimi 30 minuti.
    
3. Per limitare la ricerca agli stessi componenti solo per il pool Front End denominato pool01.contoso.net, digitare:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. La logica di ricerca predefinita per i comandi che dispongono di più parametri consiste nell'utilizzo dell'operatore logico OR con ogni parametro definito. È possibile modificare questo comportamento specificando il parametro **-MatchAll** . A tal fine, digitare quanto segue:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Se è stata impostata l'esecuzione costante degli scenari, come AlwaysOn, o è stato definito uno scenario di lunga durata, è possibile riportare i log del computer locale nella condivisione file. È possibile definire la condivisione file utilizzando il parametro CacheFileNetworkFolder con New-CsClsConfiguration per creare una nuova configurazione e con Set-CsClsConfiguration per modificarne una esistente. Se non si desidera includere la condivisione file nella raccolta dei log per la ricerca, utilizzare il parametro SkipNetworkLogs come segue:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Leggere i registri di acquisizione dal servizio di registrazione centralizzato

Si rende conto del vantaggio reale del servizio di registrazione centralizzato dopo aver eseguito la ricerca e si dispone di un file che è possibile utilizzare per individuare un problema segnalato. È possibile leggere il file in diversi modi. Il file di output è in formato testo standard ed è possibile utilizzare Notepad.exe o qualsiasi altro programma che consenta l'apertura e la lettura di un file di testo. Per i file più grandi e i problemi più complessi, è possibile utilizzare uno strumento come Snooper.exe che è stato creato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato. Snooper è incluso negli strumenti di debug che sono disponibili come download separato. È possibile scaricare gli strumenti di debug qui: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) . Quando si installano gli strumenti di debug, non vengono creati scorciatoie e voci di menu. Dopo aver installato gli strumenti di debug, aprire Esplora risorse, una finestra della riga di comando o Skype for Business Server Management Shell e passare alla directory (posizione predefinita) C:\Program Skype for Business Server 2015 \ Debugging Tools. Fare doppio clic su Snooper.exe o digitare Snooper.exe, quindi premere INVIO se si utilizza la riga di comando o Skype for Business Server Management Shell.
  
> [!IMPORTANT]
> Lo scopo di questo argomento non è quello di illustrare le tecniche di risoluzione dei problemi. La risoluzione dei problemi e i processi attorno a esso sono un argomento complesso. Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) . I processi e le procedure si applicano ancora a Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Per aprire un file di registro in Snooper

1. Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro. Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi. 
    
2. Dopo l'installazione degli strumenti di debug (LyncDebugTools.msi), cambiare directory nel percorso di Snooper.exe tramite Esplora risorse o dalla riga di comando. Per impostazione predefinita, gli strumenti di debug sono disponibili in C:\Program Skype for Business Server 2015 \ Debugging Tools. Fare doppio clic o eseguire Snooper.exe.
    
3. Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di registro, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.
    
4. I messaggi di **traccia** dei file di registro vengono visualizzati nella scheda **traccia** . Fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.
    
### <a name="to-display-a-call-flow-diagram"></a>Per visualizzare un diagramma del flusso di chiamata

1. Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro. Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.
    
2. Aprire un file di registro e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi oppure selezionare un componente di traccia nella scheda **traccia** .
    
3. Fare clic su **flusso di chiamata**.
    
> [!NOTE]
> Se si fa clic su un messaggio o su una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow". Scegliere un altro messaggio o traccia e il flusso di chiamata verrà visualizzato se il messaggio o la traccia è parte di un flusso di chiamata. 
  
4. Spostarsi tra i messaggi o le righe di traccia e osservare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.
    
5. Posizionare il puntatore del mouse sugli elementi per ottenere informazioni sui messaggi di chiamata, gli endpoint e altri componenti.
