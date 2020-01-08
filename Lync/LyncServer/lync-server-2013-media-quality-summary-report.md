---
title: 'Lync Server 2013: report di riepilogo qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c967c6d6b120c73cb933281d4edb17be1868900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Report di riepilogo qualità multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-06-29_

Il report Riepilogo qualità multimediale è forse la soluzione migliore per analizzare la qualità delle chiamate nell'organizzazione: questo report fornisce le metriche delle chiamate QoE (Quality of Experience) dettagliate suddivise nelle categorie seguenti:

  - Chiamate peer-to-peer UC (ad esempio una chiamata di Microsoft Lync 2013 a Microsoft Lync 2013)

  - Sessioni di conferenza UC

  - Sessioni di conferenza PSTN

  - Chiamate PSTN: bypass multimediale

  - Chiamate PSTN (non bypass): Leg UC

  - Chiamate PSTN (non bypass): Leg gateway

  - Altri tipi di chiamata

Quando si apre il report per la prima volta, vengono visualizzate informazioni di riepilogo per ognuna di queste categorie. Senza uscire dal report, è possibile espandere ogni categoria per esaminare le sottocategorie, ad esempio le chiamate effettuate da Office Communicator 2007 R2 a Lync 2013. A sua volta, è possibile eseguire il drill-down in queste sottocategorie per visualizzare i dettagli su ogni chiamata effettuata all'interno di tale sottocategoria.

In Microsoft Lync Server 2013 il report Riepilogo qualità multimediale suddivide ulteriormente i dati in tre tipi di chiamata: chiamate audio, videochiamate e chiamate di condivisione applicazioni. Ogni tipo di chiamata ha una propria sezione nel report e un set personalizzato di metriche delle chiamate.

Il report Riepilogo qualità multimediale consente inoltre di applicare filtri che consentono di confrontare la qualità delle chiamate cablate e le chiamate wireless, le chiamate interne e le chiamate esterne e le chiamate VPN e le chiamate non VPN.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>Accesso al report di riepilogo qualità multimediale

Il report Riepilogo qualità multimediale è accessibile dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale di chiamata scadente

Inoltre, è possibile accedere al report di distribuzione delle metriche di qualità multimediale facendo clic su una delle metriche delle chiamate audio seguenti:

  - Andata e ritorno (MS)

  - Degradazione (MOS)

  - Perdita di pacchetti

  - Jitter (MS)

  - Rapporto nascosto del guaritore

  - Rapporto allungato guaritore

  - Rapporto compresso del guaritore

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report Riepilogo qualità multimediale consente di filtrare i dati restituiti in base a elementi come il tipo di accesso (ovvero l'accesso a intervalli o l'accesso esterno) o la connessione di rete cablata/wireless. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo qualità multimediale.

### <a name="media-quality-summary-report-filters"></a>Filtri report Riepilogo qualità multimediale

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
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Interno</p></li>
<li><p>Esterno</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:</p>
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

Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo qualità multimediale.

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>Metriche rapporto di riepilogo qualità multimediale: riepilogo delle chiamate audio

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
<td><p><strong>Andata e ritorno (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
<p>I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>No</p></td>
<td><p>Tasso medio di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto nascosto del guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto allungato guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto compresso del guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>Metriche rapporto di riepilogo qualità multimediale: riepilogo videochiamata

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
<td><p>Perdita di pacchetti RTP (Real-Time Transport Protocol) per pacchetti in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
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


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>Metriche rapporto di riepilogo qualità multimediale: riepilogo delle chiamate di condivisione applicazioni

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
<td><p>La latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione e include la latenza della rete. Un server di conferenza di overload può avere ritardi medi più alti.</p></td>
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

