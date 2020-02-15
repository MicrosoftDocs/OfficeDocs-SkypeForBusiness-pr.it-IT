---
title: 'Lync Server 2013: rapporto riepilogativo sulla qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Report riepilogativo sulla qualità multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-06-29_

Il Rapporto riepilogativo qualità multimediale è probabilmente la risorsa migliore per analizzare la qualità delle chiamate nell'organizzazione: questo rapporto offre metriche QoE (Quality of Experience) dettagliate sulle chiamate, suddivise nelle categorie seguenti:

  - Chiamate peer-to-peer UC (ad esempio una chiamata Microsoft Lync 2013 a Microsoft Lync 2013)

  - Sessioni conferenza UC

  - Sessioni conferenza PSTN

  - Chiamate PSTN: bypass multimediale

  - Chiamate PSTN (senza bypass): coda UC

  - Chiamate PSTN (senza bypass): coda gateway

  - Altri tipi di chiamata

Quando si apre per la prima volta il rapporto, vengono visualizzate informazioni di riepilogo per ognuna delle categorie. Senza lasciare il report, è possibile espandere ogni categoria per esaminare le sottocategorie, ad esempio le chiamate effettuate da Office Communicator 2007 R2 a Lync 2013. È quindi possibile eseguire il drill-down in queste sottocategorie per visualizzare dettagli su ogni chiamata effettuata.

In Microsoft Lync Server 2013 il rapporto riepilogativo sulla qualità multimediale suddivide ulteriormente i dati in tre tipi di chiamata: chiamate audio, chiamate video e chiamate di condivisione applicazioni. A ogni tipo di chiamata è associata una sezione del rapporto e un set personalizzato di metriche.

Il Rapporto riepilogativo qualità multimediale consente inoltre di applicare filtri in base ai quali confrontare la qualità delle chiamate cablate con quella delle chiamate wireless, di quelle interne con quelle esterne e delle chiamate VPN rispetto a quelle non VPN.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>Accesso al Rapporto riepilogativo qualità multimediale

Il Rapporto riepilogativo qualità multimediale è accessibile dalla home page Rapporti di monitoraggio. È possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale chiamate di livello insufficiente

È inoltre possibile accedere al Rapporto distribuzione metriche di qualità multimediale facendo clic sulle metriche di chiamata audio seguenti:

  - Roundtrip (ms)

  - Degradazione (MOS)

  - Perdita di pacchetti

  - Instabilità (ms)

  - Rapporto campioni nascosti utilità di ripristino

  - Rapporto campioni estesi utilità di ripristino

  - Rapporto campioni compressi utilità di ripristino

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il rapporto riepilogativo sulla qualità multimediale, ad esempio, consente di filtrare i dati restituiti in base a fattori come il tipo di accesso (interno o esterno) o il tipo di connessione di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo sulla qualità multimediale.

### <a name="media-quality-summary-report-filters"></a>Filtri per il rapporto riepilogativo sulla qualità multimediale

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
<p>Le settimane vengono calcolate sempre dal lunedì alla domenica.</p></td>
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
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Interna</p></li>
<li><p>Esterna</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</p>
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

