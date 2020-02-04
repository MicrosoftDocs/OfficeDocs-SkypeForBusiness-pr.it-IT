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
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Monitoraggio della chat di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-04_

Ti consigliamo vivamente di eseguire il [programma di installazione dell'aggiornamento cumulativo](http://support.microsoft.com/kb/968802) più recente disponibile nell'area download Microsoft per migliorare le prestazioni.

Supponendo che l'aggiornamento cumulativo sia stato eseguito più tardi, usare la tabella di test di stress seguente per la metrica per capire se i server di chat di gruppo sono in uso in condizioni ottimali.

### <a name="test-environment-and-user-model"></a>Ambiente di test e modello utente

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
<td><p>Tre server di chat di gruppo in un pool di chat di gruppo, ognuno con 8 GB di memoria e 8 processori.</p></td>
</tr>
<tr class="even">
<td><p>Due front ends di Lync Server 2013 in Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 utenti simultanei in tre server di chat di gruppo.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canali ospitati dal pool di chat di gruppo.</p></td>
</tr>
<tr class="odd">
<td><p>Dimensioni canale:</p>
<ul>
<li><p>Dimensioni canale piccolo: 30</p></li>
<li><p>Dimensioni canale medio: 150</p></li>
<li><p>Dimensioni canale grande: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Conteggio canali:</p>
<ul>
<li><p>Numero di canali piccoli: 24.000</p></li>
<li><p>Numero medio canali 800</p></li>
<li><p>Canali numero grande 24</p></li>
<li><p>Totale canali 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Invitare i canali:</p>
<ul>
<li><p>La metà dei canali sono stati invitare canali</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Numero di canali che un utente si unisce:</p>
<ul>
<li><p>Dimensioni minime: 12</p></li>
<li><p>Media: 2</p></li>
<li><p>Dimensioni: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tasso di partecipazione:</p>
<ul>
<li><p>10 totale/secondo, 3.33/secondo per server</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Velocità di logout:</p>
<ul>
<li><p>10 totale/secondo, 3.33/secondo per server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tariffa chat:</p>
<ul>
<li><p>20 totali/secondi, 6.66/secondo per server</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> I numeri di contatore delle prestazioni seguenti possono variare in caso di utilizzo di specifiche hardware o profili utente diversi.



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
<th>Le soglie</th>
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

