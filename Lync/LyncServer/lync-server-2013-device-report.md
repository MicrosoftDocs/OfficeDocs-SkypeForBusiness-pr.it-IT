---
title: 'Lync Server 2013: rapporto dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97971d339dc57ab8786ff4a05adadd016a87e23a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522453"
---
# <a name="device-report-in-lync-server-2013"></a>Report dispositivo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-12_

Il Rapporto dispositivi potrebbe anche essere intitolato Rapporto altoparlanti e microfono perché il Rapporto dispositivi recupera le metriche relative alle chiamate (ad esempio, la percentuale di chiamate con qualità insufficiente, l'eco e il tempo commutazione vocale) raggruppate in base ai microfoni e agli altoparlanti utilizzati nella chiamata. Se si è interessati ai telefoni IP (noti anche come "dispositivi"), utilizzare il [rapporto inventario telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .

Il Rapporto dispositivi è estremamente utile agli amministratori per stabilire se un tipo specifico di dispositivo riporta volumi elevati di chiamate con qualità insufficiente rispetto ad altri. Questo può influire sulle decisioni da prendere in merito all'acquisto di nuovi dispositivi o alla sostituzione dei dispositivi esistenti.

Per impostazione predefinita, le informazioni visualizzate nel Rapporto dispositivi si basano sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolari (il dispositivo di rendering) utilizzati nella chiamata. Ad esempio, si supponga che vari utenti debbano utilizzare il dispositivo di acquisizione e il dispositivo di rendering seguenti:

  - Dispositivo di acquisizione -- Microfono (HD Audio integrato digitale SoundMAX)

  - Dispositivo di rendering -- Auricolare e microtelefono (Microsoft LifeChat LX-3000)

Se gli utenti hanno eseguito un totale di 254 chiamate, nel rapporto verrà visualizzata una voce simile alla seguente:


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
<td><p>Microfono (HD Audio integrato digitale SoundMAX)</p></td>
<td><p>Auricolare e microtelefono (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Ora si supponga che un certo numero di utenti utilizzi lo stesso dispositivo di acquisizione ma un dispositivo di rendering diverso. In tal caso, nel report verrà visualizzata una voce nella seconda riga per tale combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:


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
<td><p>Microfono (HD Audio integrato digitale SoundMAX)</p></td>
<td><p>Auricolare e microtelefono (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Microfono (HD Audio integrato digitale SoundMAX)</p></td>
<td><p>Altoparlanti (HD Audio integrato digitale SoundMAX)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Se si desidera visualizzare i totali combinati per un determinato dispositivo (ad esempio, per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering utilizzato), selezionare l'opzione appropriata dall'elenco a discesa Tipo di dispositivo (Dispositivo di acquisizione o Dispositivo di rendering). Se nell'esempio si seleziona Dispositivo di acquisizione, si riceverà il seguente output:


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
<td><p>Microfono (HD Audio integrato digitale SoundMAX)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Accesso al Rapporto dispositivi

In genere è possibile accedere al Rapporto dispositivi dalla home page Relazioni monitoraggio. Tuttavia, se si sta visualizzando il [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) , è possibile eseguire il drill-down nel rapporto dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:

  - Dispositivo di acquisizione

  - Dispositivo di rendering

Dal rapporto dispositivo è possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale chiamate di livello insufficiente

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Utilizzo del Rapporto dispositivi

Il Rapporto dispositivi è molto dettagliato in merito ai nomi dei dispositivi. Ad esempio, si supponga di disporre dei dispositivi di acquisizione seguenti:

  - Microfono Aastra 3002 (2- Aastra 3002)

  - Microfono Aastra 3002 (3- Aastra 3002)

  - Microfono Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Microfono Aastra 6725ip (10- Aastra 6725ip)

  - Microfono Aastra 6725ip (10- Aastra 6725ip)-V0

  - Microfono Aastra 6725ip (2- Aastra 6725ip)

  - Microfono Aastra 6725ip (3- Aastra 6725ip)

  - Microfono Aastra 6725ip (4- Aastra 6725ip)

  - Microfono Aastra 6725ip (5- Aastra 6725ip)

  - Microfono Aastra 6725ip (6- Aastra 6725ip)

  - Microfono Aastra 6725ip (7- Aastra 6725ip)

  - Microfono Aastra 6725ip (9- Aastra 6725ip)

  - Microfono Aastra 6725ip (9- Aastra 6725ip)-V0

  - Microfono Aastra 6725ip (Aastra 6725ip)

  - Microfono Aastra 6725ip (Aastra 6725ip)-V0

  - Microfono Aastra 6725ip (dispositivo audio USB)

  - Microfono Aastra 6725ip (dispositivo audio USB)-V0

<div>


> [!NOTE]  
> Tenere presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se si eseguono versioni localizzate di Lync Server 2013. Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese (Stati Uniti) potrebbe avere un nome diverso in francese o spagnolo.



</div>

Anche se spesso è utile questo livello di dettaglio, a volte si potrebbe essere interessati solo al numero di chiamate che utilizzano qualsiasi microfono Aastra, indipendentemente dal numero del modello. Un modo per ottenere informazioni di questo tipo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvarli in un file con valori delimitati da virgole (ad esempio, C: \\ data \\ devices \_Report.csv). È possibile utilizzare un insieme di comandi simili a questi per importare il file CSV in Windows PowerShell e restituire il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Verrà restituito un unico valore che rappresenta il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra. Ad esempio:

    384

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto dispositivi consente di filtrare in base a elementi quali il tipo di chiamata (ossia se la chiamata è di tipo client) una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dispositivi sono raggruppabili per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri applicabili al Rapporto dispositivi.

### <a name="device-report-filters"></a>Filtri del Rapporto dispositivi

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
<td><p><strong>Causa commutazione vocale</strong></p></td>
<td><p>Motivo per cui è stato necessario effettuare una chiamata in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie. Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Nessuno</p>
</dd>
<dt><span></span></dt>
<dd><p>Timestamp non valido</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (dynamic nonlinear processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Complessità bassa</p>
</dd>
<dt><span></span></dt>
<dd><p>Stato dispositivo non valido</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco dopo eliminazione eco acustica</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Causa eco</strong></p></td>
<td><p>Motivo per cui in una chiamata è stato rilevato l'eco sopra il livello accettato (nelle telecomunicazioni l'eco è un riflesso del suono, lo stesso effetto che si produce gridando verso il fondo di un pozzo). Selezionare una delle opzioni seguenti:</p>
<dl>
<dt><span></span></dt>
<dd><p>Tutti</p>
</dd>
<dt><span></span></dt>
<dd><p>Nessuno</p>
</dd>
<dt><span></span></dt>
<dd><p>Timestamp non valido</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco dopo eliminazione eco acustica</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (adaptive nonlinear processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (dynamic nonlinear processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Clip microfono</p>
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
<td><p>Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</p>
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
<td><p>Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</p>
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
<td><p>Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</p>
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
<td><p>Nome del dispositivo di acquisizione o di rendering. È possibile immettere il nome completo del dispositivo o una parte di esso. Ad esempio, per trovare il dispositivo Microfono (Microsoft LifeCam VX-1000.), è possibile immettere il nome del dispositivo completo come segue:</p>
<p>Microfono (Microsoft LifeCam VX-1000.)</p>
<p>In alternativa, è possibile immettere solo una parte del nome, ad esempio:</p>
<p>LifeCam</p>
<p>Si noti che il filtro precedente restituisce qualsiasi dispositivo che contiene la stringa &quot; LifeCam &quot; Anywhere nel relativo nome.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto dispositivi.

### <a name="device-report-metrics"></a>Metriche del rapporto dispositivi

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
<td><p><strong>Dispositivo di acquisizione</strong></p></td>
<td><p>Sì</p></td>
<td><p>Dispositivo (ad esempio un microfono o una webcam) utilizzato per la trasmissione dell'audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dispositivo di rendering</strong></p></td>
<td><p>Sì</p></td>
<td><p>Dispositivo (ad esempio cuffie o altoparlanti) utilizzato per la ricezione dell'audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di chiamate effettuate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale chiamate di livello insufficiente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di chiamate classificate di qualità &quot; scadente. &quot; Una chiamata scadente è qualsiasi chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata in cui si è verificato un eccessivo instabilità.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utenti univoci</strong></p></td>
<td><p>Sì</p></td>
<td><p>Utenti univoci che hanno utilizzato il dispositivo. Se un utente ha utilizzato 13 volte il dispositivo, verrà conteggiato come utente univoco, come un utente che ha utilizzato il dispositivo una sola volta.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto di tempo commutazione vocale</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata che è stato necessario effettuare in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto di microfono non funzionante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata in cui il dispositivo di acquisizione non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di acquisizione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto di altoparlante non funzionante</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale della chiamata in cui il dispositivo di rendering non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di rendering.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamate con commutazione vocale (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale delle chiamate totali che è stato necessario effettuare in modalità half-duplex. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eco microfono in ingresso (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco. Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invio eco (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di eco trasmesso ad altri utenti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate con eco (%)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale delle chiamate totali con eco superiore al livello accettabile.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

