---
title: Lync Server 2013 Capacity Planning using the user Models
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Pianificazione della capacità per Lync Server 2013 con i modelli utente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-14_

In questa sezione vengono fornite informazioni su quanti server sono necessari in un sito per il numero di utenti di tale sito, in base all'utilizzo descritto in [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Piattaforma hardware testata

Tutti i risultati delle prestazioni e i suggerimenti relativi alla distribuzione in questa sezione si basano sui test delle prestazioni nei server che eseguono l'hardware descritto nella tabella seguente. È consigliabile utilizzare hardware analogo. Se si utilizzano componenti hardware meno potenti, è possibile che si verifichino problemi funzionali o di prestazioni insufficienti. Si noti che questi suggerimenti per l'hardware sono più alti rispetto a quelli delle versioni precedenti di Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Hardware utilizzato nei test delle prestazioni

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
<td><p>Processore doppio a 64 bit, hex core, 2,26 GHz o superiore</p>
<p>I processori Intel Itanium non sono supportati per i ruoli del server di Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.</p>
<p>Due dei dischi dovrebbero utilizzare RAID 1 e sei dovrebbero utilizzare RAID 10.</p>
<p>-O</p></li>
<li><p>Unità SSD (Solid State Drive) con prestazioni simili a otto unità disco meccanico da 10.000 RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Riepilogo dei risultati

Nella tabella riportata di seguito vengono riepilogate queste indicazioni.


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
<td><p>Pool Front end con dodici front end server e un server back-end o una coppia con mirroring dei server back-end.</p></td>
<td><p>80.000 utenti univoci connessi contemporaneamente, oltre al 50% di più punti di presenza (MPOP) che rappresentano istanze non mobili, oltre al 40% degli utenti abilitati per la mobilità per un totale di 152.000 endpoint.</p></td>
</tr>
<tr class="even">
<td><p>A/V Conferencing</p></td>
<td><p>Il servizio A/V Conferencing fornito da un pool Front end supporta le conferenze del pool assumendo una dimensione massima per le conferenze di 250 utenti e solo una conferenza di questo tipo è in esecuzione alla volta.</p>
<div>

> [!NOTE]  
> È inoltre possibile supportare conferenze di grandi dimensioni tra gli utenti di 250 e 1000 distribuendo un pool Front end separato con due front end server per ospitare le conferenze di grandi dimensioni. Per informazioni dettagliate, vedere <A href="lync-server-2013-supporting-large-meetings.md">supporto di riunioni di grandi dimensioni con Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un server perimetrale</p></td>
<td><p>12.000 utenti remoti simultanei</p></td>
</tr>
<tr class="even">
<td><p>Un Director</p></td>
<td><p>12.000 utenti remoti simultanei</p></td>
</tr>
<tr class="odd">
<td><p>Monitoraggio e archiviazione</p></td>
<td><p>In Lync Server 2013, i servizi front end di monitoraggio e archiviazione ora vengono eseguiti su ogni Front End Server, anziché su ruoli server distinti.</p>
<p>Monitoring and Archiving each richiedono ancora i propri archivi di database. Se si esegue anche Exchange 2013, è possibile mantenere i dati di archiviazione in Exchange anziché in un database SQL dedicato.</p></td>
</tr>
<tr class="even">
<td><p>Un Mediation Server</p></td>
<td><p>Mediation Server collocato con Front End Server viene eseguito in tutti i front end server in un pool e deve fornire capacità sufficiente per gli utenti nel pool. Per Mediation Server autonomo, vedere la sezione "Mediation Server" più avanti in questo argomento.</p></td>
</tr>
<tr class="odd">
<td><p>Un server Standard Edition</p></td>
<td><p>Se si utilizzano i server Standard Edition per ospitare gli utenti, è consigliabile utilizzare sempre due server, abbinati con i suggerimenti per la <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">pianificazione della disponibilità elevata e del ripristino di emergenza in Lync Server 2013</a>. Ogni server della coppia può ospitare fino a 2.500 utenti e, se un server ha esito negativo, il server rimanente può supportare gli utenti di 5.000 in uno scenario di failover.</p>
<p>Se la distribuzione include una quantità significativa di traffico audio o video, le prestazioni del server possono subire più di 2.500 utenti per server. In questo caso, è consigliabile aggiungere più server Standard Edition o passare a Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Front End Server

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

