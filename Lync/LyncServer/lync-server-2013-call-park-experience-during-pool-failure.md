---
title: 'Lync Server 2013: esperienza del parcheggio di chiamata durante un errore del pool'
description: 'Lync Server 2013: esperienza del parcheggio di chiamata durante un errore del pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565272"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Esperienza del parcheggio di chiamata in Lync Server 2013 durante un errore del pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-10_

Quando un pool Front end non è disponibile a causa di un incidente non pianificato, le chiamate che sono state parcheggiate ma non ancora recuperate sono disconnesse. Durante l'esecuzione di un failover in un pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità di resilienza. In modalità di resilienza gli utenti non possono parcheggiare le chiamate, ma possono mettere le chiamate in attesa e trasferirle. Completato il failover, è possibile parcheggiare nuovamente le chiamate e recuperarle normalmente. Durante il failback, gli utenti non possono parcheggiare le chiamate finché non sono usciti dalla modalità di resilienza.

Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover utilizzano l'applicazione Parcheggio di chiamata distribuita nel pool di backup. Di conseguenza, gli utenti che vengono reindirizzati al pool di backup utilizzano le impostazioni del parcheggio di chiamata configurate per l'applicazione Parcheggio di chiamata nel pool di backup.

Nella tabella seguente viene riepilogata l'esperienza del parcheggio di chiamata tramite le fasi del ripristino di emergenza.

### <a name="user-experience-during-disaster-recovery"></a>Esperienza utente durante il ripristino di emergenza

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Stato chiamata</th>
<th>In caso di guasto</th>
<th>Durante il failover</th>
<th>Durante il failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamata non ancora parcheggiata</p></td>
<td><p>La chiamata rimane connessa, ma non può essere parcheggiata.</p></td>
<td><ul>
<li><p>Durante il failover non è possibile parcheggiare la chiamata mentre gli utenti sono in modalità di resilienza, ma è possibile metterla in attesa e trasferirla.</p></li>
<li><p>Completato il failover, è possibile parcheggiare e recuperare la chiamata.</p></li>
</ul></td>
<td><ul>
<li><p>Durante il failback non è possibile parcheggiare la chiamata mentre gli utenti sono in modalità di resilienza, ma è possibile metterla in attesa e trasferirla.</p></li>
<li><p>Completato il failback, è possibile parcheggiare e recuperare la chiamata.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamata parcheggiata, ma non ancora recuperata</p></td>
<td><p>La chiamata viene interrotta.</p></td>
<td><p>Nessuna chiamata in questo stato.</p></td>
<td><p>La chiamata resta parcheggiata.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamata parcheggiata già recuperata</p></td>
<td><p>Le chiamate restano connesse.</p></td>
<td><p>Le chiamate restano connesse.</p></td>
<td><p>Le chiamate restano connesse.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

