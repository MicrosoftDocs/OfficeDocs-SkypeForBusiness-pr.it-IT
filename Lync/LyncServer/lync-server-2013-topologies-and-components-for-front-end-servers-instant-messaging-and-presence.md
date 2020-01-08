---
title: 'Lync Server 2013: Topologie e componenti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-10-24_

Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:

  - Server front-end dell'organizzazione o server Standard Edition. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server.

  - Un gruppo di bilanciamento del carico, se si ha un pool Enterprise Edition front-end. Per altre informazioni, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Pianificazione per la distribuzione di pool Front-End

In Lync Server 2013 l'architettura del pool Front-End è cambiata e queste modifiche influenzano il modo in cui pianificare e gestire i pool di front-end.

È consigliabile che tutti i pool di front end di Enterprise Edition includano almeno tre server front-end. In Lync Server l'architettura dei pool Front-End usa un modello di sistemi distribuiti, con i dati di ogni utente conservati in tre server front-end nel pool. Per altre informazioni su questa nuova architettura, vedere [modifiche alla topologia in Lync Server 2013](lync-server-2013-topology-changes.md).

Se non si vogliono distribuire tre server front-end Enterprise Edition e si vuole eseguire il ripristino di emergenza, è consigliabile usare Lync Server Standard Edition e creare due pool con una relazione di backup associata. Verrà disponibile una soluzione di ripristino di emergenza con solo due server. Per altre informazioni sulle topologie e sulle caratteristiche di elevata disponibilità e ripristino di emergenza, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Pianificazione per la gestione dei pool Front-End

Per i pool Front-End, seguire le linee guida in questa sezione.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Verificare che i pool siano funzionali

Con il nuovo modello distribuito per i pool Front-End, è necessario che alcuni numeri di server del pool siano in funzione per il pool. Esistono due modalità di perdita per un pool

  - Perdita del quorum a livello di gruppo di routing causata da server di replica non sufficienti per un determinato gruppo di routing. Un gruppo di routing è un'aggregazione di un set di utenti ospitati nel pool. Ogni gruppo di routing include tre repliche nel pool: una primaria e due secondarie.

  - Perdita del quorum a livello di pool, causata quando i server di seeding non sono sufficienti in uso nel pool.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perdita del quorum a livello di gruppo di routing

La prima volta che si avvia un nuovo pool Front-End, è essenziale che il 85% dei server sia installato e in esecuzione, come illustrato nella tabella seguente. Se sono in uso meno server, i servizi potrebbero essere bloccati nello stato iniziale e il pool potrebbe non iniziare.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di server nel pool</th>
<th>Numero di server che devono essere in esecuzione per il pool da avviare per la prima volta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


