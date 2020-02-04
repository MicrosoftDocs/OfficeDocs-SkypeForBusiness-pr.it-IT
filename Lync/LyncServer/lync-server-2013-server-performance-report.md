---
title: 'Lync Server 2013: report sulle prestazioni del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb7e01086ac423380a913b75391ec3086ee3736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Report prestazioni server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Il report prestazioni server include un elenco dei server di Microsoft Lync Server 2013 che hanno sperimentato la percentuale più alta di chiamate scadenti. Il report suddivide i server per tipo di server, segnalando statistiche separate per i tipi seguenti:

  - Mediation Server

  - A/V Conferencing Server

  - A/V Edge Server

  - Gateway (Mediation Server)

  - Gateway (bypass Mediation Server)

  - Video (incluse le metriche video per i server di servizi di conferenza A/V e i/V Edge Server)

  - Condivisione di applicazioni (incluse le metriche di condivisione delle applicazioni per i server di servizi di conferenza A/V e i/V Edge Server)

È importante notare che la classificazione mostrata in questo report è come classifica relativa. Supponiamo ad esempio che il server con prestazioni peggiori abbia una chiamata scadente tra le chiamate a 1.000. È una percentuale più che accettabile di 1%. Tuttavia, se questo è il server più performante che hai (ovvero, se tutti gli altri server hanno una percentuale di chiamata scadente anche inferiore a .1%), il server continuerà a essere visualizzato nel report sulle prestazioni del server.

<div>

## <a name="accessing-the-server-performance-report"></a>Accesso al report sulle prestazioni del server

Il report prestazioni server è accessibile dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale di chiamata scadente

È inoltre possibile eseguire il drill-down per il report trend qualità media del server facendo clic sulla metrica seguente:

  - Tendenza

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>Uso ottimale del report sulle prestazioni del server

Il report prestazioni server offre diversi modi per filtrare i dati. ad esempio, è possibile filtrare in base al tipo di rete (chiamate effettuate da una connessione cablata e chiamate effettuate da una connessione wireless) e il tipo di accesso (chiamate effettuate dall'interno del firewall e dalle chiamate effettuate dall'esterno del firewall). È una buona idea quando si Visualizza il report sulle prestazioni del server per usare questi filtri. Supponiamo ad esempio di avere un Mediation Server con una percentuale di chiamata scadente pari a 3,24%. Se si osservano solo le chiamate wireless, lo stesso server potrebbe avere una percentuale di chiamata scadente che si avvicina al 20%. Ciò significa che il server ha avuto difficoltà con le chiamate wireless, un problema parzialmente oscurato perché il server non aveva problemi con le chiamate cablate.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report sulle prestazioni del server, ad esempio, consente di eseguire operazioni come filtrare i dati restituiti per tipo di server o per tipo di rete (cablata o wireless). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, i dati vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report prestazioni server.

### <a name="server-performance-report-filters"></a>Filtri dei report sulle prestazioni del server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Da</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di server</strong></p></td>
<td><p>Indica il tipo di server di cui devono essere segnalate le prestazioni. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>Mediation Server</p></li>
<li><p>A/V Conferencing Server</p></li>
<li><p>A/V Edge Server</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>Inizio N</strong></p></td>
<td><p>Indica il numero di server (in base alla percentuale di chiamate) da visualizzare in ogni categoria. Ad esempio, se si seleziona <strong>5</strong> , vengono visualizzati i cinque server con prestazioni più scarse. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>Interno</p></li>
<li><p>Esterno</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report sulle prestazioni del server.

### <a name="server-performance-report-metrics-audio-call-summary"></a>Metriche del report sulle prestazioni del server: riepilogo delle chiamate audio

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Può ordinare in base a</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>No</p></td>
<td><p>Nome/indirizzo IP del server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate effettuate.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>Andata e ritorno (MS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Lync Server il server di monitoraggio usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
<p>I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Jitter (MS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto nascosto del guaritore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto allungato guaritore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto compresso del guaritore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>Metriche dei report sulle prestazioni del server: riepilogo videochiamata

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tipo di chiamata/tipo di endpoint</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo. I tipi di chiamata includono:</p>
<ul>
<li><p>Chiamate peer-to-peer UC</p></li>
<li><p>Sessioni di conferenza UC</p></li>
<li><p>Sessioni di conferenza PSTN</p></li>
<li><p>Chiamate PSTN: bypass multimediale</p></li>
<li><p>Chiamate PSTN (non bypass): Leg UC</p></li>
<li><p>Chiamate PSTN (non bypass): Leg gateway</p></li>
<li><p>Altri tipi di chiamata</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate per tipo di chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata wireless)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate che hanno usato una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata (chiamata VPN)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate che hanno usato una connessione VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata esterna)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocità di bit AVG (kbit/s)</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità in bit video media (in kilobit al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di bit bassa</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale della chiamata in cui il bit rate è basso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti in uscita</strong></p></td>
<td><p>No</p></td>
<td><p>Perdita di pacchetti RTP (Real-Time Transport Protocol) per pacchetti in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fotogramma congelato%</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di fotogrammi "bloccati". In un fotogramma bloccato il video smette di avanzare mentre la parte audio della chiamata continua.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza fotogrammi in uscita AVG</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza fotogrammi media per le trasmissioni in uscita durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Frequenza fotogrammi in ingresso AVG</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza fotogrammi media per le trasmissioni in arrivo durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza fotogrammi ridotta in ingresso%</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale della chiamata in cui la velocità in bit per il video in arrivo è bassa.</p></td>
</tr>
<tr class="even">
<td><p><strong>Integrità client%</strong></p></td>
<td></td>
<td><p>Indica l'integrità relativa del dispositivo client durante la chiamata.</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>Metriche del report sulle prestazioni del server: riepilogo delle chiamate di condivisione applicazioni

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tipo di chiamata/tipo di endpoint</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo. I tipi di chiamata includono:</p>
<ul>
<li><p>Chiamate peer-to-peer UC</p></li>
<li><p>Sessioni di conferenza UC</p></li>
<li><p>Sessioni di conferenza PSTN</p></li>
<li><p>Chiamate PSTN: bypass multimediale</p></li>
<li><p>Chiamate PSTN (non bypass): Leg UC</p></li>
<li><p>Chiamate PSTN (non bypass): Leg gateway</p></li>
<li><p>Altri tipi di chiamata</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate per tipo di chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata wireless)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate che hanno usato una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata (chiamata VPN)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate che hanno usato una connessione VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata esterna)</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Jitter (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>AVG. un modo relativo</strong></p></td>
<td><p>No</p></td>
<td><p>Ritardo unidirezionale relativo medio tra due endpoint multimediali. Si tratta di una misura di latenza single-hop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Latenza di elaborazione del riquadro media RDP</strong></p></td>
<td><p>No</p></td>
<td><p>La latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. Questa metrica non include la latenza della rete. Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale riquadro viziato%</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale totale di riquadri RDP viziati.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

