---
title: 'Lync Server 2013: rapporto di distribuzione delle metriche sulla qualità multimediale'
description: 'Lync Server 2013: rapporto di distribuzione delle metriche sulla qualità multimediale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548152"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Il rapporto distribuzione metriche di qualità multimediale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

Il rapporto distribuzione metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica di qualità di esperienza, ad esempio instabilità o perdita di pacchetti. Si supponga, ad esempio, che gli utenti effettuino un totale di 10 chiamate telefoniche; tali 10 chiamate segnalano i seguenti tempi di andata e ritorno:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero di chiamata</th>
<th>Tempo di andata e ritorno (millisecondi)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10  </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


La media per i tempi di andata e ritorno è di 500 millisecondi (5000 diviso 10). 500 millisecondi è un tempo di andata e ritorno estremamente elevato; di conseguenza, è possibile che si verifichi un problema serio con la congestione della rete. (I tempi di andata e ritorno lunghi sono in genere il risultato delle reti di overload).

In realtà, ovviamente, il 90% delle chiamate ha avuto tempi di andata e ritorno eccellenti; si è avuta solo una cattiva chiamata che ha alterato i risultati complessivi. Se si esamina solo il tempo medio di andata e ritorno, è possibile passare a una conclusione molto sbagliata.

Il rapporto distribuzione metriche di qualità multimediale consente di evitare di saltare a conclusioni errate mostrando una distribuzione grafica di una metrica specificata, ad esempio il tempo di andata e ritorno. Questi grafici possono essere utili per chiarire che sono state riportate nove chiamate molto valide e una pessima chiamata. È possibile che si desideri continuare a indagare su una chiamata. Tuttavia, il fatto che 9 chiamate su 10 siano state molto valide suggerisce che non vi è alcun motivo per apportare modifiche drastiche alla rete, almeno non a questo punto nel tempo.

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto distribuzione metriche di qualità multimediale.

### <a name="media-quality-metrics-distribution-report-filters"></a>Filtri del rapporto distribuzione metriche di qualità multimediale

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
<td><p><strong>Minimo nell'asse x</strong></p></td>
<td><p>Valore più basso da visualizzare sull'asse X del grafico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Massimo nell'asse x</strong></p></td>
<td><p>Valore massimo da visualizzare sull'asse X del grafico.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Interno</p></li>
<li><p>Esterno</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
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

