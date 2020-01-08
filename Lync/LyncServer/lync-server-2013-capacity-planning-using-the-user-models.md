---
title: Pianificazione della capacità di Lync Server 2013 con i modelli utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Pianificazione della capacità per Lync Server 2013 con i modelli utente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-14_

In questa sezione vengono fornite indicazioni su quanti server sono necessari in un sito per il numero di utenti in tale sito, in base all'uso descritto nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

Tutti i risultati delle prestazioni e i suggerimenti per la distribuzione in questa sezione sono basati sul test delle prestazioni nei server che usano l'hardware descritto nella tabella seguente. Ti consigliamo di usare hardware simile. Se usi hardware meno potente, potresti riscontrare problemi di funzionalità o prestazioni scarse. Tieni presente che queste raccomandazioni hardware sono superiori a quelle delle versioni precedenti di Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Hardware usato nei test delle prestazioni

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore</p>
<p>I processori Intel Itanium non sono supportati per i ruoli di Lync Server Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o più unità disco rigido di 10.000-RPM con almeno 72 GB di spazio libero su disco.</p>
<p>Due dischi dovrebbero usare RAID 1 e sei dovrebbero usare RAID 10.</p>
<p>-O</p></li>
<li><p>SSD (Solid State Drive) che garantiscono prestazioni simili alle unità disco meccaniche di 8 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Riepilogo dei risultati

Nella tabella seguente vengono riepilogati questi suggerimenti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo del server</th>
<th>Numero massimo di utenti supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool Front end con dodici server front-end e un server back-end o una coppia speculare di server back-end.</p></td>
<td><p>80.000 utenti univoci collegati contemporaneamente, più 50% più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 152.000 endpoint.</p></td>
</tr>
<tr class="even">
<td><p>Servizi di conferenza A/V</p></td>
<td><p>Il servizio di conferenza A/V fornito da un pool di front-end supporta le conferenze del pool che presuppongono una dimensione massima per la conferenza di 250 utenti e una sola Conferenza di grandi dimensioni in esecuzione alla volta.</p>
<div>

> [!NOTE]  
> È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front-end separato con due server front-end per ospitare le conferenze di grandi dimensioni. Per informazioni dettagliate, vedere <A href="lync-server-2013-supporting-large-meetings.md">supporto di riunioni di grandi dimensioni tramite Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un server perimetrale</p></td>
<td><p>12.000 utenti remoti simultanei</p></td>
</tr>
<tr class="even">
<td><p>Un amministratore</p></td>
<td><p>12.000 utenti remoti simultanei</p></td>
</tr>
<tr class="odd">
<td><p>Monitoraggio e archiviazione</p></td>
<td><p>In Lync Server 2013 i servizi front end di monitoraggio e archiviazione vengono ora eseguiti in ogni server front-end, anziché in ruoli server distinti.</p>
<p>Il monitoraggio e l'archiviazione di ognuno richiede ancora i propri archivi di database. Se si esegue anche Exchange 2013, è possibile conservare i dati di archiviazione in Exchange, anziché in un database SQL dedicato.</p></td>
</tr>
<tr class="even">
<td><p>Un Mediation Server</p></td>
<td><p>Mediation Server collocato con Front End Server viene eseguito in tutti i server front-end di un pool e dovrebbe avere sufficiente capacità per gli utenti nel pool. Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.</p></td>
</tr>
<tr class="odd">
<td><p>Un server Standard Edition</p></td>
<td><p>Se si usano Server Standard Edition per ospitare gli utenti, è consigliabile usare sempre due server, abbinati con i suggerimenti <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">per la pianificazione della disponibilità elevata e il ripristino di emergenza in Lync Server 2013</a>. Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server non riesce, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.</p>
<p>Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono avere più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere più server Standard Edition o passare a Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Server front-end

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

In un pool Front-End è necessario disporre di un server front-end per ogni utente di 6.660 ospitato nel pool, presupponendo che l'Hyper-Threading sia abilitato in tutti i server del pool e che l'hardware del server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md). Il numero massimo di utenti in un pool Front-End è 80.000, presupponendo che l'Hyper-Threading sia abilitato in tutti i server del pool. Se si hanno più di 80.000 utenti in un sito, è possibile distribuire più di un pool Front-end.

Quando si tiene conto del numero di utenti in un pool Front-End, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a questo pool Front-end.

Quando un server attivo non è disponibile, le connessioni vengono trasferite automaticamente agli altri server del pool. Ad esempio, se si hanno 30.000 utenti e cinque server front-end, se un server non è disponibile, le connessioni degli utenti di 6000 devono essere trasferite agli altri quattro server. I quattro server rimanenti avranno tutti gli utenti di 7500, che è un numero più grande di quello raccomandato.

Se invece si è iniziato con sei server front-end per gli utenti di 30.000 e in seguito non è più disponibile, per un totale di 5000 gli utenti verranno spostati nei cinque server rimanenti. Questi cinque server conterranno tutti gli utenti di 6000, che si trova nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front-End è 80.000. Il numero massimo di server front-end in un pool è 12.