Ogni volta che il pool viene avviato, è necessario avviare 85% dei server (come illustrato nella tabella precedente). Se non è possibile avviare questo numero di server (ma è possibile avviare abbastanza server in modo che non si sia in perdita di quorum a livello di pool), è possibile usare il cmdlet **Reset-CsPoolRegistrarState-ResetType QuorumLossRecovery** per consentire al pool di recuperare il contenuto del quorum a livello di gruppo di routing ed eseguire lo stato di avanzamento. Per altre informazioni su come usare questo cmdlet, vedere [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Poiché Lync Server usa il database SQL primario come testimone, se si arresta il database principale e si passa alla copia mirror e si arresta un numero sufficiente di server front-end in modo che non sia sufficiente eseguire in base alla tabella precedente, l'intero pool verrà abbasso. Per altre informazioni, Vedi <A href="http://go.microsoft.com/fwlink/?linkid=393672">Witness mirroring del database</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perdita del quorum a livello di pool

Affinché un pool Front-end funzioni affatto, non può essere in perdita di quorum a livello di pool. Se il numero di server in uso scende al di sotto del livello di funzionalità, come illustrato nella tabella seguente, i server rimanenti del pool arrestano tutti i servizi di Lync Server. Tieni presente che i numeri della tabella seguente presuppongono che i server back-end del pool siano in funzione.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di server front-end nel pool</th>
<th>Numero di server che devono essere in uso per il pool per essere funzionali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Qualsiasi 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Qualsiasi 3</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>Qualsiasi 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>Qualsiasi 4 dei primi 7 Server</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>Qualsiasi 5 dei primi 9 server</p></td>
</tr>
</tbody>
</table>


Nella tabella precedente i "primi server" sono i server che sono stati allevati prima, cronologicamente, quando il pool è stato avviato per la prima volta. Per determinare questi server, puoi usare il cmdlet **Get-CsComputer** con l'opzione **– PoolFqdn** . Questo cmdlet visualizzerà i server nell'ordine in cui vengono visualizzati nella topologia e quelli nella parte superiore dell'elenco sono i primi server.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pool Front-end con due server front-end

Non è consigliabile distribuire un pool Front end che contiene solo due server front-end. Se è necessario distribuire un pool di questo tipo, seguire queste linee guida:

  - Se uno dei due server front-end scende, provare a riportare il server non riuscito al più presto possibile. Allo stesso modo, se è necessario aggiornare uno dei due server, riportarlo online non appena l'aggiornamento è terminato.

  - Se per qualche motivo è necessario riportare entrambi i server contemporaneamente, eseguire le operazioni seguenti quando il tempo di inattività per il pool è terminato:
    
      - La procedura consigliata consiste nel riavviare entrambi i server front-end contemporaneamente.
    
      - Se i due server non possono essere riavviati contemporaneamente, è consigliabile riportarli in ordine inverso rispetto all'ordine in cui sono stati ritirati.
    
      - Se non è possibile riportarli in questo ordine, usare il cmdlet seguente prima di riportare il pool:.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Passaggi aggiuntivi per garantire la funzionalità dei pool

Per assicurarsi che i pool Front-End rimangano funzionali, è necessario guardare un paio di altri fattori.

  - Quando si trasferiscono gli utenti al pool per la prima volta, assicurarsi che siano in esecuzione almeno tre server front-end.

  - Se si stabilisce una relazione di associazione tra questo pool e un altro pool per scopi di ripristino di emergenza, dopo aver stabilito tale relazione, è necessario assicurarsi che il pool abbia tre server front-end in esecuzione contemporaneamente in modo da sincronizzare correttamente dati con il pool di backup. Per altre informazioni sulle funzionalità di associazione e ripristino di emergenza del pool, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Migliorare l'affidabilità degli aggiornamenti del pool

Quando è necessario aggiornare o patchare i server in un pool Front-End, seguire il flusso di lavoro mostrato in [aggiornare o aggiornare i server front-end in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e le linee guida seguenti:

  - Quando si passa da un dominio di aggiornamento a un altro per gli aggiornamenti (seguire il flusso di lavoro all' [aggiornamento o aggiornare i server front-end in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), si utilizzerà il cmdlet **Get-CsPoolUpgradeReadinessState** e si verifica lo stato pronto. L'aggiunta di un'attesa di 20 minuti tra ogni dominio di aggiornamento dopo il raggiungimento di "pronto" rende più affidabili gli aggiornamenti. Se non viene **ancora pronta** durante i 20 minuti, riavviare il timer di 20 minuti. Puoi anche eseguire il cmdlet **Get-CsPoolFabricState** prima e dopo aver avviato l'intervallo di 20 minuti e verificare che non ci siano modifiche alle primarie e alle secondarie dei gruppi di routing.

  - Non passare al dominio di aggiornamento successivo se uno dei server nell'ultimo dominio di aggiornamento con patch è bloccato o non viene riavviato. Questa operazione si applica anche se non è possibile avviare uno dei server all'interno di un aggiornamento. Eseguire **Get-CsPoolFabricState** per assicurarsi che tutti i gruppi di routing abbiano un primario e almeno uno secondario; Ciò consentirà di verificare se tutti gli utenti hanno un servizio.

  - Se alcuni utenti hanno un servizio e altri no, eseguire **Get-CsPoolFabricState** con l'opzione – verbose per verificare la presenza di gruppi di routing che contengono repliche mancanti. Non riavviare l'intero pool come primo passaggio di risoluzione dei problemi. Per altre informazioni su questo cmdlet, vedere [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Assicurarsi che tutte le istanze del Visualizzatore eventi o delle finestre di monitoraggio delle prestazioni siano chiuse per le installazioni/disinstallazioni in tessuto Windows.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Modifica della configurazione di un pool Front-End

Ogni volta che si aggiungono server front-end a un pool o li si rimuove dal pool e quindi si pubblica la nuova topologia, seguire queste linee guida:

  - Dopo la pubblicazione della nuova topologia, è necessario riavviare ogni server front-end nel pool. Riavviare uno alla volta.

  - Se l'intero pool è stato premuto durante la modifica della configurazione, eseguire il cmdlet seguente dopo la pubblicazione della nuova topologia:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Se un server front-end non riesce ed è improbabile che venga sostituito per alcuni giorni o più, rimuovere il server dalla topologia. Aggiungere il nuovo server front-end alla topologia quando è di nuovo disponibile.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

