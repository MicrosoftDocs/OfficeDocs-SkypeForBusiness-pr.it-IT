---
title: Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47b9d11713e874915fac0e4b67099ce3f7456546
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Le funzionalità di ricerca nel servizio di registrazione centralizzata sono utili e potenti per i motivi seguenti:

  - Le ricerche e i risultati vengono eseguiti in un singolo computer, un pool, un sito o un ambito globale, in base ai criteri definiti.

  - Le ricerche possono essere inizialmente ampie e quindi limitate a criteri più mirati, ad esempio ora, componente o computer. Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.

  - I risultati della ricerca vengono raccolti da tutti i computer e i pool nell'ambito, raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca (limitati agli scenari in uso e ai dati acquisiti dall' scenari). Si usano strumenti noti come **Snooper** o **notepad** per leggere il file di output e i messaggi di analisi provenienti da tutta la distribuzione.

Il CLSAgent in ogni singolo computer crea i registri in base allo scenario o agli scenari (due scenari per ogni computer possono essere eseguiti in qualsiasi momento). I log e i file di indice e cache associati vengono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando Cerca indica a CLSAgent le informazioni che devono essere recuperate. CLSAgent esegue la query in base ai file di log, ai file di cache e ai file di indice e restituisce i risultati della ricerca al CLSContoller. CLSController riceve i risultati della ricerca da tutti i computer e i pool nell'ambito della ricerca. Il CLSController quindi aggrega i registri e li inserisce nell'ordine di Delta temporale, la prima voce più antica e procede in tempo fino all'ultima voce più recente.

Dopo ogni ricerca, il cmdlet **Sync-CsClsLogging** viene eseguito e svuota la cache usata dalle ricerche (da non confondere con i file di cache gestiti da CLSAgent). La cancellazione della cache consente di verificare che il buffer di acquisizione di file e traccia puliti sia pulito in CLSController per la successiva operazione di ricerca.

Per trarre il massimo vantaggio dal servizio di registrazione centralizzato, è necessario avere una buona conoscenza della configurazione della ricerca per restituire solo i messaggi di traccia dal computer e i registri del pool rilevanti per il problema che si sta ricercando. problemi

Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Il resto di questo argomento illustra come definire una ricerca per ottimizzare la risoluzione dei problemi.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base tramite il servizio di registrazione centralizzato

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Verificare di avere lo scenario AlwaysOn in uso nella distribuzione in ambito globale e quindi digitare quanto segue al prompt dei comandi:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Per impostazione predefinita, la ricerca-CsClsLogging invia i risultati della ricerca alla console. Se si vogliono salvare i risultati della ricerca in un file, usare il percorso &lt;&gt;di file completo della stringa outputFilePath. Per definire il parametro – OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette (ad esempio; C:\LogFiles\SearchOutput.txt). In questo esempio, devi assicurarti che la directory C:\LogFiles esista e che tu abbia le autorizzazioni per la lettura e la scrittura dei file (autorizzazione NTFS Modify) nella cartella. L'output viene accodato e non viene sovrascritto. Se hai bisogno di file separati, definisci un nome di file distinto per ogni ricerca.

    
    </div>
    
    Ad esempio:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base in un pool o un computer usando il servizio di registrazione centralizzato

1.  Per limitare la ricerca a un pool o un computer specifico, usare il parametro – computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Ad esempio:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Per eseguire ricerche in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, ad esempio i seguenti:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Se è necessario eseguire la ricerca in un intero pool anziché in un singolo computer, modificare il parametro-computer in-pools, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separate da virgole.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Quando si usano i comandi di ricerca, i pool possono essere qualsiasi pool nella distribuzione, ad esempio pool Front-End, pool di bordi, pool di server di chat permanenti o altri che sono definiti come pool nella distribuzione.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>Per eseguire una ricerca usando i parametri di ora

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per impostazione predefinita, l'ora di inizio per i parametri specifici del tempo di una ricerca è di 30 minuti prima della data di avvio della ricerca. In altre parole, se si avvia la ricerca alle 4:00:00 PM, la ricerca cercherà i registri per i computer e i pool definiti dalle 3:30:00 alle 4:00:00 PM. Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, usare il parametro – StartTime e impostare la stringa di data e ora per indicare l'ora in cui si vuole che venga avviata la ricerca.
    
    Usando, ad esempio,-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 09:00 in 11/20/2012 nel pool. È possibile impostare il percorso di output per scrivere i risultati in un file denominato c\\: logfile. txt come indicato di seguito:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > La stringa di data e ora specificata può essere "data/ora" o "data di scadenza". "Il comando analizzerà la stringa e utilizzerà i valori appropriati per la data e l'ora.

    
    </div>

3.  Se si vogliono recuperare i log a partire da 11:00:00 AM su 11/20/2012, è necessario definire il-StartTime. L'intervallo di tempo predefinito per la ricerca è di 30 minuti a meno che non si definisca uno specifico-EndTime. La ricerca risultante restituirà i log dal computer o dai pool definiti da 11:00:00 AM a 11:30:00 AM.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Per eseguire una ricerca di log in un determinato periodo di tempo, definire a-StartTime e an-EndTime. È necessario eseguire il log dalle 1 PM alle 2:45 PM nel computer edge01.contoso.net.
    
    Ad esempio:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Per eseguire una ricerca avanzata usando altri criteri e le opzioni di corrispondenza

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per eseguire un comando per raccogliere tracce per componenti specifici, digitare quanto segue:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Ad esempio:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    La ricerca risultante restituisce tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e i pool della distribuzione per i 30 minuti scorsi.

3.  Per limitare la ricerca con gli stessi componenti solo al pool Front-End denominato pool01.contoso.net, digitare:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La logica di ricerca predefinita per i comandi con più parametri consiste nell'usare il valore logico o con ognuno dei parametri definiti. Puoi modificare questo comportamento specificando il parametro **– MatchAll** . A tale scopo, digitare quanto segue:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Se gli scenari sono impostati per l'esecuzione costante, ad esempio AlwaysOn, oppure è stato definito un log dello scenario a esecuzione prolungata, è possibile che il computer locale venga disattivato nella condivisione file. Puoi definire la condivisione di file usando il parametro CacheFileNetworkFolder usando New-CsClsConfiguration per creare una nuova configurazione o modificare una configurazione esistente con Set-CsClsConfiguration. Se non si vuole che la ricerca includa la condivisione file nella raccolta di log in cui eseguire la ricerca, usare il parametro SkipNetworkLogs nel modo seguente:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

