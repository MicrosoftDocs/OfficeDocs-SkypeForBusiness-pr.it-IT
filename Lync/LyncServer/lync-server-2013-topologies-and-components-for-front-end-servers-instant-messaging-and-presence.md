---
title: 'Lync Server 2013: topologie e componenti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503753"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-10-24_

Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:

  - I Front End Server o i server Standard Edition dell'organizzazione. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server.

  - Un bilanciamento del carico, se si dispone di un pool Enterprise Edition front end. Per ulteriori informazioni, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Pianificazione per la distribuzione di pool Front End

In Lync Server 2013, l'architettura del pool Front End è cambiata e queste modifiche influiscono su come pianificare e gestire i pool Front end.

È consigliabile che tutti i pool Enterprise Edition front end includano almeno tre Front End Server. In Lync Server, l'architettura dei pool Front end utilizza un modello di sistemi distribuiti, con i dati di ogni utente conservati su tre Front End Server nel pool. Per ulteriori informazioni su questa nuova architettura, vedere [modifiche alla topologia in Lync Server 2013](lync-server-2013-topology-changes.md).

Se non si desidera distribuire tre Front End Server Enterprise Edition e si desidera eseguire il ripristino di emergenza, è consigliabile utilizzare Lync Server Standard Edition e creare due pool con una relazione di backup associata. In questo modo verrà fornita una soluzione di ripristino di emergenza con solo due server. Per ulteriori informazioni sulle topologie e le funzionalità di disponibilità elevata e ripristino di emergenza, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Pianificazione per la gestione di pool Front End

Per i pool Front End, seguire le linee guida riportate in questa sezione.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Garantire che i pool siano funzionali

Con il nuovo modello distribuito per i pool Front End, è necessario che alcuni numeri dei server di un pool siano in esecuzione affinché il pool funzioni. Sono disponibili due modalità di perdita per un pool

  - Perdita di quorum a livello di gruppo di routing, causata da server di replica non sufficienti per un gruppo di routing specifico. Un gruppo di routing è un'aggregazione di un insieme di utenti ospitati nel pool. Ogni gruppo di routing ha tre repliche nel pool: una principale e due secondarie.

  - Perdita di quorum a livello di pool, causata quando i server di seeding non sono sufficienti in esecuzione nel pool.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perdita di quorum a livello di gruppo di routing

La prima volta che si avvia un nuovo pool Front End, è essenziale che il 85% dei server sia attivo e in esecuzione, come illustrato nella tabella seguente. Se sono in esecuzione meno server, è possibile che i servizi siano bloccati nello stato iniziale e che il pool non venga avviato.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di server nel pool</th>
<th>Numero di server che devono essere in esecuzione per l'avvio del pool per la prima volta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10  </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10  </p></td>
</tr>
</tbody>
</table>


Ogni volta che viene avviato il pool, 85% dei server devono essere avviati (come illustrato nella tabella precedente). Se non è possibile avviare questo numero di server, ma è possibile avviare server sufficienti in modo che non si trovino perdite di quorum a livello di pool, è possibile utilizzare il cmdlet **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** per consentire al pool di eseguire il ripristino dalla perdita del quorum a livello di gruppo di routing e progredire. Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Poiché Lync Server utilizza il database SQL primario come server di controllo, se si arresta il database primario e si passa alla copia del mirror e si arresta un numero sufficiente di front end server in modo che non sia sufficiente eseguire in base alla tabella precedente, l'intero pool passerà. Per ulteriori informazioni, vedere <A href="https://go.microsoft.com/fwlink/?linkid=393672">database mirroring witness</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perdita di quorum a livello di pool

Affinché un pool Front end funzioni a tutti, non può essere in perdita di quorum a livello di pool. Se il numero di server in esecuzione scende al di sotto del livello di funzionalità, come illustrato nella tabella seguente, i server rimanenti del pool interromperanno tutti i servizi di Lync Server. Si noti che i numeri nella tabella seguente presuppongono che i server back-end del pool siano in esecuzione.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di Front End Server nel pool</th>
<th>Numero minimo di server attivi per il funzionamento del pool</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1 </p></td>
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
<td><p>7 </p></td>
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


Nella tabella precedente, i "First Server" sono i server che sono stati portati in primo luogo, in ordine cronologico, quando il pool è stato avviato per la prima volta. Per determinare questi server, è possibile utilizzare il cmdlet **Get-CsComputer** con l'opzione **– PoolFqdn** . Questo cmdlet mostrerà i server nell'ordine in cui vengono visualizzati nella topologia e quelli nella parte superiore dell'elenco sono i primi server.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pool Front End con due Front End Server