Per un pool Front-end con gli utenti di 80.000, dodici server front-end sono sufficienti per le prestazioni, in distribuzioni tipiche che seguono i [modelli utente in Lync Server 2013](lync-server-2013-user-models.md). Le distribuzioni progettate per supportare il failover del ripristino di emergenza presuppongono che un massimo di 40.000 utenti possano essere ospitati in ognuno dei due pool Front-End associati, in cui ogni pool ha sufficienti server front-end per ospitare gli utenti in entrambi i pool in caso di necessità di un pool non riuscito verso l'altro.

Il numero di utenti supportati con prestazioni ottimali per un determinato pool Front-end può essere diverso da questi numeri per i motivi seguenti:

  - L'hardware per i server front-end non soddisfa le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

  - L'utilizzo dell'organizzazione differisce in modo significativo dai modelli utente, ad esempio il traffico di conferenze più significativo.

<div>


> [!IMPORTANT]  
> In Lync Server 2013 i database di presenza sono ora ospitati nei server front-end, a differenza di Lync Server 2010 in cui erano ospitati nel server back-end. Ciò significa che le prestazioni del disco e la capacità dei server front-end non devono essere compromesse dalle raccomandazioni elencate in precedenza in questa sezione e nelle <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware del server per Lync server 2013</A>, indipendentemente dal numero di utenti ospitati dai server front-end.



</div>

La tabella seguente mostra la larghezza di banda media per la messaggistica istantanea e la presenza, dato il modello utente, come definito nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Larghezza di banda media per utente</th>
<th>Requisiti di larghezza di banda per server front-end con utenti di 6.660</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Per migliorare le prestazioni multimediali della funzionalità di conferenza A/V Conferencing e Mediation Server co-ubicata nei server front-end, è necessario abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei server front-end. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo. Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Massimali per le conferenze

Considerato il modello utente in cui il 5% degli utenti di un pool può partecipare a una conferenza in qualsiasi momento, un pool di utenti di 80.000 potrebbe avere circa 4.000 utenti in una sola volta. Queste conferenze dovrebbero essere una combinazione di elementi multimediali (alcuni messaggi istantanei, alcuni messaggi istantanei con audio, alcuni audio/video, ad esempio) e il numero di partecipanti. Non esiste alcun limite per il numero effettivo di conferenze consentite e l'utilizzo effettivo determina le prestazioni effettive. Ad esempio, se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end o A/V Conferencing Server rispetto ai suggerimenti di questo documento. Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

La dimensione massima della conferenza supportata ospitata da un normale pool di front end di Lync Server 2013 che ospita anche utenti è di 250 partecipanti. Mentre è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che un totale del 5% degli utenti del pool si trovi in conferenze simultanee. Ad esempio, in un pool di dodici server front-end e utenti di 80.000, mentre la conferenza per utenti di 250 sta accadendo, Lync Server supporta 3.750 altri utenti che partecipano a conferenze più piccole.

Indipendentemente dal numero di utenti ospitati nel pool Front-end o in un server Standard Edition, Lync Server supporta un minimo di 125 di altri utenti che partecipano a conferenze più piccole nello stesso pool o server in cui è in uso una conferenza di 250 utenti.

