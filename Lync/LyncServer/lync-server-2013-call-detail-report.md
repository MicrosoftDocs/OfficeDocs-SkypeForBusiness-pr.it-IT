---
title: 'Lync Server 2013: report dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a>Report dettagli chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Il report dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata; il report include quasi tutta la qualità delle metriche delle esperienze e delle statistiche raccolte da Lync Server, suddivise in sezioni di report, ad esempio:

  - Informazioni sulle chiamate

  - Metriche del segnale e del dispositivo chiamante

  - Dispositivo chiamato e metriche del segnale

  - Evento del client chiamante

  - Evento client chiamato

  - Flusso audio (chiamante)

  - Flusso video (chiamante)

  - Flusso audio (chiamato dal chiamante)

  - Flusso video (chiamato dal chiamante)

Tieni presente che le categorie e le metriche visualizzate in un report specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usati nella sessione. Ad esempio, una chiamata solo audio non riporta le metriche per i flussi video; Questo perché la chiamata non ha un flusso video. Analogamente, è possibile che sia presente un report che elenca le statistiche del chiamante ma non le statistiche chiamate. In genere perché il destinatario non usa un dispositivo conforme a SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata; Tuttavia, un cellulare (che non conosce le statistiche SIP o SIP) non è in grado di segnalare questo tipo di informazioni. Se si chiama qualcuno e si risponde al telefono cellulare, non si riceverà un report dal telefono cellulare al termine della chiamata.

Il report dettagli chiamata è molto utile quando si prova a determinare esattamente il motivo per cui una determinata chiamata ha riscontrato problemi di qualità multimediale.

<div>

## <a name="accessing-the-call-detail-report"></a>Accesso al report dettagli chiamata

È possibile accedere al report dettagli chiamata da uno dei report seguenti:

  - [Report posizione in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - [Report di riepilogo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - [Report di confronto qualità multimediale in Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (fare clic sul [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) e quindi fare clic sulla metrica dettaglio).

  - [Report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)

  - [Report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) (facendo clic sulla metrica dettaglio)

Dall'interno del report dettagli chiamata è possibile accedere al [report del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) facendo clic su una delle metriche seguenti:

  - Dispositivo di acquisizione

  - Dispositivo di rendering

È anche possibile accedere al report trend qualità media del server facendo clic sulla metrica A/V Edge Server.

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>Sfruttare al meglio il report dettagli chiamata

Il report dettagli chiamata in genere include più di 250 metriche diverse, inclusi elementi come la deriva del timestamp del microfono, l'ora bassa di SNR e la fine del tempo di Echo. Se non si riesce a ricordare ciò che tutte queste metriche effettivamente misurano, provare a tenere il mouse sopra l'etichetta metrica; spesso, viene visualizzata una descrizione comando che descrive la metrica.

In caso di problemi con l'individuazione di una metrica, digitare parte dell'etichetta metrica nella casella di ricerca e quindi fare clic su trova. Ad esempio, se non si riesce a trovare la metrica per l'ora bassa SNR, digitare SNR nella casella di ricerca e quindi fare clic su trova.

Tieni presente che il report tiene traccia solo delle informazioni su una chiamata. La chiamata stessa non viene registrata.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report dettagli chiamata.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report dettagli chiamata per ogni chiamata.

### <a name="call-detail-report-metrics"></a>Metriche report dettagli chiamata

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
<td><p><strong>Chiamante PAI</strong></p></td>
<td><p>No</p></td>
<td><p>P-asserzione-identità dell'utente che ha avviato la chiamata. La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endpoint chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Dispositivo usato per effettuare la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Software usato nel dispositivo che ha eseguito la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inizio chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui la chiamata è stata inizialmente inserita.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamata di bypass di Mediation Server</strong></p></td>
<td><p>No</p></td>
<td><p>Indica se la chiamata è connessa a un gateway vocale PSTN o a un IP-PBX qualificato senza passare tramite Mediation Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sistema operativo chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Sistema operativo del computer del chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>CPU installata nel computer dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Numero di core della CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Numero del processore nel computer usato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Velocità della CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità di clock della CPU del computer usato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Virtualizzazione della CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Virtualizzazione (se presenti) usata nel computer usato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamata PAI</strong></p></td>
<td><p>No</p></td>
<td><p>P-asserzione-identità dell'utente invitato a partecipare alla chiamata. La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che è stato chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endpoint chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Dispositivo usato per ricevere la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Software usato nel dispositivo che ha ricevuto la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durata</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo per la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Contrassegno di avviso di bypass multimediale</strong></p></td>
<td><p>No</p></td>
<td><p>Avviso emesso quando il Mediation Server è stato ignorato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sistema operativo chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Sistema operativo del computer per l'utente che è stato chiamato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>CPU installata nel computer dell'utente che è stato chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Numero di nucleo chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Numero del processore nel computer usato dalla persona che è stata chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocità della CPU chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità di clock della CPU del computer usato dalla persona che è stata chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Virtualizzazione della CPU chiamato</strong></p></td>
<td><p>No</p></td>
<td><p>Virtualizzazione (se presenti) usata nel computer usato dalla persona che è stata chiamata.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

