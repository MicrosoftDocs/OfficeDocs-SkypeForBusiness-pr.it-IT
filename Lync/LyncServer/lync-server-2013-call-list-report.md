---
title: 'Lync Server 2013: rapporto elenco chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b53aa6929f5719b3d291e38cdfe3265cc0458f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Rapporto elenco chiamate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Il rapporto Elenco chiamate offre metriche QoE (Quality of Experience) per le singole chiamate effettuate e ricevute nell'organizzazione. Tenere presente che le metriche effettive riportate dipendono dalla modalità di accesso al rapporto Elenco chiamate. Ad esempio, se si apre il report del rapporto [dispositivo in Lync Server 2013](lync-server-2013-device-report.md), vengono visualizzate le metriche, quali le metriche seguenti, che sono state segnalate anche nel rapporto dispositivo:

  - Microfono del chiamante

  - Altoparlante del chiamante

  - Microfono del chiamato

  - Altoparlante del chiamato

  - Rapporto di tempo commutazione vocale

Tuttavia, se si apre il rapporto elenco chiamate dal [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md), non verrà visualizzata alcuna di queste metriche. si vedranno invece metriche come queste:

  - Roundtrip (ms)

  - Degradazione (MOS)

  - Perdita di pacchetti

  - Instabilità (ms)

Si tratta delle metriche riportate nel Rapporto percorsi. Tuttavia, nel rapporto Elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per ottenere informazioni di QoE complete per qualsiasi chiamata.

<div>

## <a name="accessing-the-call-list-report"></a>Accesso al rapporto Elenco chiamate

Il rapporto Elenco chiamate è accessibile da qualsiasi dei rapporti seguenti:

  - Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)

  - Il [rapporto del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)

  - Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)

  - Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)

Dall'interno del rapporto elenco chiamate è possibile accedere al [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) facendo clic sulla metrica Dettagli.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Uso ottimale del rapporto Elenco chiamate

Se non si è certi del tipo di misurazioni offerte dalle metriche del rapporto Elenco chiamate (ad esempio il rapporto di tempo di commutazione vocale), tenere il puntatore del mouse sull'etichetta per visualizzare una descrizione comandi con informazioni sintetiche sulla metrica in questione.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il rapporto Elenco chiamate.

</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto Elenco chiamate per ogni chiamata.

### <a name="call-list-report-metrics"></a>Metriche del rapporto Elenco chiamate

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
<td><p><strong>Dettagli</strong></p></td>
<td><p>No</p></td>
<td><p>Facendo clic su questo elemento è possibile visualizzare ulteriori informazioni sulla chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora inizio</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di inizio della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di fine della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente chiamante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente destinatario chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Software utilizzato dall'endpoint dell'utente che è stato chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.</p>
<p>Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</p>
<p>Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>Sì</p></td>
<td><p>Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Instabilità</strong></p></td>
<td><p>Sì</p></td>
<td><p>Instabilità media rilevata tra gli arrivi di pacchetti RTP. (Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto campioni nascosti utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto campioni estesi utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto campioni compressi utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tipo di collegamento di comunicazione wireless. In genere è uno dei seguenti:</p>
<ul>
<li><p>Relè</p></li>
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

