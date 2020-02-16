---
title: 'Lync Server 2013: Rapporto tendenze qualità multimediale server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c36add301665c2e6b689bd1343cc09efeec5b3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Rapporto tendenze qualità multimediale server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-12_

Il Rapporto tendenze qualità multimediale server offre un modo per confrontare graficamente fino a 5 server relativamente a metriche QoE quali il volume di chiamata, la percentuale di chiamate di livello insufficiente, la perdita di pacchetti e l'instabilità. Ciò agevola attività quali l'identificazione dei server con prestazioni insufficienti, sottoutilizzati o sovrautilizzati.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Accesso al Rapporto tendenze qualità multimediale server

Il Rapporto tendenze qualità multimediale server è accessibile da uno o l'altro dei rapporto seguenti:

  - [Rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica tendenza)

  - [Rapporto dettagli chiamata in Lync server 2013](lync-server-2013-call-detail-report.md) (facendo clic sulla metrica a/V Edge Server. Se il chiamante o il destinatario della chiamata è un server, è possibile raggiungere anche il rapporto trend media Quality Server facendo clic sul nome dell'endpoint.

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Uso ottimale del Rapporto tendenze qualità multimediale server

Quando si fa clic sulla metrica di tendenza sul [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) per un server specifico, verrà aperto il rapporto tendenze qualità multimediale server. Tuttavia, verrà visualizzata solo un'istanza vuota del rapporto; il server selezionato nel Rapporto prestazioni dei server non verrà visualizzato. Sarà invece necessario selezionare il server dal menu a discesa Server. Tenere presente che l'elenco a discesa Server include anche un'opzione Seleziona tutto. Questa opzione non funziona se sono presenti più di 5 server; il Rapporto tendenze qualità multimediale server è in grado di visualizzare dati per un massimo di 5 server alla volta.

Nei grafici visualizzati dal rapporto tendenze qualità multimediale server, il volume delle chiamate a punti e la percentuale di chiamate insufficienti sono hotlinks; Se si fa clic su un punto del grafico, verrà aperta un'istanza del [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) che mostra le chiamate totali (o le chiamate insufficienti) per il periodo di tempo specificato.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto tendenze qualità multimediale server.

### <a name="server-media-quality-trend-report-filters"></a>Filtri del Rapporto tendenze qualità multimediale server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Selezionare uno dei seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare un massimo di 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
</ul>
<p>Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo Giornaliero con la data di inizio 07.07.12 e la data di fine 28.02.12, verranno visualizzati i dati relativi ai giorni da 07.08.12 alle 00.00 a 07.09.12 alle 00.00, ovvero per un totale di 31 giorni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di server </strong></p></td>
<td><p>Tipo di server coinvolto nella chiamata. Valori consentiti:</p>
<ul>
<li><p>Mediation Server</p></li>
<li><p>A/V Conferencing Server</p></li>
<li><p>A/V Edge Server</p></li>
<li><p>Gateway (Mediation Server)</p></li>
<li><p>Gateway (bypass a Mediation Server)</p></li>
<li><p>AS Conferencing Server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servers</strong></p></td>
<td><p>Nome del server coinvolto nella sessione; questo elenco a discesa viene automaticamente popolato in base al valore del filtro Tipo di server. È possibile selezionare fino a 5 diversi server per la compilazione di un rapporto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di accesso </strong></p></td>
<td><p>Indica se il partecipante era connesso alla rete interna o dalla rete esterna. Valori consenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Interna</p></li>
<li><p>Esterna</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete </strong></p></td>
<td><p>Indica il tipo di rete a cui era connesso il partecipante. Valori consentiti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un partecipante esterno utilizzava una connessione di rete privata virtuale (VPN) durante la sessione. Valori consentiti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto tendenze qualità multimediale server.

### <a name="server-media-quality-trend-report-metrics"></a>Metriche del Rapporto tendenze qualità multimediale server

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Valore medio di degrado di MOS (Media Option score) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore pari a 0,5 o meno rappresenta un calo accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</p>
<p>Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tempo medio (in millisecondi) richiesto per il roundtrip di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 200 millisecondi vengono considerati accettabili.</p>
<p>Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Instabilità (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Instabilità media rilevata tra gli arrivi di pacchetti RTP. (Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto campioni nascosti utilità di ripristino</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto campioni estesi utilità di ripristino</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto campioni compressi utilità di ripristino</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