In un pool Front End, è necessario disporre di un front end server per ogni 6.660 utenti ospitati nel pool, presupponendo che l'Hyper-Threading sia abilitato su tutti i server del pool e che l'hardware del server soddisfi le indicazioni riportate nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md). Il numero massimo di utenti in un pool Front End è 80.000, presupponendo che l'Hyper-Threading sia abilitato su tutti i server del pool. Se in un sito sono presenti più di 80.000 utenti è possibile distribuire più pool Front End.

Quando si calcola il numero di utenti in un pool Front End, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a tale pool.

Quando un server attivo non è disponibile, le relative connessioni vengono trasferite automaticamente agli altri server del pool. Ad esempio, se si dispone di 30.000 utenti e cinque front end server, se un server non è disponibile, le connessioni degli utenti di 6000 devono essere trasferite agli altri quattro server. Gli altri quattro server avranno 7500 utenti, che è un numero maggiore di quello consigliato.

Se invece si è iniziato con sei front end server per gli utenti di 30.000 e successivamente non si è resi disponibili, per un totale di 5000 gli utenti verranno spostati nei cinque server rimanenti. Questi cinque server avranno ogni host 6000 utenti, che si trova nell'intervallo consigliato.

Il numero massimo di utenti in un pool Front End è 80.000. Il numero massimo di front end server in un pool è 12.

Per un pool Front end con 80.000 utenti, dodici front end server sono sufficienti per le prestazioni, nelle distribuzioni tipiche che seguono i [modelli utente in Lync Server 2013](lync-server-2013-user-models.md). Le distribuzioni progettate per supportare il failover del ripristino di emergenza presumono che un massimo di 40.000 utenti possano essere ospitati in ognuno dei due pool Front End associati, in cui ogni pool disponga di front end server sufficienti per ospitare gli utenti in entrambi i pool in caso di errore di un pool all'altro.

Il numero di utenti supportati con prestazioni ottimali da parte di un pool Front end specifico potrebbe differire da questi numeri per i motivi seguenti:

  - L'hardware per i Front End Server non soddisfa gli elementi consigliati nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

  - L'utilizzo dell'organizzazione si discosta notevolmente dai modelli utente, ad esempio il traffico delle conferenze è molto superiore.

<div>


> [!IMPORTANT]  
> In Lync Server 2013, i database di presenza sono ora ospitati nei Front End Server, a differenza di Lync Server 2010, in cui sono ospitati nel server back-end. Questo significa che le prestazioni e la capacità del disco dei front end server non devono essere compromesse dalle raccomandazioni elencate in precedenza in questa sezione e nelle <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A>, indipendentemente dal numero di utenti ospitati dai Front End Server.



</div>

Nella tabella seguente viene illustrata la larghezza di banda media per la messaggistica istantanea e la presenza, in base al modello utente, come definito nei [modelli utente di Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Larghezza di banda media per utente</th>
<th>Requisiti di larghezza di banda per front end server con 6.660 utenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Per migliorare le prestazioni multimediali delle funzionalità di A/V Conferencing e Mediation Server in base ai server front end, è necessario abilitare il riversamento sul lato ricezione (RSS) nelle schede di rete nei Front End Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo. Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Valori massimi per le conferenze

Dato il modello utente che prevede che il 5% degli utenti di un pool possono essere in conferenza in qualsiasi momento, un pool di 80.000 utenti può avere circa 4.000 utenti in conferenza in qualsiasi momento. Le conferenze saranno variabili nel tipo di contenuti multimediali (ad esempio alcune solo di messaggistica istantanea, altre di messaggistica istantanea e audio, altre audio/video) e nel numero di partecipanti. Non esiste un limite rigido per il numero effettivo di conferenze consentite e le prestazioni reali sono determinate dall'utilizzo. Se ad esempio il numero di conferenze in modalità mista dell'organizzazione è molto superiore a quello previsto nel modello utente, può essere necessario distribuire più Front End Server o A/V Conferencing Server rispetto a quanto consigliato in questo documento. Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).

