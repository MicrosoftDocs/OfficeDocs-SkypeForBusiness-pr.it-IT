---
title: 'Lync Server 2013: rapporto dettagli chiamata'
description: 'Lync Server 2013: rapporto dettagli chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561772"
---
# <a name="call-detail-report-in-lync-server-2013"></a>Rapporto dettagli chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Il rapporto dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata. il report include quasi tutte le metriche e le statistiche relative alla qualità delle esperienze raccolte da Lync Server, divise in sezioni di report, ad esempio:

  - Informazioni chiamata

  - Metrica dispositivi e segnale chiamante

  - Metrica dispositivi e segnale destinatario chiamata

  - Evento client chiamante

  - Evento client destinatario chiamata

  - Flusso audio (da chiamante a destinatario chiamata)

  - Flusso video (da chiamante a destinatario chiamata)

  - Flusso audio (da destinatario chiamata a chiamante)

  - Flusso video (da destinatario chiamata a chiamante)

Tenere presente che le categorie e le metriche incluse in un rapporto specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usato nella sessione. Ad esempio in una chiamata solo audio non saranno presenti metriche per i flussi video, in quanto la chiamata non presenta alcun flusso video. Analogamente, si potrebbe avere un rapporto in cui sono elencate statistiche del chiamante ma non del destinatario della chiamata. Questa situazione si verifica generalmente quando il destinatario della chiamata non usa un dispositivo compatibile con SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata, ma ad esempio un telefono cellulare (che non ha nulla a che vedere con SIP o statistiche SIP) non è in grado di produrre un rapporto su questo tipo di informazioni. Se si chiama qualcuno che risponde dal telefono cellulare, non verrà prodotto alcun rapporto da quel telefono al termine della chiamata.

Il Rapporto dettagli chiamata risulta utile soprattutto quando si prova a stabilire in modo preciso la causa dei problemi di qualità multimediale in una chiamata.

<div>

## <a name="accessing-the-call-detail-report"></a>Accesso al Rapporto dettagli chiamata

Si può accedere al Rapporto dettagli chiamata da uno dei rapporti seguenti:

  - Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica percentuale di chiamata scadente)

  - Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale chiamate insufficienti)

  - Il [rapporto di confronto qualità multimediale in Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (facendo clic sul [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) e quindi scegliendo la metrica dettaglio).

  - Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate di livello insufficiente)

  - Il [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) (facendo clic sulla metrica dettaglio)

Dal rapporto dettagli chiamata è possibile accedere al [rapporto dispositivi in Lync Server 2013](lync-server-2013-device-report.md) facendo clic su una delle metriche seguenti:

  - Dispositivo di acquisizione

  - Dispositivo di rendering

È inoltre possibile accedere al Rapporto tendenze qualità multimediale server facendo clic sulla metrica A/V Edge Server.

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>Utilizzo ottimale del Rapporto dettagli chiamata

Il Rapporto dettagli chiamata include generalmente oltre 250 metriche diverse, tra cui Deviazione timestamp microfono, Tempo rapporto segnale/rumore basso e Tempo rapporto segnale near-end/eco. Se non si ricorda la misura effettiva di tutte queste metriche, provare a posizionare il mouse sull'etichetta della metrica per visualizzare un a descrizione comando della metrica.

In caso di problemi nell'individuazione di una metrica, digitare parte dell'etichetta della metrica nella casella di ricerca e fare clic su Trova. Se ad esempio non si riesce a trovare la metrica Tempo rapporto segnale/rumore basso, digitare SNR nella casella di ricerca e fare clic su Trova.

Tenere presente che il report tiene traccia delle informazioni relative a una chiamata. La chiamata non è registrata.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile applicare filtri nel Rapporto dettagli chiamata.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto dettagli chiamata per ogni chiamata.

### <a name="call-detail-report-metrics"></a>Metrica del Rapporto dettagli chiamata

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PAI chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>PAI (P-Asserted-Identity) dell'utente che ha avviato la chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endpoint chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Dispositivo utilizzato per effettuare la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Software utilizzato nel dispositivo con cui è stata effettuata la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inizio chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di inizio della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamata di bypass a Mediation Server</strong></p></td>
<td><p>No</p></td>
<td><p>Indica l'eventuale connessione della chiamata a un gateway vocale PSTN o IP-PBX qualificato senza passare attraverso il Mediation Server.</p></td>
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
<td><p><strong>Numero di core CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di processori nel computer utilizzato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Velocità CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità di clock della CPU del computer utilizzato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Virtualizzazione CPU chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Eventuale virtualizzazione nel computer utilizzato dalla persona che ha avviato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>PAI destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>PAI (P-Asserted-Identity) dell'utente che ha inviato l'invito a partecipare alla chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endpoint destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Dispositivo utilizzato per ricevere la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Software utilizzato nel dispositivo con cui è stata ricevuta la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durata</strong></p></td>
<td><p>No</p></td>
<td><p>Durata della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag di avviso bypass multimediale</strong></p></td>
<td><p>No</p></td>
<td><p>Avviso generato quando è stato ignorato il Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sistema operativo destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Sistema operativo del computer dell'utente chiamato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>CPU installata nel computer dell'utente chiamato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Numero di core CPU destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di processori nel computer utilizzato dalla persona chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocità CPU destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità di clock della CPU del computer utilizzato dalla persona chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Virtualizzazione CPU destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Eventuale virtualizzazione nel computer utilizzato dalla persona chiamata.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

