---
title: 'Lync Server 2013: record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60700070c5426d4df4d1957367ccfd743a5ba44b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Record di utilizzo PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-23_

La pianificazione dei record utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni per le chiamate attualmente in vigore nell'organizzazione, dal CEO fino ai dipendenti a tempo determinato, ai consulenti e al personale contingente. Questo processo offre anche la possibilità di riesaminare le autorizzazioni esistenti per le chiamate e modificarle. È possibile creare record utilizzo PSTN solo per le autorizzazioni per le chiamate applicabili agli utenti previsti di VoIP aziendale, ma potrebbe essere una soluzione a lungo termine più efficace creare record utilizzo PSTN per tutte le autorizzazioni per le chiamate, anche se alcune potrebbero non essere al momento applicabili al gruppo di utenti da abilitare per VoIP aziendale. In questo modo, se le autorizzazioni per le chiamate subiscono modifiche o vengono aggiunti nuovi utenti con autorizzazioni diverse per le chiamate, saranno già stati creati i record utilizzo PSTN necessari.

Nella tabella seguente viene illustrata una tipica tabella di record di utilizzo PSTN:

### <a name="pstn-usage-records"></a>Record utilizzo PSTN

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo telefono</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Chiamate locali</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Chiamate interurbane</p></td>
</tr>
<tr class="odd">
<td><p>Internazionali</p></td>
<td><p>Chiamate internazionali</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Dipendenti a tempo pieno di Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Dipendenti a tempo pieno di Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Dipendenti a tempo determinato di Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurigo</p></td>
<td><p>Dipendenti a tempo pieno di Zurigo</p></td>
</tr>
</tbody>
</table>


I record di utilizzo PSTN non svolgono di per sé alcuna funzione. Per utilizzarli, è necessario associarli agli elementi seguenti:

  - Criteri vocali, assegnati agli utenti.

  - Route, assegnate ai numeri di telefono.

Per informazioni dettagliate sui criteri vocali e le route, vedere [Voice Policies in Lync server 2013](lync-server-2013-voice-policies.md) e [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md). Per informazioni dettagliate su come crearli e configurarli, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