Le dimensioni massime supportate per la conferenza ospitate da un pool di server front end normale di Lync 2013 che ospita anche gli utenti sono 250 partecipanti. Anche se è in corso una conferenza di 250 utenti, il pool supporta ancora anche altre conferenze, in modo che il 5% degli utenti del pool si trovi in conferenze simultanee. Ad esempio, in un pool di dodici front end server e 80.000 utenti, mentre la conferenza di 250 utenti è in corso, Lync Server supporta 3.750 altri utenti che partecipano a conferenze di piccole dimensioni.

Indipendentemente dal numero di utenti che si trovano nel pool Front end o nel server Standard Edition, Lync Server supporta almeno 125 altri utenti che partecipano a conferenze di piccole dimensioni nello stesso pool o server che ospita una conferenza di 250 utenti.

Per abilitare le conferenze tra gli utenti di 250 e 1000, è possibile configurare un pool Front end separato solo per ospitare tali conferenze. Questo pool Front end non ospiterà alcun utente. Per informazioni dettagliate, vedere [supporto di riunioni di grandi dimensioni con Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Se nell'organizzazione sono presenti molte più conferenze in modalità miste rispetto a quelle assunte nel modello utente, potrebbe essere necessario distribuire più Front End Server rispetto ai consigli riportati in questo documento (fino a un massimo di 12 FEs). Per informazioni dettagliate sui presupposti del modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Edge Server

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

È necessario distribuire un server perimetrale per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due server perimetrali. Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Quando si calcola il numero di utenti per i server perimetrali, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

<div>


> [!NOTE]  
> Per migliorare le prestazioni del servizio A/V Conferencing Edge nei server perimetrali è opportuno abilitare Receive-Side Scaling (RSS) nelle schede di rete dei server perimetrali. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo. Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

Se si distribuisce il ruolo server Director, è consigliabile distribuire un amministratore per ogni 12.000 utenti remoti che accederanno contemporaneamente a un sito. Per la disponibilità elevata è consigliabile un minimo di due Director. Questi suggerimenti presumono che l'hardware per i server perimetrali soddisfi i suggerimenti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Quando si calcola il numero di utenti per i Director, includere gli utenti ospitati in Survivable Branch Appliance e Survivable Branch Server nelle succursali associate a un pool Front End del sito.

</div>

<div>

## <a name="mediation-server"></a>Mediation Server

<div>


> [!NOTE]  
> I pool allungati non sono supportati per questo ruolo del server.



</div>

Se si colloca Mediation Server con Front End Server, Mediation Server viene eseguito in tutti i Front End Server nel pool e deve fornire una capacità sufficiente per gli utenti nel pool.

Se si distribuisce un pool di Mediation Server autonomo, il numero di Mediation Server da distribuire dipende da molti fattori, tra cui l'hardware utilizzato per Mediation Server, il numero di utenti di VoIP che si ha, la quantità di peer gateway che ogni pool di Mediation Server controlli, il traffico di ora occupato attraverso tali gateway e la percentuale di chiamate con supporto che ignora il Mediation Server.

Nelle tabelle seguenti vengono fornite linee guida per il numero di chiamate simultanee che un Mediation Server può gestire, presupponendo che l'hardware per i Mediation Server soddisfi i requisiti nelle [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) e che sia abilitato l'Hyper-Threading. Per informazioni dettagliate sulla scalabilità dei Mediation Server, vedere [stima dell'utilizzo e del traffico vocale per Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Tutte le tabelle seguenti presumono l'utilizzo come riepilogato nei [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacità Mediation Server autonomo: 70% utenti interni, 30% utenti esterni con capacità di chiamata non di bypass (transcodifica multimediale eseguita da Mediation Server)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware dei server</th>
<th>Numero massimo di chiamate</th>
<th>Numero massimo di linee T1</th>
<th>Numero massimo di linee E1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Doppio processore, hex core, CPU Hyper-Threading da 2,26 GHz <strong>con Hyper-Threading disabilitato</strong>, con 32 GB di memoria e una scheda di rete a doppia porta.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Processore duale, Core esagonale, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e una scheda di rete a doppia porta.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Anche se nei test delle prestazioni sono stati utilizzati server con 32 GB di memoria, i server con 16 GB di memoria sono sono supportati in Mediation Server autonomo e sono sufficienti a garantire le prestazioni indicate in questa tabella.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacità Mediation Server (Mediation Server collocato con Front End Server) 70% utenti interni, 30% utenti esterni, capacità di chiamata non di bypass (elaborazione multimediale eseguita da Mediation Server)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware dei server</th>
<th>Numero massimo di chiamate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processore duale, Core Hex, CPU Hyper-Threading da 2,26 GHz, con memoria 32 GB e 2 schede di rete da 1 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Questo numero è molto più piccolo dei numeri per il Mediation Server autonomo perché il front end server deve gestire altre caratteristiche e funzionalità per gli utenti di 6600 ospitati in esso, oltre alla transcoding necessaria per le chiamate vocali.



</div>

<div>


> [!NOTE]  
> Per migliorare le prestazioni del Mediation Server, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete dei Mediation Server. RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server. Per informazioni dettagliate, vedere "miglioramenti della scalabilità dei ricevimenti in Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>" all'indirizzo. Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.



</div>

</div>

<div>

## <a name="back-end-server"></a>server back-end

In Lync Server 2013, i database di presenza si trovano nei front end server invece che nel server back-end. Questo ha determinato un requisito molto più semplice per ogni server back-end in Lync Server 2013, equivalente ai requisiti hardware per il front end server. Contrapporre questo a Lync Server 2010, in cui il server back-end è stato richiesto per essere un server di grado molto più alto con 25 dischi. Tuttavia, il carico di lavoro dei server back-end è ancora tale da non riuscire a rispondere alle raccomandazioni hardware elencate in precedenza in questa sezione e nelle [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Per garantire la disponibilità elevata del server back-end, è consigliabile distribuire il mirroring del server. Per ulteriori informazioni, vedere [disponibilità elevata del server back-end in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

In Lync Server 2013, se si distribuisce il monitoraggio o l'archiviazione, la funzionalità front-end di questi servizi viene eseguita nei Front End Server, anziché in ruoli server distinti. Monitoring and Archiving each utilizzano ancora un archivio di database separato dall'archivio di back-end. In alternativa, se si dispone di Exchange 2013 distribuito, è possibile archiviare i dati di archiviazione dei messaggi istantanei in Exchange anziché in un archivio SQL dedicato.

La tabella seguente indica approssimativamente la quantità di spazio di archiviazione dei database necessaria per utente al giorno per il monitoraggio e l'archiviazione di dati.


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
<td><p>Spazio su disco necessario per utente per giorno</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft ha utilizzato l'hardware nella tabella seguente per il server di database per il monitoraggio e l'archiviazione durante il testing delle prestazioni. Il test ha raccolto i dati di due pool Front End, ognuno dei quali conteneva 80.000 utenti.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware utilizzato per il monitoraggio e il testing delle prestazioni di archiviazione

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
<td><p>Processore doppio a 64 bit, hex core, 2,26 GHz o superiore</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>48 gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><p>unità disco rigido 25 10.000-RPM con 300 GB su ogni disco, con la seguente configurazione</p>
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
<td><p>File di dati CDR, QoE e di archiviazione per database, in un'unica unità</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>File di registro del database CDR</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>File di registro del database QoE</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="odd">
<td><p>File di registro del database di archiviazione</p></td>
<td><p>1 </p></td>
<td><p>2 </p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Rete</p></td>
<td><ul>
<li><p>Una scheda di rete dual port, 1 Gbps o superiore (due consigliate, da associare a un singolo indirizzo MAC e a un singolo indirizzo IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Stima dell'utilizzo e del traffico vocale per Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

