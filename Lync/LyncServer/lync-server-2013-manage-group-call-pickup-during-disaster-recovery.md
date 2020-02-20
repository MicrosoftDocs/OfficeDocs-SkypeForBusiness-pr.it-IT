---
title: 'Lync Server 2013: gestione del prelievo delle chiamate di gruppo durante il ripristino di emergenza'
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
ms.openlocfilehash: 633ccf1c792f951d13c747c935af51569365c753
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gestire il ritiro delle chiamate di gruppo durante il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Quando un pool Front end diventa non disponibile a causa di un incidente non pianificato, il servizio non viene eseguito nel pool di backup. Durante il failover per il pool di backup, gli utenti vengono reindirizzati al pool di backup e sono in modalità di resilienza. Durante la modalità di resilienza, gli utenti non possono prendere le chiamate di altri utenti o fare in modo che le chiamate vengano raccolte da altri utenti. Al termine del failover, gli utenti possono utilizzare di nuovo il pick-up di chiamata di gruppo come al solito.

Durante il failback al pool primario, gli utenti vengono reindirizzati al pool primario e sono di nuovo in modalità di resilienza. La funzionalità di prelievo delle chiamate di gruppo non è disponibile finché gli utenti non sono in modalità di resilienza.

In questa sezione vengono illustrate alcune considerazioni relative al ritiro delle chiamate di gruppo durante il ripristino di emergenza e viene descritta anche l'esperienza utente.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Considerazioni per il ritiro delle chiamate di gruppo durante il ripristino di emergenza

Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover utilizzano l'applicazione Parcheggio di chiamata in esecuzione nel pool di backup per i numeri del gruppo di prelievo delle chiamate. Pertanto, il supporto per il ritiro delle chiamate di gruppo durante il ripristino di emergenza richiede che l'applicazione Parcheggio di chiamata venga distribuita e abilitata sia nel pool primario che nel pool di backup.

Gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata devono essere reindirizzati al pool di backup dopo il completamento del processo di failover del pool di backup. Gli intervalli di numeri devono essere reindirizzati al pool primario dopo il completamento del processo di failback del pool primario. Per reindirizzare gli intervalli di prelievo delle chiamate di gruppo, utilizzare il cmdlet **set-CsCallParkOrbit** .

Se si distribuisce un nuovo pool con un nome di dominio completo (FQDN) diverso per sostituire il pool primario, è necessario riassegnare tutti gli intervalli di numeri di prelievo delle chiamate di gruppo che sono stati associati al pool primario all'FQDN del nuovo pool. Per riassegnare gli intervalli di numeri al nuovo pool, è possibile utilizzare il cmdlet **set-CsCallParkOrbit** . Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Esperienza di ritiro delle chiamate di gruppo durante l'errore del pool

Nella tabella seguente viene riepilogata l'esperienza di prelievo delle chiamate di gruppo tramite le fasi del ripristino di emergenza.

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
<th>Failback al pool primario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nuove chiamate</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e gli intervalli di numeri di prelievo delle chiamate di gruppo vengono reindirizzati al pool</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo non disponibile per gli utenti in modalità di resilienza</p></li>
</ul>
<p><strong>Dopo il completamento del failback:</strong></p>
<ul>
<li><p>Raccolta di chiamate di gruppo disponibile quando gli utenti fuori dalla resilienza e gli intervalli di numeri di prelievo delle chiamate di gruppo vengono reindirizzati al pool primario</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chiamate nella coda di prelievo delle chiamate di gruppo</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Nessuna chiamata in questo stato</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</p></li>
</ul>
<p><strong>Dopo il completamento del failback:</strong></p>
<ul>
<li><p>Non è possibile rispondere alle chiamate in coda tramite il prelievo delle chiamate di gruppo.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chiamata stabilita</p></td>
<td><p><strong>Durante il processo di failover:</strong></p>
<ul>
<li><p>Chiamate rimanere connesse</p></li>
</ul>
<p><strong>Dopo il completamento del failover:</strong></p>
<ul>
<li><p>Chiamate rimanere connesse</p></li>
</ul></td>
<td><p><strong>Durante il processo di failback:</strong></p>
<ul>
<li><p>Chiamate rimanere connesse</p></li>
</ul>
<p><strong>Dopo il completamento del failback:</strong></p>
<ul>
<li><p>Chiamate rimanere connesse</p></li>
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