Non è consigliabile distribuire un pool Front End contenente due soli Front End Server. Se fosse necessario distribuire questo tipo di pool, seguire queste indicazioni:

  - Se uno dei due Front End Server si arresta, riattivarlo al più presto. Analogamente, se occorre aggiornare uno dei due server, riportarlo online subito dopo l'aggiornamento.

  - Se per qualche ragione si rende necessario arrestare entrambi i server contemporaneamente, al termine dell'intervento procedere come segue:
    
      - La procedura consigliata consiste nel riavviare entrambi i front end server contemporaneamente.
    
      - Se non è possibile riavviare entrambi i server contemporaneamente, riattivarli in ordine inverso rispetto a quello di arresto.
    
      - Se non è possibile riattivarli nell'ordine consigliato, prima di riattivare il pool, utilizzare il cmdlet seguente:
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Passaggi aggiuntivi per garantire che i pool siano funzionali

È consigliabile guardare un paio di altri fattori per garantire che i pool Front End rimangano funzionali.

  - Quando si spostano gli utenti nel pool per la prima volta, assicurarsi che siano in esecuzione almeno tre Front End Server.

  - Se si stabilisce una relazione di abbinamento tra questo pool e un altro pool ai fini del ripristino di emergenza, dopo aver stabilito la relazione è necessario verificare che in un determinato momento questo pool disponga di tre Front End Server in esecuzione simultanea per sincronizzare correttamente i dati con il pool di backup. Per ulteriori informazioni sulle funzionalità di abbinamento dei pool e ripristino di emergenza, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Migliorare l'affidabilità degli aggiornamenti del pool

Quando è necessario aggiornare o applicare la patch ai server in un pool Front End, seguire il flusso di lavoro mostrato in [upgrade or Update Front End Servers in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e le linee guida seguenti:

  - Quando si passa da un dominio di aggiornamento a un altro per gli aggiornamenti (dopo il flusso di lavoro in fase di [aggiornamento o aggiornamento dei front end server in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), si utilizzerà il cmdlet **Get-CsPoolUpgradeReadinessState** e si verificherà lo stato pronto. L'aggiunta di un'attesa di 20 minuti tra ogni dominio di aggiornamento dopo che raggiunge "Ready" renderà gli aggiornamenti più affidabili. Se non si è **pronti** durante questo periodo di 20 minuti, riavviare il timer di 20 minuti. È inoltre possibile eseguire il cmdlet **Get-CsPoolFabricState** prima e dopo l'avvio dell'intervallo di 20 minuti e verificare che non siano presenti modifiche alle primarie e alle secondarie dei gruppi di routing.

  - Non passare al dominio di aggiornamento successivo se uno qualsiasi dei server nell'ultimo dominio di aggiornamento con patch è bloccato o non riavviato. Questo si applica anche se non è possibile avviare uno dei server all'interno di un aggiornamento. Eseguire **Get-CsPoolFabricState** per verificare che tutti i gruppi di routing abbiano un primario e almeno un secondario; Ciò consentirà di verificare se tutti gli utenti dispongono di un servizio.

  - Se alcuni utenti dispongono di un servizio e altri non lo fanno, eseguire **Get-CsPoolFabricState** con l'opzione – verbose per controllare i gruppi di routing che dispongono di repliche mancanti. Non riavviare l'intero pool come primo passaggio di risoluzione dei problemi. Per ulteriori informazioni su questo cmdlet, vedere [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Assicurarsi che tutte le istanze del Visualizzatore eventi o delle finestre di monitoraggio delle prestazioni siano chiuse per le installazioni/disinstallazioni di Windows Fabric.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Modifica della configurazione di un pool Front End

Quando si aggiungono o si rimuovono Front End Server da un pool e quindi si pubblica la nuova topologia, seguire queste linee guida:

  - Dopo la pubblicazione della nuova topologia, è necessario riavviare ogni Front End Server nel pool. Riavviarli uno alla volta.

  - Se durante le modifiche della configurazione è stato arrestato l'intero pool, dopo la pubblicazione della topologia eseguire il cmdlet seguente:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Se un Front End Server si guasta e si prevede che non verrà sostituito entro pochi giorni, rimuovere il server dalla topologia. Aggiungere il nuovo Front End Server alla topologia quando sarà disponibile.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

