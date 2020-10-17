---
title: 'Lync Server 2013: rapporto località'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e98107d4949a935cbef448e1a533bddb0f7c5dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513793"
---
# <a name="location-report-in-lync-server-2013"></a>Report percorso in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Nel Rapporto percorsi vengono fornite informazioni sulla metrica di qualità delle chiamate raggruppata per percorso di rete, ovvero per subnet di rete. Se si verificano problemi con le chiamate degli utenti, questo rapporto consente di determinare se i problemi sono diffusi oppure sono circoscritti a un segmento di rete specifico.

<div>

## <a name="accessing-the-location-report"></a>Accesso al Rapporto percorsi

Il Rapporto percorsi è accessibile dalla home page di Relazioni monitoraggio. È possibile eseguire il drill-down fino al Rapporto Elenco chiamate facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale chiamate di livello insufficiente

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il Rapporto percorsi, ad esempio, consente di filtrare in base alla posizione dalla quale è stata originata una chiamata o a seconda che la chiamata sia stata effettuata utilizzando una connessione wireless o cablata. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella che segue sono elencati i filtri applicabili al Rapporto percorsi.

### <a name="location-report-filters"></a>Filtri del Rapporto percorsi

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
<td><p><strong>Località chiamante</strong></p></td>
<td><p>Subnet IP dell'utente che ha effettuato la chiamata. È possibile selezionare solo l'opzione <strong>[Tutto]</strong> per indicare tutte le subnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Località destinatario chiamata</strong></p></td>
<td><p>Subnet IP dell'utente che ha ricevuto la chiamata. È possibile selezionare solo l'opzione <strong>[Tutto]</strong> per indicare tutte le subnet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</p>
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

Nella tabella che segue sono elencate le informazioni fornite nel Rapporto percorsi.

### <a name="location-report-metrics"></a>Metriche del Rapporto percorsi

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
<td><p><strong>Subnet chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Subnet IP dell'utente che ha effettuato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet destinatario chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Subnet IP dell'utente che ha ricevuto la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di chiamate effettuate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale delle chiamate classificate come insufficienti. Una chiamata insufficiente è una chiamata per la quale almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un'instabilità eccessiva.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.</p>
<p>Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</p>
<p>Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>Sì</p></td>
<td><p>Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Instabilità</strong></p></td>
<td><p>Sì</p></td>
<td><p>Instabilità media rilevata tra gli arrivi di pacchetti RTP. (Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto campioni nascosti utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto campioni estesi utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto campioni compressi utilità di ripristino</strong></p></td>
<td><p>Sì</p></td>
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

