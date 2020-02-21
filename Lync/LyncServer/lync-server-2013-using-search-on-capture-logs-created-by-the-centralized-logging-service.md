---
title: Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d306c17f2c399d38e406d466664a49e3e2df6ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Le funzionalità di ricerca nel servizio di registrazione centralizzato sono utili e potenti per i motivi seguenti:

  - Le ricerche e i risultati vengono eseguiti su un unico computer, un pool, un sito o un ambito globale in base ai criteri definiti.

  - Inizialmente è possibile eseguire ricerche ad ampio spettro e successivamente restringerle adottando criteri più mirati, ad esempio un'ora, un componente o un computer. Le ricerche vengono eseguite negli stessi log e quando i criteri di ricerca cambiano non è necessario effettuare di nuovo una sessione di registrazione.

  - I risultati di ricerca prelevati da tutti i computer e i pool compresi nell'ambito vengono raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca, limitatamente agli scenari eseguiti e ai dati acquisiti. È possibile utilizzare strumenti noti come **Snooper** o **Blocco note** per leggere il file di output e i messaggi di traccia di tutta la distribuzione.

In ogni singolo computer il componente Agente del servizio di registrazione centralizzato (CLSAgent) crea i registri in base allo scenario o agli scenari in esecuzione (è possibile eseguire due scenari per computer in un dato momento). I log e i file di indice e cache associati sono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando di ricerca indica a CLSAgent quali informazioni recuperare. CLSAgent esegue la query nei file di log, cache e indice e restituisce i risultati della ricerca al Controller servizio di registrazione centralizzato (CLSContoller). Quest'ultimo riceve i risultati di ricerca da tutti i computer e pool compresi nell'ambito della ricerca. Quindi aggrega (combina) i log e li ordina in base a un intervallo di tempo, dalla voce meno recente alla più recente.

Al termine di ogni ricerca viene eseguito il cmdlet **Sync-CsClsLogging**, che scarica la cache utilizzata per le ricerche (da non confondere con i file cache gestiti da CLSAgent). Lo scaricamento della cache aiuta a garantire la presenza di un buffer di acquisizione del log e del file di traccia vuoto in CLSController per la successiva operazione di ricerca.

Per ottenere il massimo vantaggio dal servizio di registrazione centralizzato, è necessaria una buona conoscenza di come configurare la ricerca per restituire solo i messaggi di traccia provenienti dai registri del computer e del pool rilevanti per il problema che si sta ricercando. problemi

Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o del controllo di accesso basato sui ruoli di CsServerAdministrator oppure di un ruolo RBAC personalizzato contenente uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Nel resto di questo argomento viene illustrato come definire una ricerca per ottimizzare la risoluzione dei problemi.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base utilizzando il servizio di registrazione centralizzato

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Verificare che nella distribuzione presso l'ambito globale sia in esecuzione lo scenario AlwaysOn e digitare quanto segue al prompt dei comandi:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Per impostazione predefinita, Search-CsClsLogging invia i risultati della ricerca alla console. Se si desidera salvare i risultati della ricerca in un file, utilizzare – OutputFilePath &lt;String fully qualified file path&gt;. Per definire il parametro –OutputFilePath, specificare un percorso e un nome file come parte del parametro in un formato stringa tra virgolette, ad esempio C:\LogFiles\SearchOutput.txt). Nell'esempio fornito è necessario verificare che la directory C:\LogFiles esista e di disporre delle autorizzazioni di lettura e scrittura (autorizzazione NTFS Modifica) dei file nella cartella. L'output viene aggiunto e non sovrascritto. Se sono necessari singoli file, definire un nome di file per ogni ricerca.

    
    </div>
    
    Ad esempio:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Per eseguire una ricerca di base in un pool o in un computer utilizzando il servizio di registrazione centralizzato

1.  Per limitare la ricerca a uno specifico pool o computer, utilizzare il parametro –Computers con il computer definito da un nome completo tra virgolette e separato da una virgola come segue:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Ad esempio:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Per eseguire la ricerca in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, come l'esempio seguente:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Se è necessario eseguire la ricerca in un intero pool, anziché in un singolo computer, modificare il parametro –Computers in –Pools, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separati da virgole.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Quando si utilizzano i comandi di ricerca, i pool possono essere tutti i pool della distribuzione, ad esempio i pool Front End, i pool di server perimetrali, i pool di Persistent Chat o altri che sono definiti come pool nella distribuzione.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>Per eseguire una ricerca utilizzando parametri temporali

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per impostazione predefinita, l'ora di inizio dei parametri di tempo per una ricerca precede di 30 minuti l'ora di avvio della ricerca. In altre parole, se una ricerca viene avviata alle 16.00.00, nei log dei computer e dei pool definiti la ricerca sarà eseguita dalle 15.30.00 alle 16.00.00. Qualora sia necessario effettuare la ricerca 60 minuti o 3 ore prima dell'ora attuale, utilizzare il parametro –StartTime e impostare la stringa di data e ora per indicare l'ora in cui si desidera avviare la ricerca.
    
    Ad esempio, impostando un intervallo di data e ora con i parametri –StartTime ed –EndTime, è possibile definire che nel pool venga effettuata una ricerca tra le 08.00 e le 09.00 del 20 novembre 2012. È possibile impostare il percorso di output in modo che i risultati vengano scritti in un\\file denominato c: logfile. txt, come indicato di seguito:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > La stringa di data e ora specificata può essere "data ora" o "data ora. "Il comando analizzerà la stringa e utilizzerà i valori corretti per la data e l'ora.

    
    </div>

3.  Se si desidera recuperare i log che iniziano alle 11.00.00 del 20 novembre 2012, definire il parametro –StartTime. Se non viene specificato il parametro –EndTime, l'intervallo di tempo predefinito per la ricerca è pari a 30 minuti e vengono pertanto restituiti i log dei computer o pool specificati dalle 11.00.00 alle 11.30.00.
    
    Ad esempio:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Per cercare i log all'interno di uno specifico periodo, definire i parametri –StartTime ed –EndTime. Vengono cercati i log dalle 13.00 alle 14.45 del computer edge01.contoso.net.
    
    Ad esempio:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Per eseguire una ricerca avanzata utilizzando altri criteri e opzioni di corrispondenza

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per eseguire un comando per raccogliere le tracce di specifici componenti, digitare quanto segue:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Ad esempio:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    Vengono restituite tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e pool della distribuzione negli ultimi 30 minuti.

3.  Per limitare la ricerca agli stessi componenti solo per il pool Front End denominato pool01.contoso.net, digitare:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La logica di ricerca predefinita per i comandi che dispongono di più parametri consiste nell'utilizzo dell'operatore logico OR con ogni parametro definito. Questo comportamento può essere modificato specificando il parametro **–MatchAll**. A tal fine, digitare quanto segue:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Se è stata impostata l'esecuzione costante degli scenari, come AlwaysOn, o è stato definito uno scenario di lunga durata, è possibile riportare i log del computer locale nella condivisione file. È possibile definire la condivisione file utilizzando il parametro CacheFileNetworkFolder con New-CsClsConfiguration per creare una nuova configurazione e con Set-CsClsConfiguration per modificarne una esistente. Se non si desidera includere la condivisione file nella raccolta dei log per la ricerca, utilizzare il parametro SkipNetworkLogs come segue:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

