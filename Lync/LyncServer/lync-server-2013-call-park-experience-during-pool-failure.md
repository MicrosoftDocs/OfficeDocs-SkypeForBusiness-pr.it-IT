---
title: 'Lync Server 2013: Esperienza del parcheggio di chiamata durante un errore del pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Esperienza del parcheggio di chiamata in Lync Server 2013 durante un errore del pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-10_

Quando un pool Front-end diventa non disponibile a causa di un evento non pianificato, le chiamate parcheggiate ma non ancora recuperate vengono disconnesse. Durante il failover in un pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità resilienza. In modalità resilienza, gli utenti non possono parcheggiare le chiamate, ma possono effettuare chiamate in attesa e trasferirle. Al termine del failover, le chiamate possono essere di nuovo parcheggiate e recuperate come di consueto. Durante il failback, gli utenti non possono parcheggiare le chiamate finché non si trovano in modalità di resilienza.

Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover usano l'applicazione Parcheggio di chiamata distribuita nel pool di backup. Di conseguenza, gli utenti che vengono reindirizzati al pool di backup usano le impostazioni del parcheggio di chiamata configurate per l'applicazione Call Park nel pool di backup.

La tabella seguente riepiloga l'esperienza di parcheggio delle chiamate attraverso le fasi del ripristino di emergenza.

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
<th>Quando si verifica un'interruzione</th>
<th>Durante il failover</th>
<th>Durante il failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamata non ancora parcheggiata</p></td>
<td><p>La chiamata rimane connessa, ma non può essere parcheggiata.</p></td>
<td><ul>
<li><p>Durante il failover, la chiamata non può essere parcheggiata mentre gli utenti sono in modalità di resilienza, ma possono essere messi in attesa e trasferiti.</p></li>
<li><p>Quando il failover viene completato, la chiamata può essere parcheggiata e recuperata.</p></li>
</ul></td>
<td><ul>
<li><p>Durante il failback, la chiamata non può essere parcheggiata mentre gli utenti sono in modalità di resilienza, ma possono essere messi in attesa e trasferiti.</p></li>
<li><p>Quando il failback viene completato, la chiamata può essere parcheggiata e recuperata.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamata parcheggiata, ma non ancora recuperata</p></td>
<td><p>La chiamata è disconnessa.</p></td>
<td><p>Nessuna chiamata in questo stato.</p></td>
<td><p>La chiamata rimane parcheggiata.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamata parcheggiata già recuperata</p></td>
<td><p>La chiamata rimane connessa.</p></td>
<td><p>La chiamata rimane connessa.</p></td>
<td><p>La chiamata rimane connessa.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

