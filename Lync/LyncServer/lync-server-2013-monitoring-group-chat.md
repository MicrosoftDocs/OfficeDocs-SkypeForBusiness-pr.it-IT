---
title: 'Lync Server 2013: monitoraggio chat di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Monitoraggio chat di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-04_

È consigliabile eseguire il [programma di installazione degli aggiornamenti cumulativi del server](http://support.microsoft.com/kb/968802) più recente disponibile nell'area download Microsoft per migliorare le prestazioni.

Presupponendo che si esegua l'aggiornamento cumulativo più recente, utilizzare la tabella di test di stress seguente per valutare se i server di chat di gruppo sono in esecuzione in condizioni di integrità ottimali.

### <a name="test-environment-and-user-model"></a>Ambiente di testing e modello utente

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tre server chat di gruppo in un pool di chat di gruppo, ognuno con 8 GB di memoria e 8 processori.</p></td>
</tr>
<tr class="even">
<td><p>Due front-end di Lync Server 2013 in Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 utenti simultanei su tre server chat di gruppo.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canali ospitati dal pool di chat di gruppo.</p></td>
</tr>
<tr class="odd">
<td><p>Dimensione canale:</p>
<ul>
<li><p>Dimensione canale piccolo: 30</p></li>
<li><p>Dimensione canale medio: 150</p></li>
<li><p>Dimensione canale di grandi dimensioni: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Conteggio canali:</p>
<ul>
<li><p>Canali di piccole dimensioni: 24.000</p></li>
<li><p>Numero medio di canali 800</p></li>
<li><p>Numero di canali di grandi dimensioni 24</p></li>
<li><p>Totale canali 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Invitare i canali:</p>
<ul>
<li><p>La metà dei canali sono stati invitare i canali</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Numero di canali che un utente unisce:</p>
<ul>
<li><p>Piccolo: 12</p></li>
<li><p>Media: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tasso di partecipazione:</p>
<ul>
<li><p>10 totale/secondo, 3,33/secondo per server</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Velocità di logout:</p>
<ul>
<li><p>10 totale/secondo, 3,33/secondo per server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Velocità chat:</p>
<ul>
<li><p>20 totale/secondo, 6.66/secondo per server</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> I numeri di contatore delle prestazioni seguenti variano probabilmente quando si utilizzano specifiche hardware o profili utente diversi.



</div>

### <a name="performance-counter-to-be-monitored"></a>Contatore delle prestazioni da monitorare

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contatore delle prestazioni</th>
<th>Soglie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processo (ChannelService)-&gt;% tempo processore</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