Nella tabella seguente sono elencate le informazioni disponibili nel rapporto riepilogativo sulla qualità multimediale.

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate audio

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
<td><p><strong>Tipo di chiamata/Tipo di endpoint </strong></p></td>
<td><p>No</p></td>
<td><p>Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</p>
<ul>
<li><p>Chiamate peer-to-peer UC</p></li>
<li><p>Sessioni conferenza UC</p></li>
<li><p>Sessioni conferenza PSTN</p></li>
<li><p>Chiamate PSTN: bypass multimediale</p></li>
<li><p>Chiamate PSTN (senza bypass): coda UC</p></li>
<li><p>Chiamate PSTN (senza bypass): coda gateway</p></li>
<li><p>Altri tipi di chiamata</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate per ciascun tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata wireless) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata (chiamata VPN) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata esterna) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tempo medio di roundtrip, in millisecondi, necessario per un pacchetto RTP (Real-Time Transport Protocol) per viaggiare fino a un altro endpoint e tornare indietro. Un roundtrip di 100 millisecondi o meno è considerato di qualità accettabile.</p>
<p>Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Degradazione MOS (Mean Opinion Score) media sperimentata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</p>
<p>Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video in Internet, non raggiungono la destinazione. Valori di perdita alti sono in genere dovuti a congestione, disponibilità di una larghezza di banda troppo ridotta, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</p></td>
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
<td><p>Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle videochiamate

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
<td><p><strong>Tipo di chiamata/Tipo di endpoint </strong></p></td>
<td><p>No</p></td>
<td><p>Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</p>
<ul>
<li><p>Chiamate peer-to-peer UC</p></li>
<li><p>Sessioni conferenza UC</p></li>
<li><p>Sessioni conferenza PSTN</p></li>
<li><p>Chiamate PSTN: bypass multimediale</p></li>
<li><p>Chiamate PSTN (senza bypass): coda UC</p></li>
<li><p>Chiamate PSTN (senza bypass): coda gateway</p></li>
<li><p>Altri tipi di chiamata</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate per ciascun tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata wireless) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata (chiamata VPN) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata esterna) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocità media in bit (Kbit/s)</strong></p></td>
<td><p>No</p></td>
<td><p>Velocità in bit video media (in kilobit al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>Bassa velocità in bit (%)</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale della chiamata con velocità in bit bassa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti in uscita</strong></p></td>
<td><p>No</p></td>
<td><p>Perdita di pacchetti RTP (Real-Time Transport Protocol) in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>% fotogrammi bloccati</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di fotogrammi “bloccati”. In un fotogramma bloccato, il video smette di avanzare mentre la parte audio della chiamata prosegue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza media dei fotogrammi in uscita</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza media dei fotogrammi per le trasmissioni in uscita durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Frequenza media dei fotogrammi in ingresso</strong></p></td>
<td><p>No</p></td>
<td><p>Frequenza media dei fotogrammi per le trasmissioni in arrivo durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bassa frequenza dei fotogrammi in ingresso (%)</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale della chiamata con velocità in bit bassa per il video in arrivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Integrità client (%)</strong></p></td>
<td></td>
<td><p>Indica l'integrità relativa del dispositivo client durante la chiamata.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate di condivisione applicazioni

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
<td><p><strong>Tipo di chiamata/Tipo di endpoint </strong></p></td>
<td><p>No</p></td>
<td><p>Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</p>
<ul>
<li><p>Chiamate peer-to-peer UC</p></li>
<li><p>Sessioni conferenza UC</p></li>
<li><p>Sessioni conferenza PSTN</p></li>
<li><p>Chiamate PSTN: bypass multimediale</p></li>
<li><p>Chiamate PSTN (senza bypass): coda UC</p></li>
<li><p>Chiamate PSTN (senza bypass): coda gateway</p></li>
<li><p>Altri tipi di chiamata</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate per ciascun tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata wireless) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata (chiamata VPN) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate eseguite tramite una connessione VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume chiamata (chiamata esterna) </strong></p></td>
<td><p>No</p></td>
<td><p>Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Instabilità (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Instabilità media rilevata tra gli arrivi di pacchetti RTP. (Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="even">
<td><p><strong>Media unidirezionale relativa</strong></p></td>
<td><p>No</p></td>
<td><p>Media unidirezionale relativa tra due endpoint multimediali. Si tratta di una misurazione della latenza a singolo hop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Latenza media elaborazione sezioni RDP</strong></p></td>
<td><p>No</p></td>
<td><p>Latenza media dell'elaborazione delle sezioni RDP in AS Conferencing Server per la durata della sessione di visualizzazione. Una media elevata riflette un ritardo più lungo nell'esperienza di visualizzazione e include la latenza della rete. In un server per conferenze sovraccaricato possono verificarsi ritardi medi maggiori.</p></td>
</tr>
<tr class="even">
<td><p><strong>% totale sezioni danneggiate</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale totale di sezioni RDP danneggiate.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

