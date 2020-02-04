---
title: 'Lync Server 2013: gestire il ritiro delle chiamate di gruppo durante il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gestire il ritiro delle chiamate di gruppo durante il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Quando un pool Front-end diventa non disponibile a causa di un problema non pianificato, il servizio non viene superato nel pool di backup. Durante il failover nel pool di backup, gli utenti vengono reindirizzati al pool di backup e si trovano in modalità resilienza. Mentre si è in modalità di resilienza, gli utenti non possono raccogliere le chiamate di altri utenti o ricevere le chiamate raccolte da altri utenti. Al termine del failover, gli utenti possono usare di nuovo il pick-up delle chiamate di gruppo come di consueto.

Durante il failback nel pool principale, gli utenti vengono reindirizzati al pool principale e sono di nuovo in modalità di resilienza. La funzionalità di prelievo delle chiamate di gruppo non è disponibile finché gli utenti non sono in modalità resilienza.

In questa sezione vengono illustrate alcune considerazioni relative al ritiro delle chiamate di gruppo durante il ripristino di emergenza e descrive anche l'esperienza utente.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Considerazioni per il ritiro delle chiamate di gruppo durante il ripristino di emergenza

Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover usano l'applicazione Call Park in esecuzione nel pool di backup per i numeri dei gruppi di raccolta chiamate. Pertanto, il supporto per il ritiro delle chiamate di gruppo durante il ripristino di emergenza richiede che l'applicazione Call Park venga distribuita e abilitata sia nel pool principale che nel pool di backup.

Gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di parcheggio delle chiamate devono essere reindirizzati al pool di backup dopo il completamento del processo di failover nel pool di backup. Gli intervalli di numeri devono essere reindirizzati al pool principale dopo il completamento del processo di failback al pool primario. Per reindirizzare gli intervalli di prelievo delle chiamate di gruppo, usare il cmdlet **set-CsCallParkOrbit** .

Se si distribuisce un nuovo pool con un nome di dominio completo diverso (FQDN) per sostituire il pool principale, è necessario riassegnare tutti gli intervalli di numeri di raccolta delle chiamate di gruppo associati al pool primario al nome di dominio completo del nuovo pool. Per riassegnare intervalli di numeri al nuovo pool, è possibile usare il cmdlet **set-CsCallParkOrbit** . Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Esperienza di ritiro delle chiamate di gruppo durante l'errore del pool

La tabella seguente riepiloga l'esperienza di raccolta delle chiamate di gruppo tramite le fasi del ripristino di emergenza.

### <a name="user-experience-during-disaster-recovery"></a>Esperienza utente durante il ripristino di emergenza

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Stato chiamata</th>
<th>Failover per il pool di backup</th>
<th>Failback nel pool primario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Raccolta chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e dagli intervalli di numeri di raccolta chiamate di gruppo vengono reindirizzati al pool di backup</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Raccolta chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</p></li>
</ul>
<p><strong>Al termine del failback:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e dagli intervalli di numeri di raccolta delle chiamate di gruppo vengono reindirizzati al pool primario</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate nella coda di ritiro delle chiamate di gruppo</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite raccolta chiamate di gruppo.</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Nessuna chiamata in questo stato</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite raccolta chiamate di gruppo.</p></li>
</ul>
<p><strong>Al termine del failback:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite raccolta chiamate di gruppo.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chiamata stabilita</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Chiamate rimanete connesse</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Chiamate rimanete connesse</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Chiamate rimanete connesse</p></li>
</ul>
<p><strong>Al termine del failback:</strong></p>
<ul>
<li><p>Chiamate rimanete connesse</p></li>
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

