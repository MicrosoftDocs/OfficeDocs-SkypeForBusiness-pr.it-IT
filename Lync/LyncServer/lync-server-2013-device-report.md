---
title: 'Lync Server 2013: report dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Report dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-12_

Il report del dispositivo potrebbe essere meglio intitolato il rapporto microfono e altoparlanti; Questo perché il report del dispositivo recupera le metriche correlate alle chiamate, ad esempio la percentuale di chiamata scadente, l'eco e il tempo di cambio vocale, raggruppate per i microfoni e gli altoparlanti usati nella chiamata. Se si è interessati ai telefoni IP (detti anche "dispositivi"), usare invece il report sull' [inventario dei telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .

Il report del dispositivo è estremamente utile per gli amministratori per determinare se un determinato tipo di dispositivo sta vivendo alti volumi di chiamate di qualità scadente rispetto ad altri. A sua volta, questo potrebbe influenzare qualsiasi decisione da apportare quando arriva il momento di acquistare nuovi dispositivi o di sostituire i dispositivi esistenti.

Per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata. Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente: per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata. Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente:

  - Dispositivo di acquisizione: microfono (SoundMAX Integrated Digital HD audio)

  - Dispositivo di rendering: auricolare Headset (Microsoft LifeChat LX-3000)

Se gli utenti hanno apportato un totale di 254 chiamate, nel report verrà visualizzata una voce simile alla seguente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo di acquisizione</th>
<th>Dispositivo di rendering</th>
<th>Volume chiamata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfono (SoundMAX Integrated Digital audio HD)</p></td>
<td><p>Auricolare (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Supponiamo che tu abbia un certo numero di utenti che usano lo stesso dispositivo di acquisizione, ma un dispositivo di rendering diverso. In questo caso, nel report verrà visualizzata una seconda voce, una per la combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo di acquisizione</th>
<th>Dispositivo di rendering</th>
<th>Volume chiamata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfono (SoundMAX Integrated Digital audio HD)</p></td>
<td><p>Auricolare (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Microfono (SoundMAX Integrated Digital audio HD)</p></td>
<td><p>Altoparlanti (SoundMAX Integrated Digital HD audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Se si preferisce visualizzare i totali combinati per un dispositivo specifico, ad esempio per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering usato, selezionare l'opzione appropriata nell'elenco a discesa tipo di dispositivo (dispositivo di acquisizione o dispositivo di rendering). Se si seleziona dispositivo di acquisizione in questo esempio, verrà restituito un output simile al seguente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo di acquisizione</th>
<th>Volume chiamata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfono (SoundMAX Integrated Digital audio HD)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Accesso al report del dispositivo

Il report del dispositivo è in genere accessibile dalla Home page dei report di monitoraggio. Se tuttavia si sta visualizzando il [report dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) , è possibile eseguire il drill-down per il report del dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:

  - Dispositivo di acquisizione

  - Dispositivo di rendering

Nel report del dispositivo è possibile eseguire il drill-down [nel report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale di chiamata scadente

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Sfruttare al meglio il report del dispositivo

Quando si tratta di nomi di dispositivi, il report del dispositivo è estremamente dettagliato; Supponiamo ad esempio di avere i seguenti dispositivi di acquisizione:

  - Aastra 3002 microfono (2-Aastra 3002)

  - Aastra 3002 microfono (3-Aastra 3002)

  - Aastra 3002 microfono (Aastra 3002)

  - Aastra 6725ip

  - Microfono 6725ip Aastra (10-Aastra 6725ip)

  - Microfono 6725ip Aastra (10-Aastra 6725ip)-V0

  - Microfono 6725ip Aastra (2-Aastra 6725ip)

  - Microfono 6725ip Aastra (3-Aastra 6725ip)

  - Microfono 6725ip Aastra (4-Aastra 6725ip)

  - Microfono 6725ip Aastra (5-Aastra 6725ip)

  - Microfono 6725ip Aastra (6-Aastra 6725ip)

  - Microfono 6725ip Aastra (7-Aastra 6725ip)

  - Microfono 6725ip Aastra (9-Aastra 6725ip)

  - Microfono 6725ip Aastra (9-Aastra 6725ip)-V0

  - Microfono 6725ip Aastra (Aastra 6725ip)

  - Microfono 6725ip Aastra (Aastra 6725ip)-V0

  - Microfono 6725ip Aastra (dispositivo audio USB)

  - Microfono 6725ip Aastra (dispositivo audio USB)-V0

<div>


> [!NOTE]  
> Tieni presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se Esegui versioni localizzate di Lync Server 2013. Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese USA potrebbe avere un nome diverso in francese o spagnolo.



</div>

Spesso si vorrà questo livello di dettaglio; in altri casi, tuttavia, potresti essere interessato al numero di chiamate che usano qualsiasi microfono Aastra, indipendentemente dal tipo di modello. Un modo per ottenere informazioni come questo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvare i dati in un file con valori separati da virgola, ad\\esempio\\C\_: data Devices report. csv. Puoi quindi usare un set di comandi simili a questi per importare. File CSV in Windows PowerShell e riportare il numero totale di chiamate effettuate con un dispositivo di acquisizione Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Questo restituirà un singolo valore che rappresenta il numero totale di chiamate effettuate con un dispositivo di acquisizione di Aastra. Ad esempio:

    384

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report dispositivo consente di filtrare in base a elementi come il tipo di chiamata, ovvero la chiamata a una chiamata client, una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, i dispositivi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report del dispositivo.

### <a name="device-report-filters"></a>Filtri di report per dispositivi

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
<td><p><strong>Causa interruttore vocale</strong></p></td>
<td><p>Motivo per cui una chiamata deve essere inserita in modalità half duplex per evitare l'eco. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Nessuno</p>
</dd>
<dt><span></span></dt>
<dd><p>Timestamp errato</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Bassa complessità</p>
</dd>
<dt><span></span></dt>
<dd><p>Stato del dispositivo non valido</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo post-AEC (annullamento dell'eco acustica)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Causa eco</strong></p></td>
<td><p>Motivo per cui l'eco sopra il livello accettato è stato rilevato in una chiamata. (In telecomunicazioni Echo è un riflesso del suono, lo stesso fenomeno che si sente se si urla in fondo a un pozzo). Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Nessuno</p>
</dd>
<dt><span></span></dt>
<dd><p>Timestamp errato</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo post-AEC (annullamento dell'eco acustica)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (processore nonlineare adattivo)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Ritaglio del microfono</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di chiamata</strong></p></td>
<td><p>Indica il tipo di chiamata effettuata. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Chiamata client</p>
</dd>
<dt><span></span></dt>
<dd><p>Chiamata PSTN</p>
</dd>
<dt><span></span></dt>
<dd><p>Conferenza telefonica</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Interno</p>
</dd>
<dt><span></span></dt>
<dd><p>Esterno</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Cablata</p>
</dd>
<dt><span></span></dt>
<dd><p>Wireless</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>Non VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di dispositivo</strong></p></td>
<td><p>Indica il tipo di dispositivo. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Dispositivo di acquisizione</p>
</dd>
<dt><span></span></dt>
<dd><p>Dispositivo di rendering</p>
</dd>
<dt><span></span></dt>
<dd><p>Coppia di dispositivi di acquisizione/rendering</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Nome dispositivo</strong></p></td>
<td><p>Nome del dispositivo di acquisizione o rendering. È possibile immettere il nome completo del dispositivo o qualsiasi parte del nome del dispositivo. Ad esempio, per trovare il microfono del dispositivo (Microsoft LifeCam VX-1000.), è possibile immettere il nome completo del dispositivo nel modo seguente:</p>
<p>Microfono (Microsoft LifeCam VX-1000.)</p>
<p>In alternativa, è possibile immettere solo una parte del nome. Ad esempio:</p>
<p>LifeCam</p>
<p>Tieni presente che il filtro precedente restituisce qualsiasi dispositivo che contiene la &quot;stringa&quot; LifeCam in qualsiasi punto del suo nome.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report del dispositivo.

### <a name="device-report-metrics"></a>Metriche del report del dispositivo

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
<td><p><strong>Dispositivo di acquisizione</strong></p></td>
<td><p>Sì</p></td>
<td><p>Dispositivo, ad esempio un microfono o una webcam, usato per la trasmissione di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dispositivo di rendering</strong></p></td>
<td><p>Sì</p></td>
<td><p>Dispositivo, ad esempio un auricolare o un altoparlante, usato per ricevere l'audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di chiamate inserite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di chiamate classificate come &quot;scadenti. &quot; Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utenti univoci</strong></p></td>
<td><p>Sì</p></td>
<td><p>Utenti univoci che hanno usato il dispositivo. Se un utente ha usato il dispositivo 13 volte, conta come un utente univoco, come un utente che ha usato solo il dispositivo una sola volta.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto tra il tempo di cambio vocale</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata che deve essere eseguita in modalità half duplex per evitare l'eco. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto del microfono non funzionante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata in cui il dispositivo di acquisizione non funzionava a un livello accettabile. Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di acquisizione che non funziona come previsto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto tra l'altoparlante non funziona</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata in cui il dispositivo di rendering non funzionava a un livello accettabile. Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di rendering che non funziona come previsto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamate con interruttore vocale (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale delle chiamate totali che dovevano essere inserite nella modalità half duplex. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Microfono Echo in (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invio Echo (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di eco trasmessa ad altri utenti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate con Echo (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale delle chiamate totali con echo che supera il livello accettabile.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