Per abilitare le conferenze tra gli utenti di 250 e 1000, è possibile configurare un pool Front-end separato solo per ospitare tali conferenze. Questo pool Front-end non ospiterà alcun utente. Per informazioni dettagliate, vedere [supporto di riunioni di grandi dimensioni tramite Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Se l'organizzazione ha molte più conferenze in modalità mista rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più server front-end rispetto alle raccomandazioni del documento (fino a un massimo di 12 FEs). Per informazioni dettagliate sulle ipotesi nel modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Edge Server

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

Devi distribuire un server perimetrale per ogni utente remoto di 12.000 che accede simultaneamente a un sito. È consigliabile almeno due server Edge per una disponibilità elevata. Queste raccomandazioni presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Quando si tiene conto del numero di utenti per gli Edge Server, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.

<div>


> [!NOTE]  
> Per migliorare le prestazioni del servizio A/V Conferencing Edge in un server perimetrale, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete degli Edge Server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo. Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

Se si distribuisce il ruolo Director Server, è consigliabile distribuire un amministratore per ogni utente remoto di 12.000 che accede contemporaneamente a un sito. Consigliamo almeno due direttori per una disponibilità elevata. Queste raccomandazioni presuppongono che l'hardware per gli Edge Server soddisfi le raccomandazioni nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Quando si tiene conto del numero di utenti per gli amministratori, includere gli utenti ospitati in Survivable Branch Appliances e Survivable Branch Server presso succursali associate a un pool Front-end in questo sito.

</div>

<div>

## <a name="mediation-server"></a>Mediation Server

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i server front-end del pool e deve avere sufficiente capacità per gli utenti del pool.

Se si distribuisce un pool di Mediation Server autonomo, il numero di server di mediazione da distribuire dipende da molti fattori, tra cui l'hardware usato per Mediation Server, il numero di utenti VoIP che si ha, la quantità di peer del gateway che ogni pool di Mediation Server controlli, il traffico ora occupato attraverso i gateway e la percentuale di chiamate con elementi multimediali che ignorano il Mediation Server.

Le tabelle seguenti includono una linea guida per il numero di chiamate simultanee che possono essere gestite da un Mediation Server, presupponendo che l'hardware per i server di mediazione soddisfi i requisiti delle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) e che l'Hyper-Threading sia abilitato. Per informazioni dettagliate sulla scalabilità di Mediation Server, vedere [stima dell'uso delle voci e del traffico per Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Tutte le tabelle seguenti presuppongono l'utilizzo come riepilogato nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacità di mediazione del server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non bypass (transcodifica multimediale eseguita da Mediation Server)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware del server</th>
<th>Numero massimo di chiamate</th>
<th>Numero massimo di righe T1</th>
<th>Numero massimo di righe E1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processore duale, hex core, CPU Hyper-Threading a 2,26 GHz <strong>con Hyper-Threading disabilitato</strong>, con memoria di 32 GB e una scheda di rete a doppia porta.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Processore dual, hex core, CPU Hyper-Threaded da 2,26 GHz, con memoria 32 GB e una scheda di rete a doppia porta.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Anche se i server con 32 GB di memoria sono stati usati per il test delle prestazioni, i server con 16 GB di memoria sono supportati per Mediation Server autonomo e sono sufficienti per dare le prestazioni illustrate in questa tabella.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacità Mediation Server (Mediation Server con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non bypass (elaborazione multimediale eseguita da Mediation Server)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware del server</th>
<th>Numero massimo di chiamate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processore duale, hex core, CPU Hyper-Threaded da 2,26 GHz, con memoria di 32 GB e schede di rete da 2 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Questo numero è molto più piccolo dei numeri per il server di mediazione autonomo perché il server front-end deve gestire altre funzionalità e funzioni per gli utenti di 6600 ospitati, oltre alla transcodifica necessaria per le chiamate vocali.



</div>

<div>


> [!NOTE]  
> Per migliorare le prestazioni del Mediation Server, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete dei media server. RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server. Per informazioni dettagliate, vedere "miglioramenti della scala sul lato ricezione in Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>all'indirizzo. Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.



</div>

</div>

<div>

## <a name="back-end-server"></a>Server back-end

In Lync Server 2013 i database di presenza si trovano nei server front-end anziché nel server back-end. Ciò ha comportato un requisito molto più semplice per ogni server back-end in Lync Server 2013, equivalente al requisito hardware per il server front-end. In confronto a Lync Server 2010, in cui è necessario che il server back-end sia un server di qualità molto più elevato con 25 dischi. Tuttavia, il carico di lavoro dei server back-end è ancora tale che non è necessario soddisfare le raccomandazioni hardware elencate in precedenza in questa sezione e nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Per ottenere una disponibilità elevata del server back-end, è consigliabile distribuire il mirroring del server. Per altre informazioni, vedere [back-end server high availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

In Lync Server 2013, se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei server front-end, anziché in ruoli server distinti. Il monitoraggio e l'archiviazione di ogni nuovo uso di un proprio archivio database, separato dallo Store back-end. In alternativa, se è stato distribuito Exchange 2013, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

La tabella seguente indica approssimativamente la quantità di spazio di archiviazione del database necessaria per ogni utente per giorno per il monitoraggio e l'archiviazione dei dati.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (monitoraggio)</strong></p></td>
<td><p><strong>QoE (monitoraggio)</strong></p></td>
<td><p><strong>Archiviazione</strong></p></td>
</tr>
<tr class="even">
<td><p>Spazio su disco richiesto per ogni utente per giorno</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft ha usato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il test delle prestazioni. Il test ha raccolto i dati di due pool Front-End, ognuno dei quali conteneva gli utenti di 80.000.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware usato per il monitoraggio e l'archiviazione del test delle prestazioni

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente hardware</th>
<th>Consigliato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>48 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><p>25 10.000-RPM unità disco rigido con 300 GB su ogni disco, con la configurazione seguente</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Unità</strong></p></td>
<td><p><strong>Configurazione RAID</strong></p></td>
<td><p><strong>Numero di dischi</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR, QoE e archiviazione dei file di dati del database in un'unica unità</p></td>
<td><p>1 + 0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>File di log del database CDR</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>File di log del database QoE</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>File di log del database di archiviazione</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>1 scheda di rete a doppia porta, 1 Gbps o superiore (2 consigliata, che richiede il teaming con un singolo indirizzo MAC e un singolo indirizzo IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Stima dell'utilizzo e del traffico vocale Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

