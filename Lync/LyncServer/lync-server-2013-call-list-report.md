---
title: 'Lync Server 2013: report elenco chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Report elenco chiamate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Il report elenco chiamate offre metriche di qualità delle esperienze (QoE) per le singole chiamate effettuate e ricevute nell'organizzazione. Tieni presente che le metriche effettive segnalate dipendono dalla modalità di accesso al report elenco chiamate. Ad esempio, se si apre il report dal [report dispositivo in Lync Server 2013](lync-server-2013-device-report.md), verranno visualizzate le metriche, come le metriche seguenti, che vengono anche segnalate nel report del dispositivo:

  - Microfono del chiamante

  - Altoparlante del chiamante

  - Microfono del destinatario

  - Altoparlante del destinatario

  - Rapporto tra il tempo di cambio vocale

Tuttavia, se si apre il report elenco chiamate dal [report posizione in Lync Server 2013](lync-server-2013-location-report.md), non verrà visualizzata alcuna di queste metriche. vedrai invece le metriche come queste:

  - Andata e ritorno (MS)

  - Degradazione (MOS)

  - Perdita di pacchetti

  - Jitter (MS)

Queste sono le metriche segnalate nel report posizione. Tuttavia, dal report elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per specificare le informazioni QoE complete per qualsiasi chiamata.

<div>

## <a name="accessing-the-call-list-report"></a>Accesso al report elenco chiamate

È possibile accedere al report elenco chiamate da uno dei report seguenti:

  - [Report posizione in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - Il [report del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - [Report di riepilogo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - [Report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

Dall'interno del report elenco chiamate è possibile accedere al [report dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) facendo clic sulla metrica dettaglio.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Sfruttare al meglio il report elenco chiamate

Se non si ricordano le metriche del rapporto elenco chiamate (ad esempio il tempo di cambio di rapporto vocale), tenere il mouse sopra l'etichetta metrica; verrà visualizzata una descrizione comando che consente di visualizzare brevemente la metrica.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report elenco chiamate.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report elenco chiamate per ogni chiamata.

### <a name="call-list-report-metrics"></a>Metriche rapporto elenco chiamate

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
<td><p><strong>Dettagli</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, nel report vengono visualizzate altre informazioni sulla chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP della persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamato</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP della persona che è stata chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di inizio</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di inizio della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di fine della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente chiamante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Software usato dall'endpoint della persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente chiamato</strong></p></td>
<td><p>Sì</p></td>
<td><p>Software usato dall'endpoint della persona chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Andata e ritorno (MS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
<p>I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tasso medio di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Jitter</strong></p></td>
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
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tipo di collegamento di comunicazione wireless. In genere, questa è una delle opzioni seguenti:</p>
<ul>
<li><p>Inoltro</p></li>
<li><p>Diretto</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

